# Optimizing the dockerfiles

I used FROM node when building my Dockerfiles, after having noticed that 
I could skip installation steps doing this, which probably has had an effect
on the size.  

For the frontend the build process the only commands that took up space where 
npm install (357kB) and COPY (147MB). However, according to image ls the entire image size was 1.05GB. 

For the backend I ran npm audit fix (4.21MB) and npm install (58.3MB). COPY 
only took 220kB. To optimize I combined the RUN commands in the backend. After that 
they only took up 211kB and the COPY command 50.6MB. Difference in overallsize was 
not very significant, and for some reason the two commands "changed places" in
size demands.

## Further optimization

After some research I noticed that the biggest impact on the image size was the version of node
I was using, and after changing to node:alpine my backend image size went down from 959MB to 131MB.
   
For the frontend the effect was similar, going down from 1.05GB to 227MB. 

I found some other options for optimizing image size such as using the base alpine image and excluding
development dependencies. I ran these changees using the dockerfile from [this site](https://blog.sourcerer.io/a-crash-course-on-optimizing-your-docker-images-for-production-46f175fdffa8)
as a base. Contrary to expectations the image size actually went up, so I reverted to the original alpine image.  

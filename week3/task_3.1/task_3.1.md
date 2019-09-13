# Optimizing the dockerfiles

I initially used FROM node when building my Dockerfiles, after having noticed that 
I could skip installation steps doing this, but for this exercise I built new 
ubuntu images. In the process I noticed Ubuntu was much lighter. 

The image size for the frontend when built with node had been a whopping a 1.05GB, which
went down to 442MB when using (totally non-optimized) Ubuntu. After optimization the size
further decreased to 414MB.

For the backend the initial size of the image was 356MB, which was considerably less than the size
of the Node image (971MB) I'd first used. After optimization the size went down to 328MB. See the attached Dockerfiles. 


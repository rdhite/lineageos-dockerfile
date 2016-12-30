# Stock LineageOS Image

#### NOTE! At this time (30-DEC-2016) Cyanogenmod is transitioning to LineageOS. The full 
migration has not happened. Some steps in making the source code for your device may (read 
*probably will*) attempt to pull from \*.cyanogenmod.org which will result in a failed make 
because that domain has been freed.

The provided Dockerfile will create an image that is ready to pull the stock LineageOS source 
code and compile it. The image will not create a non-root user and all code/binaries will belong 
to root. 

If you need a non-root user (if you aren't sure, then assume you do), create a new user and 
transfer ownership of repo and LineageOS code
```
$ useradd -m userName
$ password userName
$ chown -R userName /home/bin
$ chown -R userName /home/LineageOS
# add "export PATH=$PATH:~/bin" (sans quotes) to /home/userName/.bashrc
```

Each time a container is started using this image and that container has a non-root user, be 
sure to switch from root to that user
```
$ su - userName
```

If you need to sync:
```
$ cd /home/LineageOS && repo sync
```

For information on using LineageOS, please refer to [the LineageOS 
website.](http://www.lineageos.org/)

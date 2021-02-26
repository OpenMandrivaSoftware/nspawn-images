# Create ABF client builder image with mkosi

This set of configs and tools will help you to create ABF client builder image with `mkosi`, which you can run with `systemd-nspawn` on your host. Here are the steps:

    git clone https://github.com/OpenMandrivaSoftware/nspawn-images.git

    cd nspawn-images/omv-builder
Log in as a root.
Make sure you have installed `mkosi` already. If not run:

    dnf install mkosi
If everything is good, you may want to start to build an image by running:

    mkosi

All needed configurations are stored in `mkosi.default` file
When image is done copy `omv-builder.nspawn` to `/etc/systemd/nspawn`. Now it is time to start our image:

    systemd-nspawn -bi omv-x86_64-builder

You may log in as root to check if everything is working.

## Tips & tricks

If you are about to test someting and you will be rebuilding image then it is good idea to use cache by simply creating a directory:

    mkdir -p mkosi.cache
If you want to change someting on image, or run services etc.. just edit `mkosi.postinst`


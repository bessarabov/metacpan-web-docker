# Runnig metacpan-web in docker.

This is an experiment to run [Web interface for MetaCPAN][web] in [Docker][d]

You can build a docker image with command:

    docker build --tag metacpan .

And when you have docker image you can run in with the command:

    docker run --publish 8000:5001 --detach metacpan

With running container you can open metacpan web at http://127.0.0.1:8000
(but you need to change 127.0.0.1 to the ip of your docker virtual machine)

If you want to run metacpan web with your custom config you can use config
file from your docker host system like this:

    docker run \
        --publish 8000:5001 \
        --volume /absolute/path/to/metacpan_web.conf:/root/metacpan_web.conf \
        --detach \
        metacpan

 [web]: https://github.com/CPAN-API/metacpan-web
 [d]: https://www.docker.com/

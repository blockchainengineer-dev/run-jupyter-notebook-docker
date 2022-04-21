# run-jupyter-notebook-docker
Run a Jupyter Notebook from a Docker container hosted on Ubuntu Cloud server.

1) ssh into your Ubuntu server `ssh -i 'THE-PATH-TO-YOUR-SSH-KEY' root@YOUR-IP-ADDRESS` change root to your username if required
2) Ensure docker is installed by running the command `docker --version`
3) Ensure that you have a docker image built, use the command `docker images` to view the images built on you docker install
4) To run the docker image use the following command `docker run -it -p 8888:8888 pythonimage`  
    ...here we are using the `-it` tag for interactive pseudo-tty. 
    ... we also expose port 8888 and map it to port 8888 on our hosting machine with `-p 8888:8888`  
    Now we're inside a docker container with it's commandline 
5) Use the following command to run the Jupyter Notebook (ensure that you have it installed, it may be installed with your docker image already but of not then you'll need to install in manually) `jupyter notebook --port=8888 --no-browser --ip=0.0.0.0 --allow-root -v /path/to/notebooks:/path/to/notebooks`

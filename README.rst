docker-test
================
+ some dockerfiles to test docker.

docker command
---------------
+ **install**
.. code-block:: console

	$ sudo apt-get install apt-transport-https
	$ sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 	36A1D7869245C8950F966E92D8576A8BA88D21E9
	$ sudo bash -c "echo deb https://get.docker.io/ubuntu docker main > /etc/apt/sources.list.d/docker.list"
	$ sudo apt-get update
	$ sudo apt-get install lxc-docker

+ **pull images**
.. code-block:: console

	$ sudo docker pull ubuntu:14.04

+ **rm container**
.. code-block:: console

	$ sudo docker rm -f $(docker ps -a -q)

+ **rmi images**
.. code-block:: console

	$ sudo docker rmi <container>

+ **enter container**
.. code-block:: console

	$ sudo docker exec -i -t <container> bin/bash

+ **build Dockfile**
.. code-block:: console

	$ sudo docker build -t <repository:tag> .

+ **run images**
.. code-block:: console

	$ sudo docker run -t -i <repository:tag> bin/bash

+ **modify image**
1. run images
2. remember the unique id followed by the root.

.. code-block:: console

	$ sudo docker commit -m "commit" -a "maintainer" id <repository:tag>
    
+ **save image**
.. code-block:: console

	$ sudo docker save -o name.tar <repository:tag>

+ **load image**
.. code-block:: console

	$ sudo docker load --input name.tar

+ **mount volume**
.. code-block:: console

	$ sudo docker run -d -P --name web -v /src/webapp:/opt/webapp <repository:tag> python app.py

+ **mount volume container**
.. code-block:: console

	$ sudo docker run -d -v /dbdata --name dbdata <repository:tag> echo Dta-only container for postgres
	$ sudo docker run -d --volume-from dbdata --name db1 <repository:tag>
	$ sudo docker run -d --volume-from dbdata --name db2 <repository:tag>

+ **map hostPort containerPort**
.. code-block:: console

	$ sudo docker run -d -p 5000:5000 -p 3000:80 <repository:tag> python app.py

+ **docker log**
.. code-block:: console

	$ sudo docker logs -f <container name>

+ **show port map**
.. code-block:: console

	$ sudo docker port <container name> <port>


    

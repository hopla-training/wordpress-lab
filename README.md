# wordpress-lab

## Wordpress Lab for learning porpouses.

### [@frjaraur](https://github.com/frjaraur)
### [@hoplasoftware](https://github.com/hopla-training)

1. Create your swarm cluster

3. We will use __"wplab"__ as stack name, this is important because compose file will use this name for secrets objects.

    __If you change this name you should change stack file too.__

4. Create two secret objects for this stack deployment.

    (In this case we will use current date hashed as password for both Mysql secrets)
~~~

$ date | md5sum | docker secret create wplab_mysqlpassword -

$ date | md5sum | docker secret create wplab_mysqlrootpassword -

~~~

5. Deploy stack/compose file __"wordpress-lab.V3.yml"__.

~~~

$ docker stack deploy -c wordpress-lab.V3.yml wplab

~~~

6. Review deployed stack

~~~

$ docker stack ps wplab

~~~

7. Access Wordpress published on port 8080 (using __"routing mesh"__ your deplyment will be available on all host).

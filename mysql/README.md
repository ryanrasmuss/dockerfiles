# Quick MySQL Container

Need to make ``conf/environment.conf`` with ``MYSQL_ROOT_PASSWORD=yourpw``.

See ``Dockerfile`` comments for bulding/running.

Connect with: ``docker exec -ti [container_id] mysql -u root -p``

``show databases;``

``use [database];``

``show tables;``

``select * from [table_name];``

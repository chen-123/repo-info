## `mysql:latest`

```console
$ docker pull mysql@sha256:691c55aabb3c4e3b89b953dd2f022f7ea845e5443954767d321d5f5fa394e28c
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `mysql:latest` - linux; amd64

```console
$ docker pull mysql@sha256:12e70236ec8be07b87a95008a22deb0a2a6289ac81d852e622ea13e8311cec64
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **123.7 MB (123684558 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5195076672a7e30525705a18f7d352c920bbd07a5ae72b30e374081fe660a011`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 13 Mar 2018 22:27:37 GMT
ADD file:e3250bb9848f956bdb43b205f1237df0d81a25088c95dbdeb20a1e2baf1d884f in / 
# Tue, 13 Mar 2018 22:27:37 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 07:45:05 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Wed, 14 Mar 2018 07:45:14 GMT
RUN apt-get update && apt-get install -y --no-install-recommends gnupg dirmngr && rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 07:45:14 GMT
ENV GOSU_VERSION=1.7
# Wed, 14 Mar 2018 07:45:52 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -rf "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Wed, 14 Mar 2018 07:45:53 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 14 Mar 2018 07:45:58 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		pwgen 		openssl 		perl 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 07:46:02 GMT
RUN set -ex; 	key='A4A9406876FCBD3C456770C88C718D3B5072E1F5'; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	gpg --export "$key" > /etc/apt/trusted.gpg.d/mysql.gpg; 	rm -rf "$GNUPGHOME"; 	apt-key list > /dev/null
# Wed, 14 Mar 2018 07:47:28 GMT
ENV MYSQL_MAJOR=5.7
# Wed, 14 Mar 2018 07:47:28 GMT
ENV MYSQL_VERSION=5.7.21-1debian9
# Wed, 14 Mar 2018 07:47:29 GMT
RUN echo "deb http://repo.mysql.com/apt/debian/ stretch mysql-${MYSQL_MAJOR}" > /etc/apt/sources.list.d/mysql.list
# Wed, 14 Mar 2018 07:47:51 GMT
RUN { 		echo mysql-community-server mysql-community-server/data-dir select ''; 		echo mysql-community-server mysql-community-server/root-pass password ''; 		echo mysql-community-server mysql-community-server/re-root-pass password ''; 		echo mysql-community-server mysql-community-server/remove-test-db select false; 	} | debconf-set-selections 	&& apt-get update && apt-get install -y mysql-server="${MYSQL_VERSION}" && rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Wed, 14 Mar 2018 07:47:51 GMT
VOLUME [/var/lib/mysql]
# Wed, 14 Mar 2018 07:47:52 GMT
COPY file:05922d368ede304251c6ec3c7ddaaad93a2e4694cba77c9b3df80e006edd7b0e in /usr/local/bin/ 
# Wed, 14 Mar 2018 07:47:52 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Wed, 14 Mar 2018 07:47:53 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 14 Mar 2018 07:47:53 GMT
EXPOSE 3306/tcp
# Wed, 14 Mar 2018 07:47:53 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:2a72cbf407d67c7a7a76dd48e432091678e297140dce050ad5eccad918a9f8d6`  
		Last Modified: Tue, 13 Mar 2018 22:54:21 GMT  
		Size: 22.5 MB (22488979 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38680a9b47a889afdad30e2b778870f30b2adfb670996da71d32fef815446b32`  
		Last Modified: Wed, 14 Mar 2018 08:05:32 GMT  
		Size: 1.7 KB (1741 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c732aa0eb1bf8ee7a7dfdb2acdb3d1579110241fe47747d2b14a77e2cb504e2`  
		Last Modified: Wed, 14 Mar 2018 08:05:33 GMT  
		Size: 4.5 MB (4498488 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5317a34eddd75b2b48e525137d7d7adc1cbba157fe58eb2fc60bf93b68c7b28`  
		Last Modified: Wed, 14 Mar 2018 08:05:30 GMT  
		Size: 1.3 MB (1270416 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f92be680366c04fd6f6389a6d54d675219999b5af8d26146855f65cdba9fb79d`  
		Last Modified: Wed, 14 Mar 2018 08:05:30 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e8ecd8bec5abc5756bbbd1df8ddbe1a353ed521659cfeffeea3c0beed5b9edf2`  
		Last Modified: Wed, 14 Mar 2018 08:05:35 GMT  
		Size: 12.1 MB (12089678 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2a650284a6a80b0d6c4e22f2bd30138dbc439743c5ffc2f1aed4f0a46bb4a5f9`  
		Last Modified: Wed, 14 Mar 2018 08:05:29 GMT  
		Size: 21.3 KB (21308 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b5108d08c6de25ab4c9deb68b97ab4730e29a791ed4df8a4eb8be1dc923cd3a`  
		Last Modified: Wed, 14 Mar 2018 08:10:41 GMT  
		Size: 225.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:beaff1261757f472efc32ac65001ca49560f36549d9d15d05cf02bc92bc37f19`  
		Last Modified: Wed, 14 Mar 2018 08:10:56 GMT  
		Size: 83.3 MB (83310806 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c1a55c6375b519dfc0e608b14d744836952d8c475b81a4c9626fddf2e758fd01`  
		Last Modified: Wed, 14 Mar 2018 08:10:41 GMT  
		Size: 2.7 KB (2681 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8181cde51c6516c052322c7a2b0ca6639b86ef4c2439abe153748f04e30e80b0`  
		Last Modified: Wed, 14 Mar 2018 08:10:41 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

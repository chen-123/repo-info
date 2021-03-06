## `percona:latest`

```console
$ docker pull percona@sha256:d86cf09f14643a97ef5c1a85c4a5b5636f1a1d58fa44f243175ad620902301d3
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `percona:latest` - linux; amd64

```console
$ docker pull percona@sha256:bd15650694e98597c7735a5b4257982763418f2915ef8b590aa8cf94298a9f73
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **141.4 MB (141382891 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:892c97e4dcb024cd908b92848cb98dd1bf8dee667710ecb0d12787c372615f18`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mysqld"]`

```dockerfile
# Tue, 13 Mar 2018 21:57:21 GMT
ADD file:bc844c4763367b5f0ac7b9aebf7d43900d98f2aca101b886f185347b24973dbe in / 
# Tue, 13 Mar 2018 21:57:22 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 05:22:25 GMT
RUN groupadd -r mysql && useradd -r -g mysql mysql
# Wed, 14 Mar 2018 13:44:57 GMT
ENV GOSU_VERSION=1.7
# Wed, 14 Mar 2018 13:45:29 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends ca-certificates wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove ca-certificates wget
# Wed, 14 Mar 2018 13:45:30 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Wed, 14 Mar 2018 13:45:51 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		apt-transport-https ca-certificates 		pwgen 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 13:45:51 GMT
ENV GPG_KEYS=430BDF5C56E7C94E848EE60C1C4CBDCDCD2EFD2A 	4D1BB29D63D98E422B2113B19334A25F8507EFA5
# Wed, 14 Mar 2018 13:45:57 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/percona.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Wed, 14 Mar 2018 13:45:58 GMT
RUN echo 'deb https://repo.percona.com/apt jessie main' > /etc/apt/sources.list.d/percona.list
# Wed, 14 Mar 2018 13:45:58 GMT
ENV PERCONA_MAJOR=5.7
# Wed, 14 Mar 2018 13:45:58 GMT
ENV PERCONA_VERSION=5.7.21-20-1.jessie
# Wed, 14 Mar 2018 13:46:40 GMT
RUN { 		for key in 			percona-server-server/root_password 			percona-server-server/root_password_again 			"percona-server-server-$PERCONA_MAJOR/root-pass" 			"percona-server-server-$PERCONA_MAJOR/re-root-pass" 		; do 			echo "percona-server-server-$PERCONA_MAJOR" "$key" password 'unused'; 		done; 	} | debconf-set-selections 	&& apt-get update 	&& apt-get install -y 		percona-server-server-$PERCONA_MAJOR=$PERCONA_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& sed -ri 's/^user\s/#&/' /etc/mysql/my.cnf 	&& rm -rf /var/lib/mysql && mkdir -p /var/lib/mysql /var/run/mysqld 	&& chown -R mysql:mysql /var/lib/mysql /var/run/mysqld 	&& chmod 777 /var/run/mysqld 	&& find /etc/mysql/ -name '*.cnf' -print0 		| xargs -0 grep -lZE '^(bind-address|log)' 		| xargs -rt -0 sed -Ei 's/^(bind-address|log)/#&/' 	&& echo '[mysqld]\nskip-host-cache\nskip-name-resolve' > /etc/mysql/conf.d/docker.cnf
# Wed, 14 Mar 2018 13:46:40 GMT
VOLUME [/var/lib/mysql /var/log/mysql]
# Wed, 14 Mar 2018 13:46:41 GMT
COPY file:ff55c7472da1028b4f65163094878d7e111bf055794e1db6f6adbc876a67481b in /usr/local/bin/ 
# Wed, 14 Mar 2018 13:46:42 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh / # backwards compat
# Wed, 14 Mar 2018 13:46:42 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 14 Mar 2018 13:46:42 GMT
EXPOSE 3306/tcp
# Wed, 14 Mar 2018 13:46:43 GMT
CMD ["mysqld"]
```

-	Layers:
	-	`sha256:f2b6b4884fc8b2f1fcef843f92f7c82c9c149df85ac77e5f0de7a342ae442412`  
		Last Modified: Tue, 13 Mar 2018 22:43:41 GMT  
		Size: 52.6 MB (52608519 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26d8bdca4f3e3d03817be0249f4df6c3ab8e80c95011ca20e25bdfaeca3c3e3c`  
		Last Modified: Wed, 14 Mar 2018 05:46:22 GMT  
		Size: 2.1 KB (2089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d85f27b5d44ae5a3be6e5c3384ba37e551751cb4ff0485d3c098d2c43f06ae5f`  
		Last Modified: Wed, 14 Mar 2018 13:51:22 GMT  
		Size: 1.3 MB (1303026 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c135060cc63e2e6dc288d516eb81da0ee8e1956c94f10ac95b62f6cc00f7bbe7`  
		Last Modified: Wed, 14 Mar 2018 13:51:21 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7c2925e9ebdd42ba8ba72e0d10742bf48a583d4d346504f8d81a051c4faf152e`  
		Last Modified: Wed, 14 Mar 2018 13:51:22 GMT  
		Size: 6.7 MB (6671946 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50fd03d2dee93ab0b4beb55935a4a314de82feb04e8183c13fd964e806190d26`  
		Last Modified: Wed, 14 Mar 2018 13:51:19 GMT  
		Size: 4.7 KB (4679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e78379637ee7213379c78ec628984d8311acc6fdfd957b8798adb9a2cd55ed85`  
		Last Modified: Wed, 14 Mar 2018 13:51:19 GMT  
		Size: 211.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aeb2044f04049d9176ba96680c0a5fed528ad3513468779ce703477218a8f4ac`  
		Last Modified: Wed, 14 Mar 2018 13:51:36 GMT  
		Size: 80.8 MB (80789737 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6010c14a01faa3c1af308ba33bcc96df9db011c3bf496c36dafe3f23190d9a46`  
		Last Modified: Wed, 14 Mar 2018 13:51:19 GMT  
		Size: 2.4 KB (2448 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2446afee4e74b6d5fec2ff6ca8616c472397e9b8a2ba1e67022bfe93f5c392a`  
		Last Modified: Wed, 14 Mar 2018 13:51:19 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

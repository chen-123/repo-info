## `redis:latest`

```console
$ docker pull redis@sha256:26c93c5b06eaa323bb1089500f42b0dd158138772348b865e364127f1d554982
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `redis:latest` - linux; amd64

```console
$ docker pull redis@sha256:edb0f060fdeb089d2e05b7a69b0fb91418eb7d5cfb7b268b2e2f24a31807ae65
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **39.4 MB (39403680 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4760dc956b2ddc9ac1c508936e39b63a22c6f0640ef58c1b10ff73f04e253ffe`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Tue, 13 Mar 2018 21:58:13 GMT
ADD file:080bac9a2cdcc70ad61e50045a26172f0e1acfd3a26360cb86b6e26a3307b2e1 in / 
# Tue, 13 Mar 2018 21:58:13 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 19:07:45 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Wed, 14 Mar 2018 19:07:45 GMT
ENV GOSU_VERSION=1.10
# Wed, 14 Mar 2018 19:08:17 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 14 Mar 2018 19:10:59 GMT
ENV REDIS_VERSION=4.0.8
# Wed, 14 Mar 2018 19:11:00 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Wed, 14 Mar 2018 19:11:00 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Wed, 14 Mar 2018 19:11:48 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Wed, 14 Mar 2018 19:11:48 GMT
RUN mkdir /data && chown redis:redis /data
# Wed, 14 Mar 2018 19:11:49 GMT
VOLUME [/data]
# Wed, 14 Mar 2018 19:11:49 GMT
WORKDIR /data
# Wed, 14 Mar 2018 19:11:49 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Wed, 14 Mar 2018 19:11:50 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 14 Mar 2018 19:11:50 GMT
EXPOSE 6379/tcp
# Wed, 14 Mar 2018 19:11:50 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:b0568b191983bc2844b2fdb48aeefa72452931bfead0a87e0515bfc602ea3b0c`  
		Last Modified: Tue, 13 Mar 2018 22:45:19 GMT  
		Size: 30.1 MB (30122402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6637dc5b29fee45c6536e100b59259a74639fbf8cc42bf9149dc807e36740af5`  
		Last Modified: Wed, 14 Mar 2018 19:13:55 GMT  
		Size: 2.1 KB (2086 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b4314315f15b1cb666256edf2ac07b2a902a6d0622a0bd1120bdab9799d26c3`  
		Last Modified: Wed, 14 Mar 2018 19:13:55 GMT  
		Size: 981.7 KB (981728 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67b22db27e5144c14efdf55d9cef9c3dadffb43593790ec99663fb1b783dbb6b`  
		Last Modified: Wed, 14 Mar 2018 19:15:50 GMT  
		Size: 8.3 MB (8296963 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:350dbcc918198b2a8b0bcbd73fc376d588f6d16bdebd5f1363cf227e0a52a155`  
		Last Modified: Wed, 14 Mar 2018 19:15:49 GMT  
		Size: 98.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eee5ee716895dcaef7f476edb78073584fed9bddc7682d4df8b9e40c3b24f44b`  
		Last Modified: Wed, 14 Mar 2018 19:15:49 GMT  
		Size: 403.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; arm variant v5

```console
$ docker pull redis@sha256:5ea3638914d1bd4bf6b00bae2a2c8b2c7f4f1e2b5fee722afd6a3e87bfea0521
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **37.6 MB (37599500 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b09a87c5ba768c8ac5bc8277803efb009fbbcc859e03e8f0850adfab578eff41`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Wed, 14 Mar 2018 19:56:16 GMT
ADD file:ad47a4b810086b191c8c574897e3b299d645a336566cb3c716b17f3e35fbf87d in / 
# Wed, 14 Mar 2018 19:56:16 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 23:40:32 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Wed, 14 Mar 2018 23:40:32 GMT
ENV GOSU_VERSION=1.10
# Wed, 14 Mar 2018 23:41:18 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 14 Mar 2018 23:42:47 GMT
ENV REDIS_VERSION=4.0.8
# Wed, 14 Mar 2018 23:42:47 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Wed, 14 Mar 2018 23:42:48 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Wed, 14 Mar 2018 23:43:48 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Wed, 14 Mar 2018 23:43:49 GMT
RUN mkdir /data && chown redis:redis /data
# Wed, 14 Mar 2018 23:43:49 GMT
VOLUME [/data]
# Wed, 14 Mar 2018 23:43:50 GMT
WORKDIR /data
# Wed, 14 Mar 2018 23:43:51 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Wed, 14 Mar 2018 23:43:51 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 14 Mar 2018 23:43:52 GMT
EXPOSE 6379/tcp
# Wed, 14 Mar 2018 23:43:52 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:16d1ef8f2728e0194f717016e924d03797379be56a8cd4bbdea8d983641afa9a`  
		Last Modified: Wed, 14 Mar 2018 20:07:34 GMT  
		Size: 28.4 MB (28430822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:021939e1ca1b03114ed435503435ac1ec0053d661bf03b052fb3fa169d00770d`  
		Last Modified: Wed, 14 Mar 2018 23:44:19 GMT  
		Size: 2.1 KB (2078 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:48100a2eb28a0c0f8e9e6b6e2277fc9e0f6f17da0981e3be4cf445453e90d6eb`  
		Last Modified: Wed, 14 Mar 2018 23:44:20 GMT  
		Size: 971.3 KB (971279 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab61074231a085d787b5c50b73b1c6d51f8fd725163cd4a6fb6e96e9b65d85b6`  
		Last Modified: Wed, 14 Mar 2018 23:44:55 GMT  
		Size: 8.2 MB (8194785 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d5c2b2115d97cc0c03ba0f55c82103fad5822bc26d4724847193431d93b0558`  
		Last Modified: Wed, 14 Mar 2018 23:44:52 GMT  
		Size: 134.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eb2dc1b253281510e35922e55fd046a41d5c46a8ee7598ffdfe2ddbf592621ae`  
		Last Modified: Wed, 14 Mar 2018 23:44:52 GMT  
		Size: 402.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; arm variant v7

```console
$ docker pull redis@sha256:dbd7c144ca17371b72c88a6c5675429be9e272c9024b4b2da6d0a04c453c8309
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **35.2 MB (35184926 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7e41a5db264b5745d986f22bb8b792b2314b8acd74b1a2b895001b61c342a55e`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Wed, 14 Mar 2018 12:27:28 GMT
ADD file:901c5a711f269a7dd8f11eff27131cd2f6d2aee98d68f1e19b4ed954798e5d3f in / 
# Wed, 14 Mar 2018 12:27:29 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 15:44:10 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Wed, 14 Mar 2018 15:44:19 GMT
ENV GOSU_VERSION=1.10
# Wed, 14 Mar 2018 15:45:20 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 14 Mar 2018 15:47:03 GMT
ENV REDIS_VERSION=4.0.8
# Wed, 14 Mar 2018 15:47:03 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Wed, 14 Mar 2018 15:47:04 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Wed, 14 Mar 2018 15:48:01 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Wed, 14 Mar 2018 15:48:02 GMT
RUN mkdir /data && chown redis:redis /data
# Wed, 14 Mar 2018 15:48:02 GMT
VOLUME [/data]
# Wed, 14 Mar 2018 15:48:03 GMT
WORKDIR /data
# Wed, 14 Mar 2018 15:48:03 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Wed, 14 Mar 2018 15:48:04 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 14 Mar 2018 15:48:04 GMT
EXPOSE 6379/tcp
# Wed, 14 Mar 2018 15:48:04 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:b8c016a755ce56e2fbb5a9f179c7bde3f0742c21b2727356a1658fc7d973f46a`  
		Last Modified: Wed, 14 Mar 2018 12:39:21 GMT  
		Size: 26.3 MB (26290283 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b2daa0616e76420cd00e153994139c08a33c1d399f3debb98ea27f15ecb8c84`  
		Last Modified: Wed, 14 Mar 2018 15:48:31 GMT  
		Size: 2.1 KB (2075 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c943f731432d73833cfa4d22e135075012e0ff4680d54710ace42c3876f9f1e0`  
		Last Modified: Wed, 14 Mar 2018 15:48:31 GMT  
		Size: 956.1 KB (956111 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:22e5f8761f00c2c1d0733c392cdcba424635a781922d51d2ac1024d44834ed58`  
		Last Modified: Wed, 14 Mar 2018 15:49:23 GMT  
		Size: 7.9 MB (7935921 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a99c0326cc70901812b6773fb245e7312818386b46287aed69acfbf6f49d3419`  
		Last Modified: Wed, 14 Mar 2018 15:49:20 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8c3bda2a449e5a6f3ceb88e11c6d43e2946de19770164635a75431b57a49b9e`  
		Last Modified: Wed, 14 Mar 2018 15:49:20 GMT  
		Size: 403.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; arm64 variant v8

```console
$ docker pull redis@sha256:17ece7562e8e774485672c04a08daa0d517a2fc7aa20459bec0fd4e3d70fcc63
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **36.9 MB (36884586 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3096a114350fdd1db5670d83e5eb797a260ba6d8978d224f8d8e432b1f7efc2a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Wed, 14 Mar 2018 17:25:26 GMT
ADD file:0012468f66c7e5b0efd7217a1f29f5044d4dce5a19dcd39786aa7573bc927763 in / 
# Wed, 14 Mar 2018 17:25:26 GMT
CMD ["bash"]
# Thu, 15 Mar 2018 01:00:37 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Thu, 15 Mar 2018 01:00:37 GMT
ENV GOSU_VERSION=1.10
# Thu, 15 Mar 2018 01:01:35 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Thu, 15 Mar 2018 01:04:10 GMT
ENV REDIS_VERSION=4.0.8
# Thu, 15 Mar 2018 01:04:11 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Thu, 15 Mar 2018 01:04:12 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Thu, 15 Mar 2018 01:10:18 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Thu, 15 Mar 2018 01:10:21 GMT
RUN mkdir /data && chown redis:redis /data
# Thu, 15 Mar 2018 01:10:22 GMT
VOLUME [/data]
# Thu, 15 Mar 2018 01:10:24 GMT
WORKDIR /data
# Thu, 15 Mar 2018 01:10:25 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Thu, 15 Mar 2018 01:10:26 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 15 Mar 2018 01:10:28 GMT
EXPOSE 6379/tcp
# Thu, 15 Mar 2018 01:10:29 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:784b6f32f75d9222c618727f66027b44ffa35120fc128790dfce4d1070befc90`  
		Last Modified: Wed, 14 Mar 2018 17:39:37 GMT  
		Size: 27.5 MB (27488177 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0d3475bc4704a0cf864207d5cc8c81043c7bf5fb4a138fbad39c3ec3ebbc1fa`  
		Last Modified: Thu, 15 Mar 2018 01:11:02 GMT  
		Size: 2.1 KB (2103 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6aee833ba6520662ec17502d34841bade40071486c5fdf7c4098a666a0dfddcb`  
		Last Modified: Thu, 15 Mar 2018 01:11:00 GMT  
		Size: 948.7 KB (948651 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:113987a0d82c2085a6ebc301687dcf69eb1efe4f95371f32d67c256e90e69a7b`  
		Last Modified: Thu, 15 Mar 2018 01:12:01 GMT  
		Size: 8.4 MB (8445154 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5336787041eabdee3ec4642454b2fe66deccfeafc641fc8579e554652ac0d98`  
		Last Modified: Thu, 15 Mar 2018 01:11:57 GMT  
		Size: 98.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4de7d6fe7c5f612bdf6c4f5ce0165aa683b959b8396b9ba15ce67482cbe9e9a5`  
		Last Modified: Thu, 15 Mar 2018 01:11:57 GMT  
		Size: 403.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; 386

```console
$ docker pull redis@sha256:4b849e84067c4b21088b2cad86db671d65499e479a6b295ac181c7888514e9ea
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **39.2 MB (39191934 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4e54c9a71a10799bcb15eed48ee03690b939a0a3d5fb1762b3d6fdaf68d66cd1`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Thu, 15 Feb 2018 15:10:21 GMT
ADD file:d01127592c252b8d04a3bc643ddd1053a3e9cd036c81aa31b53bf3f51b542f6a in / 
# Thu, 15 Feb 2018 15:10:21 GMT
CMD ["bash"]
# Wed, 21 Feb 2018 13:46:10 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Wed, 21 Feb 2018 13:46:10 GMT
ENV GOSU_VERSION=1.10
# Wed, 21 Feb 2018 13:47:02 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 21 Feb 2018 14:00:50 GMT
ENV REDIS_VERSION=4.0.8
# Wed, 21 Feb 2018 14:00:50 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Wed, 21 Feb 2018 14:00:50 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Wed, 21 Feb 2018 14:02:03 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Wed, 21 Feb 2018 14:02:03 GMT
RUN mkdir /data && chown redis:redis /data
# Wed, 21 Feb 2018 14:02:04 GMT
VOLUME [/data]
# Wed, 21 Feb 2018 14:02:04 GMT
WORKDIR /data
# Wed, 21 Feb 2018 14:02:05 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Wed, 21 Feb 2018 14:02:05 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 21 Feb 2018 14:02:05 GMT
EXPOSE 6379/tcp
# Wed, 21 Feb 2018 14:02:06 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:2c3a67c6c38b2cc7ef92c7d27dfe86398e5a7297b5b0e03d825a82312b60bf9a`  
		Last Modified: Thu, 15 Feb 2018 00:53:43 GMT  
		Size: 30.3 MB (30273198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b459ace55b14953bf5a256c637c483c8dcda03fda090002dd34450c3c52a6893`  
		Last Modified: Wed, 21 Feb 2018 14:02:34 GMT  
		Size: 2.1 KB (2081 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fa3eeadbe98c7e01ab0007a73e259c0744cde1d67e4e76ce9e47e620ebd5172`  
		Last Modified: Wed, 21 Feb 2018 14:02:33 GMT  
		Size: 960.8 KB (960808 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d6fef721fbf7f005a3be906f4390fd4dcf7c4ece56d9fc4f41216ff43cabf5b0`  
		Last Modified: Wed, 21 Feb 2018 14:09:22 GMT  
		Size: 8.0 MB (7955347 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e56e230ec65eef596768d5eb2205eac56f0460c021422995a7eefcf4201c9efd`  
		Last Modified: Wed, 21 Feb 2018 14:09:20 GMT  
		Size: 98.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bf21c33eb326612aef6e45877202e74da8e29ca339a49992bb920c90abb2ab9`  
		Last Modified: Wed, 21 Feb 2018 14:09:20 GMT  
		Size: 402.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; ppc64le

```console
$ docker pull redis@sha256:bb75a8cad0c8d60267b27d66ee82fd68e6a6741b31270dae89daaabf679a9d40
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **38.9 MB (38923146 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dc439fb87aa91a26fe1fd0b5a1e84cd2a4c6060fa6d158165394cd4fc2b665d0`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Wed, 14 Mar 2018 00:32:43 GMT
ADD file:27ae8e2821fa9503c72fac99c983a370df91d52d7a5b3423149597f1e7809a7a in / 
# Wed, 14 Mar 2018 00:32:44 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 05:35:28 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Wed, 14 Mar 2018 05:35:30 GMT
ENV GOSU_VERSION=1.10
# Wed, 14 Mar 2018 05:37:58 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 14 Mar 2018 05:43:10 GMT
ENV REDIS_VERSION=4.0.8
# Wed, 14 Mar 2018 05:43:11 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Wed, 14 Mar 2018 05:43:13 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Wed, 14 Mar 2018 05:46:24 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Wed, 14 Mar 2018 05:46:27 GMT
RUN mkdir /data && chown redis:redis /data
# Wed, 14 Mar 2018 05:46:29 GMT
VOLUME [/data]
# Wed, 14 Mar 2018 05:46:30 GMT
WORKDIR /data
# Wed, 14 Mar 2018 05:46:32 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Wed, 14 Mar 2018 05:46:34 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 14 Mar 2018 05:46:35 GMT
EXPOSE 6379/tcp
# Wed, 14 Mar 2018 05:46:37 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:5853f0e07e55a691985bbc1b5abe444cd0a1293cf6b5356cbc6b27b3cbd790ef`  
		Last Modified: Wed, 14 Mar 2018 00:39:27 GMT  
		Size: 29.3 MB (29311797 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9037176dd765016b2062b3704cf1a0ce37eb5be70e816144f6ef15aee65c5f5b`  
		Last Modified: Wed, 14 Mar 2018 05:48:01 GMT  
		Size: 2.1 KB (2097 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0ece0c0b3e24e0e490a1d49528df343815d2f5e9f01c20e7c496b956ac9291f0`  
		Last Modified: Wed, 14 Mar 2018 05:48:01 GMT  
		Size: 950.7 KB (950652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:deb374bcf0463877de765e0723f89325992ea3ab88ba89d42f18a55212c88677`  
		Last Modified: Wed, 14 Mar 2018 05:48:50 GMT  
		Size: 8.7 MB (8658063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:82953e28faa0e3b9afcba1d9adc7b1041d7c1dab8539e06e2f5cd20f1a3eedeb`  
		Last Modified: Wed, 14 Mar 2018 05:48:46 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9047b7474f697425407432deff8eee6001543e87bf7be34cfd6af3ce3afcb48`  
		Last Modified: Wed, 14 Mar 2018 05:48:46 GMT  
		Size: 404.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `redis:latest` - linux; s390x

```console
$ docker pull redis@sha256:7de460f06fc379abe7a19b41e6005cf41fd42885254acfe5698a00855606e95e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **40.2 MB (40205828 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5a14317551fc08d57ed7c2fe1ceb0e02b3dd5a9e99cd1a2a7508e239f752e012`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["redis-server"]`

```dockerfile
# Wed, 14 Mar 2018 05:22:12 GMT
ADD file:5cd4239ce601f059eb8656abcae1c4827d7d75823a0e5e1a60bb2704635bde19 in / 
# Wed, 14 Mar 2018 05:22:12 GMT
CMD ["bash"]
# Fri, 16 Mar 2018 05:24:30 GMT
RUN groupadd -r redis && useradd -r -g redis redis
# Fri, 16 Mar 2018 05:24:30 GMT
ENV GOSU_VERSION=1.10
# Fri, 16 Mar 2018 05:24:49 GMT
RUN set -ex; 		fetchDeps='ca-certificates wget'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')"; 	wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch"; 	wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$dpkgArch.asc"; 	export GNUPGHOME="$(mktemp -d)"; 	gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4; 	gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu; 	rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc; 	chmod +x /usr/local/bin/gosu; 	gosu nobody true; 		apt-get purge -y --auto-remove $fetchDeps
# Fri, 16 Mar 2018 05:25:30 GMT
ENV REDIS_VERSION=4.0.8
# Fri, 16 Mar 2018 05:25:30 GMT
ENV REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz
# Fri, 16 Mar 2018 05:25:30 GMT
ENV REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad
# Fri, 16 Mar 2018 05:26:02 GMT
RUN set -ex; 		buildDeps=' 		wget 				gcc 		libc6-dev 		make 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O redis.tar.gz "$REDIS_DOWNLOAD_URL"; 	echo "$REDIS_DOWNLOAD_SHA *redis.tar.gz" | sha256sum -c -; 	mkdir -p /usr/src/redis; 	tar -xzf redis.tar.gz -C /usr/src/redis --strip-components=1; 	rm redis.tar.gz; 		grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 1$' /usr/src/redis/src/server.h; 	sed -ri 's!^(#define CONFIG_DEFAULT_PROTECTED_MODE) 1$!\1 0!' /usr/src/redis/src/server.h; 	grep -q '^#define CONFIG_DEFAULT_PROTECTED_MODE 0$' /usr/src/redis/src/server.h; 		make -C /usr/src/redis -j "$(nproc)"; 	make -C /usr/src/redis install; 		rm -r /usr/src/redis; 		apt-get purge -y --auto-remove $buildDeps
# Fri, 16 Mar 2018 05:26:02 GMT
RUN mkdir /data && chown redis:redis /data
# Fri, 16 Mar 2018 05:26:02 GMT
VOLUME [/data]
# Fri, 16 Mar 2018 05:26:03 GMT
WORKDIR /data
# Fri, 16 Mar 2018 05:26:03 GMT
COPY file:9c29fbe8374a97f9c2d953c9c8b7224554607eeb7a610a930844f2bec678265c in /usr/local/bin/ 
# Fri, 16 Mar 2018 05:26:03 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 16 Mar 2018 05:26:03 GMT
EXPOSE 6379/tcp
# Fri, 16 Mar 2018 05:26:03 GMT
CMD ["redis-server"]
```

-	Layers:
	-	`sha256:73a91a9f561cad48038a81f8d9c37a90e39c3d0c806aaedb15f2f77092870ce4`  
		Last Modified: Wed, 14 Mar 2018 05:26:42 GMT  
		Size: 30.3 MB (30301960 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8c4a0627308986c079aac5fcd4443370e25d46e7d2121a8ec46f5e93f70893e`  
		Last Modified: Fri, 16 Mar 2018 05:26:21 GMT  
		Size: 2.1 KB (2089 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2379099d7972abdfc0ee1b53049fd97e8fd9dd0132e05f544d08a18026289c9d`  
		Last Modified: Fri, 16 Mar 2018 05:26:22 GMT  
		Size: 966.9 KB (966876 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:35ca26f6d8ae6bee60d3339d78bf99ba973b6f881ce05aff2142827818d4cdcc`  
		Last Modified: Fri, 16 Mar 2018 05:26:39 GMT  
		Size: 8.9 MB (8934402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5cea9e6dd239f778a1f25f84b447dcb762dbc8fb00ecc65232d0f2167039c820`  
		Last Modified: Fri, 16 Mar 2018 05:26:37 GMT  
		Size: 99.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f366e1ad902201ece15584c146093722f7bc9f34412a352062bd70a512656297`  
		Last Modified: Fri, 16 Mar 2018 05:26:37 GMT  
		Size: 402.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

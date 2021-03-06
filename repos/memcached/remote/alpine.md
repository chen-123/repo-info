## `memcached:alpine`

```console
$ docker pull memcached@sha256:6d7bde6a89491fb133d672a5834954749f8ddd31ff97653b2494f86a4189f10a
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v6
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `memcached:alpine` - linux; amd64

```console
$ docker pull memcached@sha256:d2ff27dc74aa1458beec9009658c01fc64d05afcb1cd73ff931d1fa74cefac94
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.8 MB (3804778 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5c28baaba1e0a517ce3a8576d0755f651b77764142d19eac55500eddeadefda9`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["memcached"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Fri, 19 Jan 2018 01:45:05 GMT
RUN adduser -D memcache
# Sat, 03 Mar 2018 01:15:56 GMT
ENV MEMCACHED_VERSION=1.5.6
# Sat, 03 Mar 2018 01:15:56 GMT
ENV MEMCACHED_SHA1=ca35929e74b132c2495a6957cfdc80556337fb90
# Sat, 03 Mar 2018 01:19:16 GMT
RUN set -x 		&& apk add --no-cache --virtual .build-deps 		ca-certificates 		coreutils 		cyrus-sasl-dev 		dpkg-dev dpkg 		gcc 		libc-dev 		libevent-dev 		libressl 		linux-headers 		make 		perl 		perl-utils 		tar 		&& wget -O memcached.tar.gz "https://memcached.org/files/memcached-$MEMCACHED_VERSION.tar.gz" 	&& echo "$MEMCACHED_SHA1  memcached.tar.gz" | sha1sum -c - 	&& mkdir -p /usr/src/memcached 	&& tar -xzf memcached.tar.gz -C /usr/src/memcached --strip-components=1 	&& rm memcached.tar.gz 		&& cd /usr/src/memcached 		&& ./configure 		--build="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 		--enable-sasl 	&& make -j "$(nproc)" 		&& make test 	&& make install 		&& cd / && rm -rf /usr/src/memcached 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --virtual .memcached-rundeps $runDeps 	&& apk del .build-deps 		&& memcached -V
# Sat, 03 Mar 2018 01:19:16 GMT
COPY file:621e178b267679ef7140edd23c3ad9e717ed767ed55322a4e198798311bc1d36 in /usr/local/bin/ 
# Sat, 03 Mar 2018 01:19:17 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Sat, 03 Mar 2018 01:19:17 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 03 Mar 2018 01:19:17 GMT
USER [memcache]
# Sat, 03 Mar 2018 01:19:18 GMT
EXPOSE 11211/tcp
# Sat, 03 Mar 2018 01:19:18 GMT
CMD ["memcached"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b2dd15093416a9c9620ddfa18507f40ab70c5f3fd5b338e34990af372932a3d`  
		Last Modified: Fri, 19 Jan 2018 01:55:02 GMT  
		Size: 1.2 KB (1244 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5abf9f6aeed3d9122eb2ffffd18aa0a310faa85307a0f3bb5c3eaeec900d6e6d`  
		Last Modified: Sat, 03 Mar 2018 01:20:42 GMT  
		Size: 1.7 MB (1737592 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:762ceae99e707e86ae027c21bdb49885a1b2f34b53bc07be7f7837788d609df6`  
		Last Modified: Sat, 03 Mar 2018 01:20:41 GMT  
		Size: 284.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62fd19b03430b6f63d13224c58e658028f25dac7f8090b1a30e499e0def6ddb6`  
		Last Modified: Sat, 03 Mar 2018 01:20:41 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `memcached:alpine` - linux; arm variant v6

```console
$ docker pull memcached@sha256:75b50344b2414146c15c760b42785c6c481801150788c17f59de506b944cf02e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.7 MB (3739426 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:276d0c2c4ba1586c2c76f0c813e6227a6ef60924f132799b64aacd4113495423`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["memcached"]`

```dockerfile
# Mon, 26 Feb 2018 23:48:41 GMT
ADD file:966d84204dc4860e9281f7c93c792137c88298edb284f267def4b38a11b79a1f in / 
# Mon, 26 Feb 2018 23:48:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Mon, 26 Feb 2018 23:48:42 GMT
CMD ["/bin/sh"]
# Thu, 01 Mar 2018 22:28:21 GMT
RUN adduser -D memcache
# Fri, 02 Mar 2018 22:28:21 GMT
ENV MEMCACHED_VERSION=1.5.6
# Fri, 02 Mar 2018 22:28:21 GMT
ENV MEMCACHED_SHA1=ca35929e74b132c2495a6957cfdc80556337fb90
# Fri, 02 Mar 2018 22:48:18 GMT
RUN set -x 		&& apk add --no-cache --virtual .build-deps 		ca-certificates 		coreutils 		cyrus-sasl-dev 		dpkg-dev dpkg 		gcc 		libc-dev 		libevent-dev 		libressl 		linux-headers 		make 		perl 		perl-utils 		tar 		&& wget -O memcached.tar.gz "https://memcached.org/files/memcached-$MEMCACHED_VERSION.tar.gz" 	&& echo "$MEMCACHED_SHA1  memcached.tar.gz" | sha1sum -c - 	&& mkdir -p /usr/src/memcached 	&& tar -xzf memcached.tar.gz -C /usr/src/memcached --strip-components=1 	&& rm memcached.tar.gz 		&& cd /usr/src/memcached 		&& ./configure 		--build="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 		--enable-sasl 	&& make -j "$(nproc)" 		&& make test 	&& make install 		&& cd / && rm -rf /usr/src/memcached 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --virtual .memcached-rundeps $runDeps 	&& apk del .build-deps 		&& memcached -V
# Fri, 02 Mar 2018 22:48:21 GMT
COPY file:621e178b267679ef7140edd23c3ad9e717ed767ed55322a4e198798311bc1d36 in /usr/local/bin/ 
# Fri, 02 Mar 2018 22:48:25 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Fri, 02 Mar 2018 22:48:26 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 02 Mar 2018 22:48:26 GMT
USER [memcache]
# Fri, 02 Mar 2018 22:48:27 GMT
EXPOSE 11211/tcp
# Fri, 02 Mar 2018 22:48:28 GMT
CMD ["memcached"]
```

-	Layers:
	-	`sha256:95d54dd4bdadebb53f9b91b25aa7dc5fcb83c534eb1d196eb0814aa1e16f3db2`  
		Last Modified: Fri, 01 Dec 2017 18:41:57 GMT  
		Size: 2.0 MB (2038298 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5993b3593c77413be85d318297ad8313b945069768a7e454d487fd47fa4b4343`  
		Last Modified: Mon, 26 Feb 2018 23:49:26 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9c991fcbb1642e4c203f3ec02fe1bd716035895d814f5639c7286cb13f84009`  
		Last Modified: Fri, 02 Mar 2018 22:48:37 GMT  
		Size: 1.3 KB (1276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:182283613398bb7b44902147ab19fdd23300ff6c9fb843dbf0815ab4bc4aa338`  
		Last Modified: Fri, 02 Mar 2018 22:48:38 GMT  
		Size: 1.7 MB (1699270 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4cb2817051c02569e759029f302f3309eb8fce988d9b51fd49e04607a6e3e833`  
		Last Modified: Fri, 02 Mar 2018 22:48:36 GMT  
		Size: 286.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:992f038c1080437c8d4b4b712847febf237666834ed73208291ba94a2b666fdf`  
		Last Modified: Fri, 02 Mar 2018 22:48:37 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `memcached:alpine` - linux; arm64 variant v8

```console
$ docker pull memcached@sha256:583f5d718a575221d4f349bcfb8955fece51d6e7d04ebb6c27c9f61b2e0c1811
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.7 MB (3673574 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bc51673cdd7b11af568e7d7e21d8e72f5945c223bfc625a7122cd0ae58e04ea6`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["memcached"]`

```dockerfile
# Fri, 01 Dec 2017 18:42:42 GMT
ADD file:a6ef3cbbb1c0e5dfc6c3e41d70fd93e548594d9cb42c067e52df46d418c10a79 in / 
# Fri, 01 Dec 2017 18:42:42 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:42:43 GMT
CMD ["/bin/sh"]
# Fri, 19 Jan 2018 04:16:39 GMT
RUN adduser -D memcache
# Sat, 03 Mar 2018 03:53:36 GMT
ENV MEMCACHED_VERSION=1.5.6
# Sat, 03 Mar 2018 03:53:37 GMT
ENV MEMCACHED_SHA1=ca35929e74b132c2495a6957cfdc80556337fb90
# Sat, 03 Mar 2018 03:57:51 GMT
RUN set -x 		&& apk add --no-cache --virtual .build-deps 		ca-certificates 		coreutils 		cyrus-sasl-dev 		dpkg-dev dpkg 		gcc 		libc-dev 		libevent-dev 		libressl 		linux-headers 		make 		perl 		perl-utils 		tar 		&& wget -O memcached.tar.gz "https://memcached.org/files/memcached-$MEMCACHED_VERSION.tar.gz" 	&& echo "$MEMCACHED_SHA1  memcached.tar.gz" | sha1sum -c - 	&& mkdir -p /usr/src/memcached 	&& tar -xzf memcached.tar.gz -C /usr/src/memcached --strip-components=1 	&& rm memcached.tar.gz 		&& cd /usr/src/memcached 		&& ./configure 		--build="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 		--enable-sasl 	&& make -j "$(nproc)" 		&& make test 	&& make install 		&& cd / && rm -rf /usr/src/memcached 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --virtual .memcached-rundeps $runDeps 	&& apk del .build-deps 		&& memcached -V
# Sat, 03 Mar 2018 03:57:51 GMT
COPY file:621e178b267679ef7140edd23c3ad9e717ed767ed55322a4e198798311bc1d36 in /usr/local/bin/ 
# Sat, 03 Mar 2018 03:57:53 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Sat, 03 Mar 2018 03:57:55 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 03 Mar 2018 03:57:55 GMT
USER [memcache]
# Sat, 03 Mar 2018 03:57:56 GMT
EXPOSE 11211/tcp
# Sat, 03 Mar 2018 03:57:57 GMT
CMD ["memcached"]
```

-	Layers:
	-	`sha256:b78042c299ad99d1e646b18762d4bc22a84c4f88e5bb491ea6293a10f53ddf79`  
		Last Modified: Fri, 01 Dec 2017 18:43:42 GMT  
		Size: 2.0 MB (1988857 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6fd45b97b6c2a3ac869ae5c99e087e97bc29714b165180e06f0c9116f400f2dd`  
		Last Modified: Fri, 01 Dec 2017 18:43:41 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:151c071afab1ab7b08ef0dbe8e2ea271716a48481c9f03bf22500bddd9538556`  
		Last Modified: Fri, 19 Jan 2018 04:21:20 GMT  
		Size: 1.2 KB (1246 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f575f998de0f2683e907d564faac071edadb5beef942846d7765e226e14d277f`  
		Last Modified: Sat, 03 Mar 2018 03:59:35 GMT  
		Size: 1.7 MB (1682895 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:70cd30d7b6df753ee65c8a282ef95d3957e845dbac820c3fdeed8bfd4a05fe39`  
		Last Modified: Sat, 03 Mar 2018 03:59:34 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7fe94f88cdeb7c594d4ccfcf18d35938a8fbaa2709aa263a065039b784b70039`  
		Last Modified: Sat, 03 Mar 2018 03:59:34 GMT  
		Size: 118.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `memcached:alpine` - linux; 386

```console
$ docker pull memcached@sha256:5cf8ff8057b10feac0d8647e78b2b2e5dcab321a3150f2336b89ddfc30ed6694
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **4.0 MB (3966868 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ab4262fd18e9bcee78bac5cf3ca18ada9f8d8f53a9150acf4594bbff6f32b68f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["memcached"]`

```dockerfile
# Fri, 01 Dec 2017 18:46:48 GMT
ADD file:614c07101e677db9a4118a71c852a2be45a337d94c5bedfb48ae8c4cad21d625 in / 
# Fri, 01 Dec 2017 18:46:48 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:46:48 GMT
CMD ["/bin/sh"]
# Fri, 19 Jan 2018 21:15:00 GMT
RUN adduser -D memcache
# Sat, 03 Mar 2018 20:50:06 GMT
ENV MEMCACHED_VERSION=1.5.6
# Sat, 03 Mar 2018 20:50:06 GMT
ENV MEMCACHED_SHA1=ca35929e74b132c2495a6957cfdc80556337fb90
# Sat, 03 Mar 2018 20:53:39 GMT
RUN set -x 		&& apk add --no-cache --virtual .build-deps 		ca-certificates 		coreutils 		cyrus-sasl-dev 		dpkg-dev dpkg 		gcc 		libc-dev 		libevent-dev 		libressl 		linux-headers 		make 		perl 		perl-utils 		tar 		&& wget -O memcached.tar.gz "https://memcached.org/files/memcached-$MEMCACHED_VERSION.tar.gz" 	&& echo "$MEMCACHED_SHA1  memcached.tar.gz" | sha1sum -c - 	&& mkdir -p /usr/src/memcached 	&& tar -xzf memcached.tar.gz -C /usr/src/memcached --strip-components=1 	&& rm memcached.tar.gz 		&& cd /usr/src/memcached 		&& ./configure 		--build="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 		--enable-sasl 	&& make -j "$(nproc)" 		&& make test 	&& make install 		&& cd / && rm -rf /usr/src/memcached 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --virtual .memcached-rundeps $runDeps 	&& apk del .build-deps 		&& memcached -V
# Sat, 03 Mar 2018 20:53:39 GMT
COPY file:621e178b267679ef7140edd23c3ad9e717ed767ed55322a4e198798311bc1d36 in /usr/local/bin/ 
# Sat, 03 Mar 2018 20:53:40 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Sat, 03 Mar 2018 20:53:41 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 03 Mar 2018 20:53:41 GMT
USER [memcache]
# Sat, 03 Mar 2018 20:53:41 GMT
EXPOSE 11211/tcp
# Sat, 03 Mar 2018 20:53:42 GMT
CMD ["memcached"]
```

-	Layers:
	-	`sha256:381c1d4107a4401d75b916e6dc4331efddc01adac41f49eeaa711ab898606a1a`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 2.1 MB (2126217 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a29cce73050e1b58c218a1c94cd8c9f719d38530500ab97333eac5fdaf385dbc`  
		Last Modified: Fri, 01 Dec 2017 18:47:24 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e764ac324ae5f248d64a1c76d7f7962178040706dce50136076b67b727edbd7`  
		Last Modified: Fri, 19 Jan 2018 21:27:28 GMT  
		Size: 1.2 KB (1250 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2483517fae8a81334344b01f6ddb8235b9cf8a884c36b4585edf87a67f382a00`  
		Last Modified: Sat, 03 Mar 2018 21:08:54 GMT  
		Size: 1.8 MB (1838822 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7379449dfb3dbfd6503de4d96291dbf4ad1cabc7755473645ced1bb8359bb2da`  
		Last Modified: Sat, 03 Mar 2018 21:08:54 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f685098ab816a0850981a39b20941f40cd2f12475b4d537be67267c8cc93ef9`  
		Last Modified: Sat, 03 Mar 2018 21:08:54 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `memcached:alpine` - linux; ppc64le

```console
$ docker pull memcached@sha256:0f9b95ac87f74594d15da00ffc12cbf3b73fc2afe1162288384f439a8a2de586
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.8 MB (3826884 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e77853c0930653ca46e8141b9890232a85e28f70062a10aa435c00b3d7ede760`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["memcached"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:54 GMT
ADD file:791370adae5cfa8feec749693f5a995a01f58f0462b7aa675fc5bf991e1282b5 in / 
# Fri, 01 Dec 2017 18:41:55 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:57 GMT
CMD ["/bin/sh"]
# Fri, 19 Jan 2018 01:33:29 GMT
RUN adduser -D memcache
# Sat, 03 Mar 2018 01:39:33 GMT
ENV MEMCACHED_VERSION=1.5.6
# Sat, 03 Mar 2018 01:39:34 GMT
ENV MEMCACHED_SHA1=ca35929e74b132c2495a6957cfdc80556337fb90
# Sat, 03 Mar 2018 01:43:25 GMT
RUN set -x 		&& apk add --no-cache --virtual .build-deps 		ca-certificates 		coreutils 		cyrus-sasl-dev 		dpkg-dev dpkg 		gcc 		libc-dev 		libevent-dev 		libressl 		linux-headers 		make 		perl 		perl-utils 		tar 		&& wget -O memcached.tar.gz "https://memcached.org/files/memcached-$MEMCACHED_VERSION.tar.gz" 	&& echo "$MEMCACHED_SHA1  memcached.tar.gz" | sha1sum -c - 	&& mkdir -p /usr/src/memcached 	&& tar -xzf memcached.tar.gz -C /usr/src/memcached --strip-components=1 	&& rm memcached.tar.gz 		&& cd /usr/src/memcached 		&& ./configure 		--build="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 		--enable-sasl 	&& make -j "$(nproc)" 		&& make test 	&& make install 		&& cd / && rm -rf /usr/src/memcached 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --virtual .memcached-rundeps $runDeps 	&& apk del .build-deps 		&& memcached -V
# Sat, 03 Mar 2018 01:43:26 GMT
COPY file:621e178b267679ef7140edd23c3ad9e717ed767ed55322a4e198798311bc1d36 in /usr/local/bin/ 
# Sat, 03 Mar 2018 01:43:29 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Sat, 03 Mar 2018 01:43:30 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 03 Mar 2018 01:43:31 GMT
USER [memcache]
# Sat, 03 Mar 2018 01:43:32 GMT
EXPOSE 11211/tcp
# Sat, 03 Mar 2018 01:43:33 GMT
CMD ["memcached"]
```

-	Layers:
	-	`sha256:0da653ea85b50d280ec56ca2eafb7e8b37590630356e043fa9ff162d55732a23`  
		Last Modified: Fri, 01 Dec 2017 18:42:14 GMT  
		Size: 2.1 MB (2081469 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9fd90b777cc38b5b6ca1b2407e647fdc22ef31b57ef98e924e7e0635adffc385`  
		Last Modified: Fri, 01 Dec 2017 18:42:15 GMT  
		Size: 176.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab31b119386a086d3a80f01a107e952063d9f94f3a50fe9a2dabc1b8fdd2b087`  
		Last Modified: Fri, 19 Jan 2018 01:37:46 GMT  
		Size: 1.3 KB (1275 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:59fe5c1b56de66db6542f5b873a01e187871e21d16dcb27429327553ef08ba93`  
		Last Modified: Sat, 03 Mar 2018 01:44:10 GMT  
		Size: 1.7 MB (1743562 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:50c3c452eeb64a8c180ea1d1eb08fcb5b419a9c21d6b8977bb9be99a505bb404`  
		Last Modified: Sat, 03 Mar 2018 01:44:09 GMT  
		Size: 283.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0702d18ace1878277000ed1d9eb374417de037403fd7625c0eeccfbeeea65300`  
		Last Modified: Sat, 03 Mar 2018 01:44:10 GMT  
		Size: 119.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `memcached:alpine` - linux; s390x

```console
$ docker pull memcached@sha256:321f94ca4908569cbd2f3bd7942f63ee841bea1493af22d8635bc2de7db54d6a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.6 MB (3604172 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:706759e438a7de0e05da78f41aea4f5653cd59e4719afa9319e533dc6396ebca`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["memcached"]`

```dockerfile
# Fri, 01 Dec 2017 18:41:57 GMT
ADD file:9c09dfc247c393ab1c6205a4b7857047a3d88e398e8d35aede30f7d613ef1de9 in / 
# Fri, 01 Dec 2017 18:41:58 GMT
COPY file:0f1d36dd7d8d53613b275660a88c5bf9b608ea8aa73a8054cb8bdbd73fd971ac in /etc/localtime 
# Fri, 01 Dec 2017 18:41:58 GMT
CMD ["/bin/sh"]
# Fri, 19 Jan 2018 18:33:29 GMT
RUN adduser -D memcache
# Sat, 03 Mar 2018 18:37:05 GMT
ENV MEMCACHED_VERSION=1.5.6
# Sat, 03 Mar 2018 18:37:05 GMT
ENV MEMCACHED_SHA1=ca35929e74b132c2495a6957cfdc80556337fb90
# Sat, 03 Mar 2018 18:40:23 GMT
RUN set -x 		&& apk add --no-cache --virtual .build-deps 		ca-certificates 		coreutils 		cyrus-sasl-dev 		dpkg-dev dpkg 		gcc 		libc-dev 		libevent-dev 		libressl 		linux-headers 		make 		perl 		perl-utils 		tar 		&& wget -O memcached.tar.gz "https://memcached.org/files/memcached-$MEMCACHED_VERSION.tar.gz" 	&& echo "$MEMCACHED_SHA1  memcached.tar.gz" | sha1sum -c - 	&& mkdir -p /usr/src/memcached 	&& tar -xzf memcached.tar.gz -C /usr/src/memcached --strip-components=1 	&& rm memcached.tar.gz 		&& cd /usr/src/memcached 		&& ./configure 		--build="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 		--enable-sasl 	&& make -j "$(nproc)" 		&& make test 	&& make install 		&& cd / && rm -rf /usr/src/memcached 		&& runDeps="$( 		scanelf --needed --nobanner --format '%n#p' --recursive /usr/local 			| tr ',' '\n' 			| sort -u 			| awk 'system("[ -e /usr/local/lib/" $1 " ]") == 0 { next } { print "so:" $1 }' 	)" 	&& apk add --virtual .memcached-rundeps $runDeps 	&& apk del .build-deps 		&& memcached -V
# Sat, 03 Mar 2018 18:40:23 GMT
COPY file:621e178b267679ef7140edd23c3ad9e717ed767ed55322a4e198798311bc1d36 in /usr/local/bin/ 
# Sat, 03 Mar 2018 18:40:24 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Sat, 03 Mar 2018 18:40:24 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Sat, 03 Mar 2018 18:40:24 GMT
USER [memcache]
# Sat, 03 Mar 2018 18:40:24 GMT
EXPOSE 11211/tcp
# Sat, 03 Mar 2018 18:40:24 GMT
CMD ["memcached"]
```

-	Layers:
	-	`sha256:11e7bc85614a236b32043d147930fd2bc9055af8642fe30e5e56142590572b0e`  
		Last Modified: Fri, 01 Dec 2017 18:42:22 GMT  
		Size: 2.2 MB (2185231 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3f825cbb729285f1fe2a0cd1d4d36897e3fe2191c5ee044ce11a5d301dc64a34`  
		Last Modified: Fri, 01 Dec 2017 18:42:22 GMT  
		Size: 175.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3ee38c4a66157820c6274c579d65ea2b83987e188f25c816a44863a47059c895`  
		Last Modified: Fri, 19 Jan 2018 18:37:09 GMT  
		Size: 1.2 KB (1246 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a3c7f5b513b6034578219122f004609e7fcdcebea4791a44cc1d254008ba960`  
		Last Modified: Sat, 03 Mar 2018 18:41:00 GMT  
		Size: 1.4 MB (1417114 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b36d8e220637b71105206601361a6afb249cce05fd278c0effdd4aa60ba4b549`  
		Last Modified: Sat, 03 Mar 2018 18:40:58 GMT  
		Size: 285.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e558108b24d74270538fdc215b38833e703b75bccca63daf470cc847c403f8b`  
		Last Modified: Sat, 03 Mar 2018 18:40:58 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

<!-- THIS FILE IS GENERATED VIA './update-remote.sh' -->

# Tags of `znc`

-	[`znc:1.6`](#znc16)
-	[`znc:1.6.6`](#znc166)
-	[`znc:1.6.6-slim`](#znc166-slim)
-	[`znc:1.6-slim`](#znc16-slim)
-	[`znc:latest`](#znclatest)
-	[`znc:slim`](#zncslim)

## `znc:1.6`

```console
$ docker pull znc@sha256:e0aaa5027be53c10ed607f0550ea7ebf7ee2335a6e2cea8cc8dfd6aaa6b2515e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `znc:1.6` - linux; amd64

```console
$ docker pull znc@sha256:4513f95681513fca24a6a698d3b6c586ef9f7ecca242b049ea40365283deeaf9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **105.5 MB (105514366 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a7fc05a35e1fe2a941041f982b2ef55ebd8dac50bfa594401362f849f69dba4f`
-	Entrypoint: `["\/entrypoint.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 03:44:56 GMT
ENV GPG_KEY=D5823CACB477191CAC0075555AE420CC0209989E
# Wed, 10 Jan 2018 03:44:57 GMT
ARG CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6
# Wed, 10 Jan 2018 03:44:57 GMT
ARG MAKEFLAGS=
# Tue, 06 Mar 2018 01:32:42 GMT
ENV ZNC_VERSION=1.6.6
# Wed, 07 Mar 2018 08:22:15 GMT
# ARGS: CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6 MAKEFLAGS=
RUN set -x     && adduser -S znc     && addgroup -S znc     && apk add --no-cache --virtual runtime-dependencies         ca-certificates         cyrus-sasl         icu         su-exec         tini         tzdata     && apk add --no-cache --virtual build-dependencies         build-base         curl         cyrus-sasl-dev         gnupg         icu-dev         libressl-dev         perl-dev         python3-dev     && mkdir /znc-src && cd /znc-src     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz" -o znc.tgz     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz.sig" -o znc.tgz.sig     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "${GPG_KEY}"     && gpg --batch --verify znc.tgz.sig znc.tgz     && rm -rf "$GNUPGHOME"     && tar -zxf znc.tgz --strip-components=1     && mkdir build && cd build     && ../configure ${CONFIGUREFLAGS}     && make $MAKEFLAGS     && make install     && apk del build-dependencies     && cd / && rm -rf /znc-src
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:9d7b3114446d239420ea168b9310c1d20e26b75d069079c5742a25823c4c2aab in / 
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:e0192a282adc7f54a8a1ff4594ead3ef35387b9ac6cad11dc37da9ea1b048a13 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:378c136273fef23830ba35f7a8a99554baf86a694f5366f4ba9e9bbabcb8ee6a in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:9c43478daa2a1fccaed5a69ad3c74782d9efa3cd18a66d033f2ddf6956451ba5 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
COPY file:0aff452a445b305c16e9c2c7fb36e9b027100f93ff8f18f4a9342fb94cc44b9c in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
VOLUME [/znc-data]
# Wed, 07 Mar 2018 08:22:18 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Mar 2018 08:25:34 GMT
RUN set -x     && apk add --no-cache         build-base         icu-dev         libressl-dev         perl         python3
# Wed, 07 Mar 2018 08:25:35 GMT
COPY file:d1446fead8db29053b5a4bf7f2af913ddb4d8b1c90f97cc6c099fc74c4322109 in /startup-sequence/ 
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:103251184b1f99b967d69ff5703f1ce65a243b3fbf7bfac07fc332ba920a3dc2`  
		Last Modified: Wed, 07 Mar 2018 08:25:59 GMT  
		Size: 21.8 MB (21826555 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2cff81d055115221819fa260de76558cacb3d62b690323c599002bd40e826ca`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a52e46ee8f1f8130ff7e09d8027b97ef727fd785c98ac19f2f5f2b8268ef85c1`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea96b30d7a8a2f31c50297a97684a574c7ec5eb2b82736ed5a502ba13acb7eeb`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:824687efb5b6b763191b21277fff2756dbfb18faf34c5261c790b8b6ec9230c0`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3235ad9c300eef882002d62630ef4176a9ae2c21d4a75aa384c5b71a50e58b07`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 351.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40a3bfde275a32a63fa7b866c38a75d933cd11b16441532c73e11f4fc16a6909`  
		Last Modified: Wed, 07 Mar 2018 08:27:05 GMT  
		Size: 81.6 MB (81620628 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06cf59fc68dff93a7f6f767850146d5c755386461e45442469ee20eb208ebd3f`  
		Last Modified: Wed, 07 Mar 2018 08:26:52 GMT  
		Size: 332.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `znc:1.6.6`

```console
$ docker pull znc@sha256:e0aaa5027be53c10ed607f0550ea7ebf7ee2335a6e2cea8cc8dfd6aaa6b2515e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `znc:1.6.6` - linux; amd64

```console
$ docker pull znc@sha256:4513f95681513fca24a6a698d3b6c586ef9f7ecca242b049ea40365283deeaf9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **105.5 MB (105514366 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a7fc05a35e1fe2a941041f982b2ef55ebd8dac50bfa594401362f849f69dba4f`
-	Entrypoint: `["\/entrypoint.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 03:44:56 GMT
ENV GPG_KEY=D5823CACB477191CAC0075555AE420CC0209989E
# Wed, 10 Jan 2018 03:44:57 GMT
ARG CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6
# Wed, 10 Jan 2018 03:44:57 GMT
ARG MAKEFLAGS=
# Tue, 06 Mar 2018 01:32:42 GMT
ENV ZNC_VERSION=1.6.6
# Wed, 07 Mar 2018 08:22:15 GMT
# ARGS: CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6 MAKEFLAGS=
RUN set -x     && adduser -S znc     && addgroup -S znc     && apk add --no-cache --virtual runtime-dependencies         ca-certificates         cyrus-sasl         icu         su-exec         tini         tzdata     && apk add --no-cache --virtual build-dependencies         build-base         curl         cyrus-sasl-dev         gnupg         icu-dev         libressl-dev         perl-dev         python3-dev     && mkdir /znc-src && cd /znc-src     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz" -o znc.tgz     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz.sig" -o znc.tgz.sig     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "${GPG_KEY}"     && gpg --batch --verify znc.tgz.sig znc.tgz     && rm -rf "$GNUPGHOME"     && tar -zxf znc.tgz --strip-components=1     && mkdir build && cd build     && ../configure ${CONFIGUREFLAGS}     && make $MAKEFLAGS     && make install     && apk del build-dependencies     && cd / && rm -rf /znc-src
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:9d7b3114446d239420ea168b9310c1d20e26b75d069079c5742a25823c4c2aab in / 
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:e0192a282adc7f54a8a1ff4594ead3ef35387b9ac6cad11dc37da9ea1b048a13 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:378c136273fef23830ba35f7a8a99554baf86a694f5366f4ba9e9bbabcb8ee6a in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:9c43478daa2a1fccaed5a69ad3c74782d9efa3cd18a66d033f2ddf6956451ba5 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
COPY file:0aff452a445b305c16e9c2c7fb36e9b027100f93ff8f18f4a9342fb94cc44b9c in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
VOLUME [/znc-data]
# Wed, 07 Mar 2018 08:22:18 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Mar 2018 08:25:34 GMT
RUN set -x     && apk add --no-cache         build-base         icu-dev         libressl-dev         perl         python3
# Wed, 07 Mar 2018 08:25:35 GMT
COPY file:d1446fead8db29053b5a4bf7f2af913ddb4d8b1c90f97cc6c099fc74c4322109 in /startup-sequence/ 
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:103251184b1f99b967d69ff5703f1ce65a243b3fbf7bfac07fc332ba920a3dc2`  
		Last Modified: Wed, 07 Mar 2018 08:25:59 GMT  
		Size: 21.8 MB (21826555 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2cff81d055115221819fa260de76558cacb3d62b690323c599002bd40e826ca`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a52e46ee8f1f8130ff7e09d8027b97ef727fd785c98ac19f2f5f2b8268ef85c1`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea96b30d7a8a2f31c50297a97684a574c7ec5eb2b82736ed5a502ba13acb7eeb`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:824687efb5b6b763191b21277fff2756dbfb18faf34c5261c790b8b6ec9230c0`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3235ad9c300eef882002d62630ef4176a9ae2c21d4a75aa384c5b71a50e58b07`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 351.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40a3bfde275a32a63fa7b866c38a75d933cd11b16441532c73e11f4fc16a6909`  
		Last Modified: Wed, 07 Mar 2018 08:27:05 GMT  
		Size: 81.6 MB (81620628 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06cf59fc68dff93a7f6f767850146d5c755386461e45442469ee20eb208ebd3f`  
		Last Modified: Wed, 07 Mar 2018 08:26:52 GMT  
		Size: 332.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `znc:1.6.6-slim`

```console
$ docker pull znc@sha256:892fe7ae4e297ca41b0d0ab9680630b96ce75d92515a71ad3bb2222d2a262baf
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `znc:1.6.6-slim` - linux; amd64

```console
$ docker pull znc@sha256:f15635fd193f4946f0ad61257280d1d9c389e3196636abacaf9b92d9499e6268
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **23.9 MB (23893406 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9fa07312a97398530366d2d9535aca2f9cea885c25db98aca6ff30c0f634463e`
-	Entrypoint: `["\/entrypoint.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 03:44:56 GMT
ENV GPG_KEY=D5823CACB477191CAC0075555AE420CC0209989E
# Wed, 10 Jan 2018 03:44:57 GMT
ARG CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6
# Wed, 10 Jan 2018 03:44:57 GMT
ARG MAKEFLAGS=
# Tue, 06 Mar 2018 01:32:42 GMT
ENV ZNC_VERSION=1.6.6
# Wed, 07 Mar 2018 08:22:15 GMT
# ARGS: CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6 MAKEFLAGS=
RUN set -x     && adduser -S znc     && addgroup -S znc     && apk add --no-cache --virtual runtime-dependencies         ca-certificates         cyrus-sasl         icu         su-exec         tini         tzdata     && apk add --no-cache --virtual build-dependencies         build-base         curl         cyrus-sasl-dev         gnupg         icu-dev         libressl-dev         perl-dev         python3-dev     && mkdir /znc-src && cd /znc-src     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz" -o znc.tgz     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz.sig" -o znc.tgz.sig     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "${GPG_KEY}"     && gpg --batch --verify znc.tgz.sig znc.tgz     && rm -rf "$GNUPGHOME"     && tar -zxf znc.tgz --strip-components=1     && mkdir build && cd build     && ../configure ${CONFIGUREFLAGS}     && make $MAKEFLAGS     && make install     && apk del build-dependencies     && cd / && rm -rf /znc-src
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:9d7b3114446d239420ea168b9310c1d20e26b75d069079c5742a25823c4c2aab in / 
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:e0192a282adc7f54a8a1ff4594ead3ef35387b9ac6cad11dc37da9ea1b048a13 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:378c136273fef23830ba35f7a8a99554baf86a694f5366f4ba9e9bbabcb8ee6a in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:9c43478daa2a1fccaed5a69ad3c74782d9efa3cd18a66d033f2ddf6956451ba5 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
COPY file:0aff452a445b305c16e9c2c7fb36e9b027100f93ff8f18f4a9342fb94cc44b9c in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
VOLUME [/znc-data]
# Wed, 07 Mar 2018 08:22:18 GMT
ENTRYPOINT ["/entrypoint.sh"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:103251184b1f99b967d69ff5703f1ce65a243b3fbf7bfac07fc332ba920a3dc2`  
		Last Modified: Wed, 07 Mar 2018 08:25:59 GMT  
		Size: 21.8 MB (21826555 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2cff81d055115221819fa260de76558cacb3d62b690323c599002bd40e826ca`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a52e46ee8f1f8130ff7e09d8027b97ef727fd785c98ac19f2f5f2b8268ef85c1`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea96b30d7a8a2f31c50297a97684a574c7ec5eb2b82736ed5a502ba13acb7eeb`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:824687efb5b6b763191b21277fff2756dbfb18faf34c5261c790b8b6ec9230c0`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3235ad9c300eef882002d62630ef4176a9ae2c21d4a75aa384c5b71a50e58b07`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 351.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `znc:1.6-slim`

```console
$ docker pull znc@sha256:892fe7ae4e297ca41b0d0ab9680630b96ce75d92515a71ad3bb2222d2a262baf
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `znc:1.6-slim` - linux; amd64

```console
$ docker pull znc@sha256:f15635fd193f4946f0ad61257280d1d9c389e3196636abacaf9b92d9499e6268
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **23.9 MB (23893406 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9fa07312a97398530366d2d9535aca2f9cea885c25db98aca6ff30c0f634463e`
-	Entrypoint: `["\/entrypoint.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 03:44:56 GMT
ENV GPG_KEY=D5823CACB477191CAC0075555AE420CC0209989E
# Wed, 10 Jan 2018 03:44:57 GMT
ARG CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6
# Wed, 10 Jan 2018 03:44:57 GMT
ARG MAKEFLAGS=
# Tue, 06 Mar 2018 01:32:42 GMT
ENV ZNC_VERSION=1.6.6
# Wed, 07 Mar 2018 08:22:15 GMT
# ARGS: CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6 MAKEFLAGS=
RUN set -x     && adduser -S znc     && addgroup -S znc     && apk add --no-cache --virtual runtime-dependencies         ca-certificates         cyrus-sasl         icu         su-exec         tini         tzdata     && apk add --no-cache --virtual build-dependencies         build-base         curl         cyrus-sasl-dev         gnupg         icu-dev         libressl-dev         perl-dev         python3-dev     && mkdir /znc-src && cd /znc-src     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz" -o znc.tgz     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz.sig" -o znc.tgz.sig     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "${GPG_KEY}"     && gpg --batch --verify znc.tgz.sig znc.tgz     && rm -rf "$GNUPGHOME"     && tar -zxf znc.tgz --strip-components=1     && mkdir build && cd build     && ../configure ${CONFIGUREFLAGS}     && make $MAKEFLAGS     && make install     && apk del build-dependencies     && cd / && rm -rf /znc-src
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:9d7b3114446d239420ea168b9310c1d20e26b75d069079c5742a25823c4c2aab in / 
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:e0192a282adc7f54a8a1ff4594ead3ef35387b9ac6cad11dc37da9ea1b048a13 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:378c136273fef23830ba35f7a8a99554baf86a694f5366f4ba9e9bbabcb8ee6a in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:9c43478daa2a1fccaed5a69ad3c74782d9efa3cd18a66d033f2ddf6956451ba5 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
COPY file:0aff452a445b305c16e9c2c7fb36e9b027100f93ff8f18f4a9342fb94cc44b9c in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
VOLUME [/znc-data]
# Wed, 07 Mar 2018 08:22:18 GMT
ENTRYPOINT ["/entrypoint.sh"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:103251184b1f99b967d69ff5703f1ce65a243b3fbf7bfac07fc332ba920a3dc2`  
		Last Modified: Wed, 07 Mar 2018 08:25:59 GMT  
		Size: 21.8 MB (21826555 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2cff81d055115221819fa260de76558cacb3d62b690323c599002bd40e826ca`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a52e46ee8f1f8130ff7e09d8027b97ef727fd785c98ac19f2f5f2b8268ef85c1`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea96b30d7a8a2f31c50297a97684a574c7ec5eb2b82736ed5a502ba13acb7eeb`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:824687efb5b6b763191b21277fff2756dbfb18faf34c5261c790b8b6ec9230c0`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3235ad9c300eef882002d62630ef4176a9ae2c21d4a75aa384c5b71a50e58b07`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 351.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `znc:latest`

```console
$ docker pull znc@sha256:e0aaa5027be53c10ed607f0550ea7ebf7ee2335a6e2cea8cc8dfd6aaa6b2515e
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `znc:latest` - linux; amd64

```console
$ docker pull znc@sha256:4513f95681513fca24a6a698d3b6c586ef9f7ecca242b049ea40365283deeaf9
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **105.5 MB (105514366 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a7fc05a35e1fe2a941041f982b2ef55ebd8dac50bfa594401362f849f69dba4f`
-	Entrypoint: `["\/entrypoint.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 03:44:56 GMT
ENV GPG_KEY=D5823CACB477191CAC0075555AE420CC0209989E
# Wed, 10 Jan 2018 03:44:57 GMT
ARG CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6
# Wed, 10 Jan 2018 03:44:57 GMT
ARG MAKEFLAGS=
# Tue, 06 Mar 2018 01:32:42 GMT
ENV ZNC_VERSION=1.6.6
# Wed, 07 Mar 2018 08:22:15 GMT
# ARGS: CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6 MAKEFLAGS=
RUN set -x     && adduser -S znc     && addgroup -S znc     && apk add --no-cache --virtual runtime-dependencies         ca-certificates         cyrus-sasl         icu         su-exec         tini         tzdata     && apk add --no-cache --virtual build-dependencies         build-base         curl         cyrus-sasl-dev         gnupg         icu-dev         libressl-dev         perl-dev         python3-dev     && mkdir /znc-src && cd /znc-src     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz" -o znc.tgz     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz.sig" -o znc.tgz.sig     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "${GPG_KEY}"     && gpg --batch --verify znc.tgz.sig znc.tgz     && rm -rf "$GNUPGHOME"     && tar -zxf znc.tgz --strip-components=1     && mkdir build && cd build     && ../configure ${CONFIGUREFLAGS}     && make $MAKEFLAGS     && make install     && apk del build-dependencies     && cd / && rm -rf /znc-src
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:9d7b3114446d239420ea168b9310c1d20e26b75d069079c5742a25823c4c2aab in / 
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:e0192a282adc7f54a8a1ff4594ead3ef35387b9ac6cad11dc37da9ea1b048a13 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:378c136273fef23830ba35f7a8a99554baf86a694f5366f4ba9e9bbabcb8ee6a in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:9c43478daa2a1fccaed5a69ad3c74782d9efa3cd18a66d033f2ddf6956451ba5 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
COPY file:0aff452a445b305c16e9c2c7fb36e9b027100f93ff8f18f4a9342fb94cc44b9c in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
VOLUME [/znc-data]
# Wed, 07 Mar 2018 08:22:18 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 07 Mar 2018 08:25:34 GMT
RUN set -x     && apk add --no-cache         build-base         icu-dev         libressl-dev         perl         python3
# Wed, 07 Mar 2018 08:25:35 GMT
COPY file:d1446fead8db29053b5a4bf7f2af913ddb4d8b1c90f97cc6c099fc74c4322109 in /startup-sequence/ 
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:103251184b1f99b967d69ff5703f1ce65a243b3fbf7bfac07fc332ba920a3dc2`  
		Last Modified: Wed, 07 Mar 2018 08:25:59 GMT  
		Size: 21.8 MB (21826555 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2cff81d055115221819fa260de76558cacb3d62b690323c599002bd40e826ca`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a52e46ee8f1f8130ff7e09d8027b97ef727fd785c98ac19f2f5f2b8268ef85c1`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea96b30d7a8a2f31c50297a97684a574c7ec5eb2b82736ed5a502ba13acb7eeb`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:824687efb5b6b763191b21277fff2756dbfb18faf34c5261c790b8b6ec9230c0`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3235ad9c300eef882002d62630ef4176a9ae2c21d4a75aa384c5b71a50e58b07`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 351.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40a3bfde275a32a63fa7b866c38a75d933cd11b16441532c73e11f4fc16a6909`  
		Last Modified: Wed, 07 Mar 2018 08:27:05 GMT  
		Size: 81.6 MB (81620628 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06cf59fc68dff93a7f6f767850146d5c755386461e45442469ee20eb208ebd3f`  
		Last Modified: Wed, 07 Mar 2018 08:26:52 GMT  
		Size: 332.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `znc:slim`

```console
$ docker pull znc@sha256:892fe7ae4e297ca41b0d0ab9680630b96ce75d92515a71ad3bb2222d2a262baf
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `znc:slim` - linux; amd64

```console
$ docker pull znc@sha256:f15635fd193f4946f0ad61257280d1d9c389e3196636abacaf9b92d9499e6268
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **23.9 MB (23893406 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:9fa07312a97398530366d2d9535aca2f9cea885c25db98aca6ff30c0f634463e`
-	Entrypoint: `["\/entrypoint.sh"]`

```dockerfile
# Tue, 09 Jan 2018 21:10:58 GMT
ADD file:093f0723fa46f6cdbd6f7bd146448bb70ecce54254c35701feeceb956414622f in / 
# Tue, 09 Jan 2018 21:10:58 GMT
CMD ["/bin/sh"]
# Wed, 10 Jan 2018 03:44:56 GMT
ENV GPG_KEY=D5823CACB477191CAC0075555AE420CC0209989E
# Wed, 10 Jan 2018 03:44:57 GMT
ARG CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6
# Wed, 10 Jan 2018 03:44:57 GMT
ARG MAKEFLAGS=
# Tue, 06 Mar 2018 01:32:42 GMT
ENV ZNC_VERSION=1.6.6
# Wed, 07 Mar 2018 08:22:15 GMT
# ARGS: CONFIGUREFLAGS=--prefix=/opt/znc --enable-cyrus --enable-perl --enable-python --disable-ipv6 MAKEFLAGS=
RUN set -x     && adduser -S znc     && addgroup -S znc     && apk add --no-cache --virtual runtime-dependencies         ca-certificates         cyrus-sasl         icu         su-exec         tini         tzdata     && apk add --no-cache --virtual build-dependencies         build-base         curl         cyrus-sasl-dev         gnupg         icu-dev         libressl-dev         perl-dev         python3-dev     && mkdir /znc-src && cd /znc-src     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz" -o znc.tgz     && curl -fsSL "https://znc.in/releases/archive/znc-${ZNC_VERSION}.tar.gz.sig" -o znc.tgz.sig     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "${GPG_KEY}"     && gpg --batch --verify znc.tgz.sig znc.tgz     && rm -rf "$GNUPGHOME"     && tar -zxf znc.tgz --strip-components=1     && mkdir build && cd build     && ../configure ${CONFIGUREFLAGS}     && make $MAKEFLAGS     && make install     && apk del build-dependencies     && cd / && rm -rf /znc-src
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:9d7b3114446d239420ea168b9310c1d20e26b75d069079c5742a25823c4c2aab in / 
# Wed, 07 Mar 2018 08:22:16 GMT
COPY file:e0192a282adc7f54a8a1ff4594ead3ef35387b9ac6cad11dc37da9ea1b048a13 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:378c136273fef23830ba35f7a8a99554baf86a694f5366f4ba9e9bbabcb8ee6a in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:17 GMT
COPY file:9c43478daa2a1fccaed5a69ad3c74782d9efa3cd18a66d033f2ddf6956451ba5 in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
COPY file:0aff452a445b305c16e9c2c7fb36e9b027100f93ff8f18f4a9342fb94cc44b9c in /startup-sequence/ 
# Wed, 07 Mar 2018 08:22:18 GMT
VOLUME [/znc-data]
# Wed, 07 Mar 2018 08:22:18 GMT
ENTRYPOINT ["/entrypoint.sh"]
```

-	Layers:
	-	`sha256:ff3a5c916c92643ff77519ffa742d3ec61b7f591b6b7504599d95a4a41134e28`  
		Last Modified: Tue, 09 Jan 2018 21:13:34 GMT  
		Size: 2.1 MB (2065537 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:103251184b1f99b967d69ff5703f1ce65a243b3fbf7bfac07fc332ba920a3dc2`  
		Last Modified: Wed, 07 Mar 2018 08:25:59 GMT  
		Size: 21.8 MB (21826555 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d2cff81d055115221819fa260de76558cacb3d62b690323c599002bd40e826ca`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a52e46ee8f1f8130ff7e09d8027b97ef727fd785c98ac19f2f5f2b8268ef85c1`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea96b30d7a8a2f31c50297a97684a574c7ec5eb2b82736ed5a502ba13acb7eeb`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 234.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:824687efb5b6b763191b21277fff2756dbfb18faf34c5261c790b8b6ec9230c0`  
		Last Modified: Wed, 07 Mar 2018 08:25:54 GMT  
		Size: 279.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3235ad9c300eef882002d62630ef4176a9ae2c21d4a75aa384c5b71a50e58b07`  
		Last Modified: Wed, 07 Mar 2018 08:25:55 GMT  
		Size: 351.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

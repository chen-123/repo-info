## `solr:6-slim`

```console
$ docker pull solr@sha256:7a49a28db2860f4fedb838919bca86b173e2fec3b406416f37a5a2209e7f6968
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

### `solr:6-slim` - linux; amd64

```console
$ docker pull solr@sha256:45d255579567fd5fce6e1914daaeadd70b298ca1b89310ba9aa55fc4382e65ce
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **230.7 MB (230650332 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:57e152da84d046e8eb32be635e45d4cc45061c89d8b785dac5d03dc491263b08`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr-foreground"]`

```dockerfile
# Tue, 13 Mar 2018 22:27:37 GMT
ADD file:e3250bb9848f956bdb43b205f1237df0d81a25088c95dbdeb20a1e2baf1d884f in / 
# Tue, 13 Mar 2018 22:27:37 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 11:07:04 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 11:07:04 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 11:07:05 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 14 Mar 2018 11:07:06 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 14 Mar 2018 11:07:06 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 14 Mar 2018 11:07:06 GMT
ENV JAVA_VERSION=8u151
# Wed, 14 Mar 2018 11:07:06 GMT
ENV JAVA_DEBIAN_VERSION=8u151-b12-1~deb9u1
# Wed, 14 Mar 2018 11:07:07 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 14 Mar 2018 11:07:24 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 14 Mar 2018 11:07:26 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Thu, 15 Mar 2018 13:22:34 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Thu, 15 Mar 2018 13:22:34 GMT
ARG SOLR_DOWNLOAD_SERVER
# Thu, 15 Mar 2018 13:22:42 GMT
RUN apt-get update &&   apt-get -y install lsof procps wget gpg &&   rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 13:25:54 GMT
ENV SOLR_USER=solr SOLR_UID=8983 SOLR_GROUP=solr SOLR_GID=8983 SOLR_VERSION=6.6.3 SOLR_URL=https://archive.apache.org/dist/lucene/solr/6.6.3/solr-6.6.3.tgz SOLR_SHA256=326ad83d479d78a8bd72b69110073a6012c81dcb708164ec61e2816321f777f3 SOLR_KEYS=5F55943E13D49059D3F342777186B06E1ED139E7 PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 15 Mar 2018 13:25:55 GMT
RUN groupadd -r --gid $SOLR_GID $SOLR_GROUP &&   useradd -r --uid $SOLR_UID --gid $SOLR_GID $SOLR_USER
# Thu, 15 Mar 2018 13:25:59 GMT
RUN set -e; for key in $SOLR_KEYS; do     found='';     for server in       ha.pool.sks-keyservers.net       hkp://keyserver.ubuntu.com:80       hkp://p80.pool.sks-keyservers.net:80       pgp.mit.edu     ; do       echo "  trying $server for $key";       gpg --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$key" && found=yes && break;     done;     test -z "$found" && echo >&2 "error: failed to fetch $key from several disparate servers -- network issues?" && exit 1;   done;   exit 0
# Thu, 15 Mar 2018 13:26:14 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -nv $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -nv $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores /opt/solr/server/logs /docker-entrypoint-initdb.d /opt/docker-solr &&   sed -i -e 's/"\$(whoami)" == "root"/$(id -u) == 0/' /opt/solr/bin/solr &&   sed -i -e 's/lsof -PniTCP:/lsof -t -PniTCP:/' /opt/solr/bin/solr &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_GROUP /opt/solr
# Thu, 15 Mar 2018 13:26:14 GMT
COPY dir:559a3b850dcec4cf3808cc890e2a3da7dea47e3e083fe4065a61affa123bfbce in /opt/docker-solr/scripts 
# Thu, 15 Mar 2018 13:26:15 GMT
RUN chown -R $SOLR_USER:$SOLR_GROUP /opt/docker-solr
# Thu, 15 Mar 2018 13:26:15 GMT
EXPOSE 8983/tcp
# Thu, 15 Mar 2018 13:26:16 GMT
WORKDIR /opt/solr
# Thu, 15 Mar 2018 13:26:16 GMT
USER [solr]
# Thu, 15 Mar 2018 13:26:16 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 15 Mar 2018 13:26:16 GMT
CMD ["solr-foreground"]
```

-	Layers:
	-	`sha256:2a72cbf407d67c7a7a76dd48e432091678e297140dce050ad5eccad918a9f8d6`  
		Last Modified: Tue, 13 Mar 2018 22:54:21 GMT  
		Size: 22.5 MB (22488979 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:35b826b31940917d1052a280a46c73120f9688ce9b03a4f185d80b57755e0a9d`  
		Last Modified: Wed, 14 Mar 2018 12:48:12 GMT  
		Size: 454.8 KB (454841 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cb043c2d1520ae17e6480642d46665aeb109f65e9fa57cd74e8d82beb3f6eb5f`  
		Last Modified: Wed, 14 Mar 2018 12:48:11 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b9d9a7482db5eaf9dfdeb02742795077ba645020e34eb8d7edade6f3ad7736b`  
		Last Modified: Wed, 14 Mar 2018 12:48:11 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f72e4c44d5ebaf32aa99b539255f3ff367bc899d572d92e3d13581eb54f464c`  
		Last Modified: Wed, 14 Mar 2018 12:48:22 GMT  
		Size: 56.0 MB (55999295 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cc097d790b50066f7e74a2a515381ee9340942d2b877144df6ea432127b1da26`  
		Last Modified: Wed, 14 Mar 2018 12:48:11 GMT  
		Size: 272.1 KB (272079 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e67e97e64381f90e32498c77b152bca8802836425313f618ca90d4b9ff8ba121`  
		Last Modified: Thu, 15 Mar 2018 13:50:03 GMT  
		Size: 4.0 MB (3968111 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:36ffcb2e21fe03dc6331e38a4724fce9614573588c789a649d13939ca89b3d83`  
		Last Modified: Thu, 15 Mar 2018 13:54:42 GMT  
		Size: 4.3 KB (4328 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84d9ab0caef3b70cb65b3c65083bc0b64b2e5e5c95eb876bbb980e9c0a38af93`  
		Last Modified: Thu, 15 Mar 2018 13:54:42 GMT  
		Size: 10.8 KB (10756 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7508fba94286d480c5048a45d680e5fe4a3c8bbb4af0359ff272b493495bc0a7`  
		Last Modified: Thu, 15 Mar 2018 13:55:07 GMT  
		Size: 147.4 MB (147443111 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c78a36f218753ead775f8fa003b372d6402bed171aec6c37e7658c2a24eec2d5`  
		Last Modified: Thu, 15 Mar 2018 13:54:42 GMT  
		Size: 4.2 KB (4224 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d5d258d818ce66cf807ff0c2eef72e68f0a5128b0da8ccb564c50b7ce2a5e63`  
		Last Modified: Thu, 15 Mar 2018 13:54:42 GMT  
		Size: 4.2 KB (4229 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `solr:6-slim` - linux; arm variant v5

```console
$ docker pull solr@sha256:dcee5ced867aafc7ce2559419fcda43216a38ea005ac261252a2b78c62fc6e59
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **219.9 MB (219850689 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a7f20109f371a3dece172f72a132265c8fcf83373f5c323caa73f4053eb4da80`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr-foreground"]`

```dockerfile
# Wed, 14 Mar 2018 20:01:39 GMT
ADD file:c472062baa8d8c35c7642162b18516ecdc2e143d0e5c147b472312cfc532efe9 in / 
# Wed, 14 Mar 2018 20:01:40 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 22:48:26 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 22:48:27 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 22:48:28 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 14 Mar 2018 22:48:29 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 14 Mar 2018 22:48:29 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 14 Mar 2018 22:48:30 GMT
ENV JAVA_VERSION=8u151
# Wed, 14 Mar 2018 22:48:30 GMT
ENV JAVA_DEBIAN_VERSION=8u151-b12-1~deb9u1
# Wed, 14 Mar 2018 22:48:30 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 14 Mar 2018 22:49:05 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 14 Mar 2018 22:49:16 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Thu, 15 Mar 2018 01:47:17 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Thu, 15 Mar 2018 01:47:17 GMT
ARG SOLR_DOWNLOAD_SERVER
# Thu, 15 Mar 2018 01:47:29 GMT
RUN apt-get update &&   apt-get -y install lsof procps wget gpg &&   rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 01:50:22 GMT
ENV SOLR_USER=solr SOLR_UID=8983 SOLR_GROUP=solr SOLR_GID=8983 SOLR_VERSION=6.6.3 SOLR_URL=https://archive.apache.org/dist/lucene/solr/6.6.3/solr-6.6.3.tgz SOLR_SHA256=326ad83d479d78a8bd72b69110073a6012c81dcb708164ec61e2816321f777f3 SOLR_KEYS=5F55943E13D49059D3F342777186B06E1ED139E7 PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 15 Mar 2018 01:50:23 GMT
RUN groupadd -r --gid $SOLR_GID $SOLR_GROUP &&   useradd -r --uid $SOLR_UID --gid $SOLR_GID $SOLR_USER
# Thu, 15 Mar 2018 01:50:26 GMT
RUN set -e; for key in $SOLR_KEYS; do     found='';     for server in       ha.pool.sks-keyservers.net       hkp://keyserver.ubuntu.com:80       hkp://p80.pool.sks-keyservers.net:80       pgp.mit.edu     ; do       echo "  trying $server for $key";       gpg --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$key" && found=yes && break;     done;     test -z "$found" && echo >&2 "error: failed to fetch $key from several disparate servers -- network issues?" && exit 1;   done;   exit 0
# Thu, 15 Mar 2018 01:50:42 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -nv $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -nv $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores /opt/solr/server/logs /docker-entrypoint-initdb.d /opt/docker-solr &&   sed -i -e 's/"\$(whoami)" == "root"/$(id -u) == 0/' /opt/solr/bin/solr &&   sed -i -e 's/lsof -PniTCP:/lsof -t -PniTCP:/' /opt/solr/bin/solr &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_GROUP /opt/solr
# Thu, 15 Mar 2018 01:50:43 GMT
COPY dir:559a3b850dcec4cf3808cc890e2a3da7dea47e3e083fe4065a61affa123bfbce in /opt/docker-solr/scripts 
# Thu, 15 Mar 2018 01:50:44 GMT
RUN chown -R $SOLR_USER:$SOLR_GROUP /opt/docker-solr
# Thu, 15 Mar 2018 01:50:44 GMT
EXPOSE 8983/tcp
# Thu, 15 Mar 2018 01:50:45 GMT
WORKDIR /opt/solr
# Thu, 15 Mar 2018 01:50:45 GMT
USER [solr]
# Thu, 15 Mar 2018 01:50:45 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 15 Mar 2018 01:50:46 GMT
CMD ["solr-foreground"]
```

-	Layers:
	-	`sha256:8efba53ec4136476603e9856d8bb17541faa0f33abada48ac4d2d7efe61ff43f`  
		Last Modified: Wed, 14 Mar 2018 20:13:21 GMT  
		Size: 21.2 MB (21164955 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b1949e18a328f3c9b962c19755d8a55af0f21d21943810d7daf39862ab8bedf`  
		Last Modified: Wed, 14 Mar 2018 23:12:26 GMT  
		Size: 447.7 KB (447681 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b95963c2f246890fe81e80837f0f83814d454828b59a18fb683a23a7f0eb09c`  
		Last Modified: Wed, 14 Mar 2018 23:12:26 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f7dc2f45c72f39e5727403aaf034f49ea08f3db29ca0556933a777d8ea0ff9d`  
		Last Modified: Wed, 14 Mar 2018 23:12:26 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:96069ab4c3365044a7103b16a1c9f0916d0f53c8f779b19218ab0c520fcd65be`  
		Last Modified: Wed, 14 Mar 2018 23:12:38 GMT  
		Size: 46.7 MB (46726479 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:94eeed948b7ccf3ef4c161427270912d45cd6c17831a3cc894ff7147db4c6a62`  
		Last Modified: Wed, 14 Mar 2018 23:12:26 GMT  
		Size: 272.2 KB (272198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c389a12b3f60e7b31a15db36537dc329be944b949362b093e0a5f048057fad91`  
		Last Modified: Thu, 15 Mar 2018 01:53:25 GMT  
		Size: 3.8 MB (3772367 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:80cadc45d617bbc9131acf97df772fcb387312a9592e0e90a775c868e6418121`  
		Last Modified: Thu, 15 Mar 2018 01:56:50 GMT  
		Size: 4.3 KB (4260 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a43dd6469e59839e6a46dc89236033fa34edd2e7e6491511ec90b9853812dbfd`  
		Last Modified: Thu, 15 Mar 2018 01:56:50 GMT  
		Size: 10.8 KB (10793 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad201cbbedf4a5c42908ff01761337996ef0dae59aa572ee3e58b087500dc4ed`  
		Last Modified: Thu, 15 Mar 2018 01:57:09 GMT  
		Size: 147.4 MB (147443092 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:342920ba5d1c260ad22cc00efa1d8f56a0bcffe6d5521a608d1574ebce013974`  
		Last Modified: Thu, 15 Mar 2018 01:56:50 GMT  
		Size: 4.3 KB (4254 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b28d92f53fd7327a36f981b27e76a1f9789aa6ab5467e220c1489a9c0fb546f7`  
		Last Modified: Thu, 15 Mar 2018 01:56:50 GMT  
		Size: 4.2 KB (4232 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `solr:6-slim` - linux; arm variant v7

```console
$ docker pull solr@sha256:8bcf2a880c2d22654b6d3ee7e02b8625667dec6156736467573504b0ebf22820
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **217.1 MB (217080868 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:15c3d75572048b7e628988890129c0201e2628a1c91815126803fbaa1e057917`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr-foreground"]`

```dockerfile
# Mon, 09 Oct 2017 21:45:43 GMT
ADD file:b758c6c3ff989778bd740dde35c86b953fa09be913a7e02711b2881de6b8911d in / 
# Mon, 09 Oct 2017 21:45:44 GMT
CMD ["bash"]
# Mon, 09 Oct 2017 23:05:29 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Mon, 09 Oct 2017 23:05:30 GMT
ENV LANG=C.UTF-8
# Mon, 09 Oct 2017 23:05:32 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Mon, 09 Oct 2017 23:05:33 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Mon, 09 Oct 2017 23:07:42 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Mon, 09 Oct 2017 23:07:43 GMT
ENV JAVA_VERSION=8u141
# Mon, 09 Oct 2017 23:07:43 GMT
ENV JAVA_DEBIAN_VERSION=8u141-b15-1~deb9u1
# Mon, 09 Oct 2017 23:07:43 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Mon, 09 Oct 2017 23:08:10 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Mon, 09 Oct 2017 23:08:18 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Tue, 10 Oct 2017 01:28:50 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Tue, 10 Oct 2017 01:28:50 GMT
ARG SOLR_DOWNLOAD_SERVER
# Tue, 10 Oct 2017 01:28:58 GMT
RUN apt-get update &&   apt-get -y install lsof procps wget gpg &&   rm -rf /var/lib/apt/lists/*
# Thu, 08 Mar 2018 14:24:23 GMT
ENV SOLR_USER=solr SOLR_UID=8983 SOLR_GROUP=solr SOLR_GID=8983 SOLR_VERSION=6.6.3 SOLR_URL=https://archive.apache.org/dist/lucene/solr/6.6.3/solr-6.6.3.tgz SOLR_SHA256=326ad83d479d78a8bd72b69110073a6012c81dcb708164ec61e2816321f777f3 SOLR_KEYS=5F55943E13D49059D3F342777186B06E1ED139E7 PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 08 Mar 2018 14:24:24 GMT
RUN groupadd -r --gid $SOLR_GID $SOLR_GROUP &&   useradd -r --uid $SOLR_UID --gid $SOLR_GID $SOLR_USER
# Thu, 08 Mar 2018 14:24:28 GMT
RUN set -e; for key in $SOLR_KEYS; do     found='';     for server in       ha.pool.sks-keyservers.net       hkp://keyserver.ubuntu.com:80       hkp://p80.pool.sks-keyservers.net:80       pgp.mit.edu     ; do       echo "  trying $server for $key";       gpg --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$key" && found=yes && break;     done;     test -z "$found" && echo >&2 "error: failed to fetch $key from several disparate servers -- network issues?" && exit 1;   done;   exit 0
# Thu, 08 Mar 2018 14:24:42 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -nv $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -nv $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores /opt/solr/server/logs /docker-entrypoint-initdb.d /opt/docker-solr &&   sed -i -e 's/"\$(whoami)" == "root"/$(id -u) == 0/' /opt/solr/bin/solr &&   sed -i -e 's/lsof -PniTCP:/lsof -t -PniTCP:/' /opt/solr/bin/solr &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_GROUP /opt/solr
# Thu, 08 Mar 2018 14:24:43 GMT
COPY dir:559a3b850dcec4cf3808cc890e2a3da7dea47e3e083fe4065a61affa123bfbce in /opt/docker-solr/scripts 
# Thu, 08 Mar 2018 14:24:44 GMT
RUN chown -R $SOLR_USER:$SOLR_GROUP /opt/docker-solr
# Thu, 08 Mar 2018 14:24:44 GMT
EXPOSE 8983/tcp
# Thu, 08 Mar 2018 14:24:44 GMT
WORKDIR /opt/solr
# Thu, 08 Mar 2018 14:24:45 GMT
USER [solr]
# Thu, 08 Mar 2018 14:24:45 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 08 Mar 2018 14:24:45 GMT
CMD ["solr-foreground"]
```

-	Layers:
	-	`sha256:59e81a3fde58ec8d4b8f2f58b98ef2f4d951d37dd9b99b016fd294a8e07d7796`  
		Last Modified: Mon, 09 Oct 2017 21:52:49 GMT  
		Size: 19.3 MB (19277135 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6226915187b9d61d290e04413a4ccdf021b5e0fc267ba8129cc0126cab1f1a93`  
		Last Modified: Mon, 09 Oct 2017 23:24:02 GMT  
		Size: 430.6 KB (430580 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f98b9b3c90ff2ee65efc9f88b2383f6f1760df78bcd965fa0b22e001977eaf96`  
		Last Modified: Mon, 09 Oct 2017 23:24:01 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:377cafaae0c7321b0549f3949d78826675109fe908cb8521f39fe433ccfced7c`  
		Last Modified: Mon, 09 Oct 2017 23:24:01 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6a90e76db87bd029fe0cc5b41e212f46198e84bcdd6fd9d8100d543019ca3ec0`  
		Last Modified: Mon, 09 Oct 2017 23:25:48 GMT  
		Size: 46.2 MB (46152339 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d672e3cc87b30249aae8cf95548eb623752b0a5c2e9e70c1a578c7895b2c909d`  
		Last Modified: Mon, 09 Oct 2017 23:25:36 GMT  
		Size: 272.2 KB (272181 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3348db73a5179352f7c9415360de082aefe0b3a8015a2c4fd26d9ee95a665061`  
		Last Modified: Tue, 10 Oct 2017 01:37:52 GMT  
		Size: 3.5 MB (3481666 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71802e75f255865310dc9e4c220443493fe84f5a814284b04cd6d931a317e213`  
		Last Modified: Thu, 08 Mar 2018 14:28:51 GMT  
		Size: 4.3 KB (4259 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:07f6bf2e9a6a5eb30cc973f6c0dfaaf33446d4a5aa3eb9dae0c6ae55cc400dbb`  
		Last Modified: Thu, 08 Mar 2018 14:28:51 GMT  
		Size: 10.8 KB (10787 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb220bd2e4a89be08aac999fd88f3654d4516905d5cf3dc526db9983159b6f6d`  
		Last Modified: Thu, 08 Mar 2018 14:29:09 GMT  
		Size: 147.4 MB (147443061 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c5371ba85ef90fe499318fd8e5935caa787b751dff33df97a0bb3456ba7f9e77`  
		Last Modified: Thu, 08 Mar 2018 14:28:51 GMT  
		Size: 4.3 KB (4252 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a4fecdb66ab5658949b9e37fc8623ca9ccb7695a852de2f68d68ae46a1f5d6d0`  
		Last Modified: Thu, 08 Mar 2018 14:28:51 GMT  
		Size: 4.2 KB (4230 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `solr:6-slim` - linux; arm64 variant v8

```console
$ docker pull solr@sha256:a2949c3cdf5325e47c856c98e17780f7d7f68953523e34eea7a3ac6a1020ff41
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **220.3 MB (220312957 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2e18c25d11b9d258b1d704784846eff8502b5b46cb446d73ddcfebac625db345`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr-foreground"]`

```dockerfile
# Wed, 14 Mar 2018 17:31:57 GMT
ADD file:c8a9419b2fbc1297f28b404507a39054e101a6f21f15c352b351cab19067cb4f in / 
# Wed, 14 Mar 2018 17:31:57 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 20:40:13 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 20:40:14 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 20:40:18 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 14 Mar 2018 20:40:20 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 14 Mar 2018 20:40:21 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 14 Mar 2018 20:40:22 GMT
ENV JAVA_VERSION=8u151
# Wed, 14 Mar 2018 20:40:23 GMT
ENV JAVA_DEBIAN_VERSION=8u151-b12-1~deb9u1
# Wed, 14 Mar 2018 20:40:24 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 14 Mar 2018 20:42:34 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 14 Mar 2018 20:42:42 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Thu, 15 Mar 2018 07:45:01 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Thu, 15 Mar 2018 07:45:03 GMT
ARG SOLR_DOWNLOAD_SERVER
# Thu, 15 Mar 2018 07:46:53 GMT
RUN apt-get update &&   apt-get -y install lsof procps wget gpg &&   rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 07:55:33 GMT
ENV SOLR_USER=solr SOLR_UID=8983 SOLR_GROUP=solr SOLR_GID=8983 SOLR_VERSION=6.6.3 SOLR_URL=https://archive.apache.org/dist/lucene/solr/6.6.3/solr-6.6.3.tgz SOLR_SHA256=326ad83d479d78a8bd72b69110073a6012c81dcb708164ec61e2816321f777f3 SOLR_KEYS=5F55943E13D49059D3F342777186B06E1ED139E7 PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 15 Mar 2018 07:55:38 GMT
RUN groupadd -r --gid $SOLR_GID $SOLR_GROUP &&   useradd -r --uid $SOLR_UID --gid $SOLR_GID $SOLR_USER
# Thu, 15 Mar 2018 07:55:43 GMT
RUN set -e; for key in $SOLR_KEYS; do     found='';     for server in       ha.pool.sks-keyservers.net       hkp://keyserver.ubuntu.com:80       hkp://p80.pool.sks-keyservers.net:80       pgp.mit.edu     ; do       echo "  trying $server for $key";       gpg --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$key" && found=yes && break;     done;     test -z "$found" && echo >&2 "error: failed to fetch $key from several disparate servers -- network issues?" && exit 1;   done;   exit 0
# Thu, 15 Mar 2018 07:56:40 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -nv $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -nv $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores /opt/solr/server/logs /docker-entrypoint-initdb.d /opt/docker-solr &&   sed -i -e 's/"\$(whoami)" == "root"/$(id -u) == 0/' /opt/solr/bin/solr &&   sed -i -e 's/lsof -PniTCP:/lsof -t -PniTCP:/' /opt/solr/bin/solr &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_GROUP /opt/solr
# Thu, 15 Mar 2018 07:56:41 GMT
COPY dir:559a3b850dcec4cf3808cc890e2a3da7dea47e3e083fe4065a61affa123bfbce in /opt/docker-solr/scripts 
# Thu, 15 Mar 2018 07:56:43 GMT
RUN chown -R $SOLR_USER:$SOLR_GROUP /opt/docker-solr
# Thu, 15 Mar 2018 07:56:44 GMT
EXPOSE 8983/tcp
# Thu, 15 Mar 2018 07:56:45 GMT
WORKDIR /opt/solr
# Thu, 15 Mar 2018 07:56:47 GMT
USER [solr]
# Thu, 15 Mar 2018 07:56:51 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 15 Mar 2018 07:56:55 GMT
CMD ["solr-foreground"]
```

-	Layers:
	-	`sha256:fe48c4e9ee8492678b1070a971759d407b15524c49c40762b590ba4b52766dde`  
		Last Modified: Wed, 14 Mar 2018 17:47:11 GMT  
		Size: 20.3 MB (20337203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:78c2c870b6a03218fa96a1914a126961281284a49163a7dac0a01e1e541e1d87`  
		Last Modified: Wed, 14 Mar 2018 21:41:04 GMT  
		Size: 440.8 KB (440847 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9452cad7dfe516b55adcda81dc66f8983610a046558f0ff3c2fbc4d640273838`  
		Last Modified: Wed, 14 Mar 2018 21:41:04 GMT  
		Size: 247.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4bd53f132dbd6ebdabddfe1a5d0db8da6317d63520610c9287202b678034df19`  
		Last Modified: Wed, 14 Mar 2018 21:41:03 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7bdcc587dc636c9af45b3485ed384b2971cc770190a9395cfdaffe87e1937b66`  
		Last Modified: Wed, 14 Mar 2018 21:41:18 GMT  
		Size: 48.2 MB (48152953 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:daf0159d293381af77389642ad6487d24c4b793862910352b3e6ccb895c7e27b`  
		Last Modified: Wed, 14 Mar 2018 21:41:03 GMT  
		Size: 272.1 KB (272094 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f647a2227c1b2eea6df07902ba178b52a925dde32e7492bd90e2c45ad7651b2`  
		Last Modified: Thu, 15 Mar 2018 08:03:43 GMT  
		Size: 3.6 MB (3642679 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b54e07440ca77b5e6a2921b6ecb3457a6a991b1a06c384650380ed6ecb36fe49`  
		Last Modified: Thu, 15 Mar 2018 08:08:56 GMT  
		Size: 4.4 KB (4376 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8034fad0ea2f0378499463b570b5505de24915f770ba5c01f3ecd0f60f9d270`  
		Last Modified: Thu, 15 Mar 2018 08:08:56 GMT  
		Size: 10.8 KB (10754 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6f12f978381e81e2aacbf3a1ec3f529392fa37a8af2c5c8b6522b5f66c9cd66`  
		Last Modified: Thu, 15 Mar 2018 08:09:17 GMT  
		Size: 147.4 MB (147443216 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:98e924524c9aafd88ed228bbe6ae3f732b17240084dee30fe920e09b3db02d8a`  
		Last Modified: Thu, 15 Mar 2018 08:08:56 GMT  
		Size: 4.2 KB (4226 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cfe09a2f8d14e2af68a71f1fa8290422d9a8ec235eb553fdb1f743e18b3f12be`  
		Last Modified: Thu, 15 Mar 2018 08:08:56 GMT  
		Size: 4.2 KB (4231 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `solr:6-slim` - linux; 386

```console
$ docker pull solr@sha256:79b34032735d24f22eda0835fb07544a3736a873631182b6d7d564035924a02d
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **231.1 MB (231093366 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:78dbe80cbf43239a5ad3401afcb64e1c30608252e9ecebaf049d29fb9ed629f8`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr-foreground"]`

```dockerfile
# Thu, 15 Feb 2018 18:56:40 GMT
ADD file:46f3ea038ddbb2713695c8891a22675f7355211fecac25807c95590f5a5d4bfa in / 
# Thu, 15 Feb 2018 19:04:20 GMT
CMD ["bash"]
# Tue, 20 Feb 2018 18:10:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Tue, 20 Feb 2018 18:10:10 GMT
ENV LANG=C.UTF-8
# Tue, 20 Feb 2018 18:10:11 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Tue, 20 Feb 2018 18:10:12 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Tue, 20 Feb 2018 18:10:12 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Tue, 20 Feb 2018 18:10:12 GMT
ENV JAVA_VERSION=8u151
# Tue, 20 Feb 2018 18:10:13 GMT
ENV JAVA_DEBIAN_VERSION=8u151-b12-1~deb9u1
# Tue, 20 Feb 2018 18:10:13 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Tue, 20 Feb 2018 18:10:36 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Tue, 20 Feb 2018 18:10:37 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Fri, 23 Feb 2018 07:56:25 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Fri, 23 Feb 2018 07:56:25 GMT
ARG SOLR_DOWNLOAD_SERVER
# Fri, 23 Feb 2018 07:56:41 GMT
RUN apt-get update &&   apt-get -y install lsof procps wget gpg &&   rm -rf /var/lib/apt/lists/*
# Fri, 09 Mar 2018 02:27:49 GMT
ENV SOLR_USER=solr SOLR_UID=8983 SOLR_GROUP=solr SOLR_GID=8983 SOLR_VERSION=6.6.3 SOLR_URL=https://archive.apache.org/dist/lucene/solr/6.6.3/solr-6.6.3.tgz SOLR_SHA256=326ad83d479d78a8bd72b69110073a6012c81dcb708164ec61e2816321f777f3 SOLR_KEYS=5F55943E13D49059D3F342777186B06E1ED139E7 PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 09 Mar 2018 02:27:51 GMT
RUN groupadd -r --gid $SOLR_GID $SOLR_GROUP &&   useradd -r --uid $SOLR_UID --gid $SOLR_GID $SOLR_USER
# Fri, 09 Mar 2018 02:27:55 GMT
RUN set -e; for key in $SOLR_KEYS; do     found='';     for server in       ha.pool.sks-keyservers.net       hkp://keyserver.ubuntu.com:80       hkp://p80.pool.sks-keyservers.net:80       pgp.mit.edu     ; do       echo "  trying $server for $key";       gpg --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$key" && found=yes && break;     done;     test -z "$found" && echo >&2 "error: failed to fetch $key from several disparate servers -- network issues?" && exit 1;   done;   exit 0
# Fri, 09 Mar 2018 02:28:13 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -nv $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -nv $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores /opt/solr/server/logs /docker-entrypoint-initdb.d /opt/docker-solr &&   sed -i -e 's/"\$(whoami)" == "root"/$(id -u) == 0/' /opt/solr/bin/solr &&   sed -i -e 's/lsof -PniTCP:/lsof -t -PniTCP:/' /opt/solr/bin/solr &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_GROUP /opt/solr
# Fri, 09 Mar 2018 02:28:14 GMT
COPY dir:559a3b850dcec4cf3808cc890e2a3da7dea47e3e083fe4065a61affa123bfbce in /opt/docker-solr/scripts 
# Fri, 09 Mar 2018 02:28:15 GMT
RUN chown -R $SOLR_USER:$SOLR_GROUP /opt/docker-solr
# Fri, 09 Mar 2018 02:28:16 GMT
EXPOSE 8983/tcp
# Fri, 09 Mar 2018 02:28:16 GMT
WORKDIR /opt/solr
# Fri, 09 Mar 2018 02:28:16 GMT
USER [solr]
# Fri, 09 Mar 2018 02:28:16 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 09 Mar 2018 02:28:17 GMT
CMD ["solr-foreground"]
```

-	Layers:
	-	`sha256:5a3bef8a5a8dcf8e6b5914993862777a98536514aedf43f0a604d87764970d8a`  
		Last Modified: Thu, 15 Feb 2018 01:16:16 GMT  
		Size: 23.1 MB (23135027 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0b868361b518dcc6fb2c7859ac8e0443e6f443c7b452b68b8d9e7728ced6d547`  
		Last Modified: Tue, 20 Feb 2018 18:43:00 GMT  
		Size: 463.5 KB (463456 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:97a27ef0695ed4aa42a3529db326cc4880f4a549da4942a731e2c37efec5138b`  
		Last Modified: Tue, 20 Feb 2018 18:42:59 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:58beaf51181ff8f485479cd306573d135d85f527e884049db1b46205adc8040b`  
		Last Modified: Tue, 20 Feb 2018 18:42:59 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a799ddb47172277ebd7cf4a75311844e730736cab48e1f2fe575252cb7b025d4`  
		Last Modified: Tue, 20 Feb 2018 18:43:21 GMT  
		Size: 55.5 MB (55544952 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1afae4c673f3aba1e60c972999ea6310d27967c7ef56ad4f6e375756e2617205`  
		Last Modified: Tue, 20 Feb 2018 18:42:59 GMT  
		Size: 272.1 KB (272134 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:942c6acb9c59e8c4230b4a1d02d184971ea1b36dfa958a0438838122e8ded8f5`  
		Last Modified: Fri, 23 Feb 2018 08:35:29 GMT  
		Size: 4.2 MB (4210723 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:620cd5a0c4144255c07f39ba279d0ea234c709488ccb56fbec03087f943576b3`  
		Last Modified: Fri, 09 Mar 2018 05:08:27 GMT  
		Size: 4.3 KB (4264 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c9f22a89e9fb176a34108767759da892576f86229806d229f75aad77672dea5c`  
		Last Modified: Fri, 09 Mar 2018 05:08:28 GMT  
		Size: 10.8 KB (10758 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bfe8aabe665a9c37a082c89b80f2314de5b94377cbcaff9dc85de42b15eb54d9`  
		Last Modified: Fri, 09 Mar 2018 05:08:43 GMT  
		Size: 147.4 MB (147443224 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25a2229428fca3daca8e00e36aa70fc608540c2532a233222f52b0aaf8312971`  
		Last Modified: Fri, 09 Mar 2018 05:08:27 GMT  
		Size: 4.2 KB (4222 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6c0aa5c79e9bb748d47dc6aa763fa1d5bc4bb422aa04e934fb22a6f3f7d86394`  
		Last Modified: Fri, 09 Mar 2018 05:08:27 GMT  
		Size: 4.2 KB (4227 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `solr:6-slim` - linux; ppc64le

```console
$ docker pull solr@sha256:28c97c28fd22990d7cc9f1ae9098b93e1f8d3ccac1a1baf934263b157b5ae90b
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **223.5 MB (223514214 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a60d122e9c2d91eaa566efe59ff7c99505d2198d9c3dd2873beec041dbb84c8a`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr-foreground"]`

```dockerfile
# Wed, 14 Mar 2018 00:35:22 GMT
ADD file:eb08f3c15b97624b92d23e06e82a8de439723fe3fd0f2d75b242fd2a9b9abc51 in / 
# Wed, 14 Mar 2018 00:35:24 GMT
CMD ["bash"]
# Thu, 15 Mar 2018 04:52:42 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 04:52:45 GMT
ENV LANG=C.UTF-8
# Thu, 15 Mar 2018 04:52:52 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Thu, 15 Mar 2018 04:52:59 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Thu, 15 Mar 2018 04:53:02 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Thu, 15 Mar 2018 04:53:06 GMT
ENV JAVA_VERSION=8u151
# Thu, 15 Mar 2018 04:53:09 GMT
ENV JAVA_DEBIAN_VERSION=8u151-b12-1~deb9u1
# Thu, 15 Mar 2018 04:53:13 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Thu, 15 Mar 2018 04:58:07 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 15 Mar 2018 04:58:20 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Thu, 15 Mar 2018 10:49:47 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Thu, 15 Mar 2018 10:49:50 GMT
ARG SOLR_DOWNLOAD_SERVER
# Thu, 15 Mar 2018 10:50:52 GMT
RUN apt-get update &&   apt-get -y install lsof procps wget gpg &&   rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 10:59:38 GMT
ENV SOLR_USER=solr SOLR_UID=8983 SOLR_GROUP=solr SOLR_GID=8983 SOLR_VERSION=6.6.3 SOLR_URL=https://archive.apache.org/dist/lucene/solr/6.6.3/solr-6.6.3.tgz SOLR_SHA256=326ad83d479d78a8bd72b69110073a6012c81dcb708164ec61e2816321f777f3 SOLR_KEYS=5F55943E13D49059D3F342777186B06E1ED139E7 PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 15 Mar 2018 10:59:43 GMT
RUN groupadd -r --gid $SOLR_GID $SOLR_GROUP &&   useradd -r --uid $SOLR_UID --gid $SOLR_GID $SOLR_USER
# Thu, 15 Mar 2018 10:59:49 GMT
RUN set -e; for key in $SOLR_KEYS; do     found='';     for server in       ha.pool.sks-keyservers.net       hkp://keyserver.ubuntu.com:80       hkp://p80.pool.sks-keyservers.net:80       pgp.mit.edu     ; do       echo "  trying $server for $key";       gpg --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$key" && found=yes && break;     done;     test -z "$found" && echo >&2 "error: failed to fetch $key from several disparate servers -- network issues?" && exit 1;   done;   exit 0
# Thu, 15 Mar 2018 11:01:07 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -nv $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -nv $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores /opt/solr/server/logs /docker-entrypoint-initdb.d /opt/docker-solr &&   sed -i -e 's/"\$(whoami)" == "root"/$(id -u) == 0/' /opt/solr/bin/solr &&   sed -i -e 's/lsof -PniTCP:/lsof -t -PniTCP:/' /opt/solr/bin/solr &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_GROUP /opt/solr
# Thu, 15 Mar 2018 11:01:08 GMT
COPY dir:559a3b850dcec4cf3808cc890e2a3da7dea47e3e083fe4065a61affa123bfbce in /opt/docker-solr/scripts 
# Thu, 15 Mar 2018 11:01:13 GMT
RUN chown -R $SOLR_USER:$SOLR_GROUP /opt/docker-solr
# Thu, 15 Mar 2018 11:01:14 GMT
EXPOSE 8983/tcp
# Thu, 15 Mar 2018 11:01:16 GMT
WORKDIR /opt/solr
# Thu, 15 Mar 2018 11:01:17 GMT
USER [solr]
# Thu, 15 Mar 2018 11:01:19 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 15 Mar 2018 11:01:20 GMT
CMD ["solr-foreground"]
```

-	Layers:
	-	`sha256:f3543c3a35ef83bbd42a728d1995f79f0163e330a44b0abe41042ac8b94787ca`  
		Last Modified: Thu, 15 Mar 2018 00:33:06 GMT  
		Size: 22.7 MB (22746142 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2161f1e27455c4f326ed4a0e9f04c75ab7cf7ec817ac77d09e60f7546eba89eb`  
		Last Modified: Thu, 15 Mar 2018 06:06:39 GMT  
		Size: 449.8 KB (449810 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ab6707568a8fbabd710d6a1bd122f68bb3fb7bf70a82f71a8166262bc6ea9041`  
		Last Modified: Thu, 15 Mar 2018 06:06:38 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:291e9f652987d4079557622fc40bd32490a0d89f8a608d317ab0dbcdbd3557c5`  
		Last Modified: Thu, 15 Mar 2018 06:06:39 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:176b0bbc4ac5a95bb7c2c8ff12cefe9feb2605a69fdaa48c7d397eeda7d63355`  
		Last Modified: Thu, 15 Mar 2018 06:06:49 GMT  
		Size: 48.6 MB (48635818 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73b1801f573a41fbd39858d9af85a0313d5ca0dc3a0857525af168947dd62c97`  
		Last Modified: Thu, 15 Mar 2018 06:06:39 GMT  
		Size: 272.1 KB (272075 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9214303910344db67e04e3213788d380362050a964660c18466f1a32ac67c25c`  
		Last Modified: Thu, 15 Mar 2018 11:07:22 GMT  
		Size: 3.9 MB (3943309 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:398034c3ba7bc5c755b1cc3c82f6d7ba704185c2a7ce3869860a368864a2dd5a`  
		Last Modified: Thu, 15 Mar 2018 11:10:10 GMT  
		Size: 4.3 KB (4336 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8636139e22adc309cd9dcfa3b1441d8190b31d3cbdeef320ce0846142ded3945`  
		Last Modified: Thu, 15 Mar 2018 11:10:10 GMT  
		Size: 10.8 KB (10786 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:763caddc9f23fa881995144c01d84728ba8b34bf6bd0fe1e640531d5f37eaad4`  
		Last Modified: Thu, 15 Mar 2018 11:10:27 GMT  
		Size: 147.4 MB (147443079 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c40a1ba27c2bce15bd6ef2d5731df1c8711bfe03e518b70b4c5e89c98dd8850c`  
		Last Modified: Thu, 15 Mar 2018 11:10:09 GMT  
		Size: 4.2 KB (4249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:adcb8e6d8d11fe5737d04347709e0804586a12faa76d04f5e065e49d19398215`  
		Last Modified: Thu, 15 Mar 2018 11:10:10 GMT  
		Size: 4.2 KB (4229 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `solr:6-slim` - linux; s390x

```console
$ docker pull solr@sha256:828b56989928753f7d5a886448dcedaa11ee8201cba59c8bd7a6ff68dfb9e563
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **222.4 MB (222422257 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:59683979bca9e2cca1d5d12a2ca268f779924257a95710b38bd87e77ff0df31f`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["solr-foreground"]`

```dockerfile
# Wed, 14 Mar 2018 05:24:07 GMT
ADD file:61d2621323852492d52f23ac03a18fa0af2bcc5597691b40f508eae65f4a9242 in / 
# Wed, 14 Mar 2018 05:24:07 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 06:43:19 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 06:43:19 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 06:43:19 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 14 Mar 2018 06:43:20 GMT
RUN ln -svT "/usr/lib/jvm/java-8-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 14 Mar 2018 06:43:20 GMT
ENV JAVA_HOME=/docker-java-home/jre
# Wed, 14 Mar 2018 06:43:20 GMT
ENV JAVA_VERSION=8u151
# Wed, 14 Mar 2018 06:43:20 GMT
ENV JAVA_DEBIAN_VERSION=8u151-b12-1~deb9u1
# Wed, 14 Mar 2018 06:43:21 GMT
ENV CA_CERTIFICATES_JAVA_VERSION=20170531+nmu1
# Wed, 14 Mar 2018 06:43:48 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-8-jre-headless="$JAVA_DEBIAN_VERSION" 		ca-certificates-java="$CA_CERTIFICATES_JAVA_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 14 Mar 2018 06:43:51 GMT
RUN /var/lib/dpkg/info/ca-certificates-java.postinst configure
# Wed, 14 Mar 2018 11:14:33 GMT
MAINTAINER Martijn Koster "mak-docker@greenhills.co.uk"
# Wed, 14 Mar 2018 11:14:33 GMT
ARG SOLR_DOWNLOAD_SERVER
# Wed, 14 Mar 2018 11:14:40 GMT
RUN apt-get update &&   apt-get -y install lsof procps wget gpg &&   rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 11:16:32 GMT
ENV SOLR_USER=solr SOLR_UID=8983 SOLR_GROUP=solr SOLR_GID=8983 SOLR_VERSION=6.6.3 SOLR_URL=https://archive.apache.org/dist/lucene/solr/6.6.3/solr-6.6.3.tgz SOLR_SHA256=326ad83d479d78a8bd72b69110073a6012c81dcb708164ec61e2816321f777f3 SOLR_KEYS=5F55943E13D49059D3F342777186B06E1ED139E7 PATH=/opt/solr/bin:/opt/docker-solr/scripts:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 14 Mar 2018 11:16:32 GMT
RUN groupadd -r --gid $SOLR_GID $SOLR_GROUP &&   useradd -r --uid $SOLR_UID --gid $SOLR_GID $SOLR_USER
# Wed, 14 Mar 2018 11:16:35 GMT
RUN set -e; for key in $SOLR_KEYS; do     found='';     for server in       ha.pool.sks-keyservers.net       hkp://keyserver.ubuntu.com:80       hkp://p80.pool.sks-keyservers.net:80       pgp.mit.edu     ; do       echo "  trying $server for $key";       gpg --keyserver "$server" --keyserver-options timeout=10 --recv-keys "$key" && found=yes && break;     done;     test -z "$found" && echo >&2 "error: failed to fetch $key from several disparate servers -- network issues?" && exit 1;   done;   exit 0
# Wed, 14 Mar 2018 11:16:47 GMT
RUN mkdir -p /opt/solr &&   echo "downloading $SOLR_URL" &&   wget -nv $SOLR_URL -O /opt/solr.tgz &&   echo "downloading $SOLR_URL.asc" &&   wget -nv $SOLR_URL.asc -O /opt/solr.tgz.asc &&   echo "$SOLR_SHA256 */opt/solr.tgz" | sha256sum -c - &&   (>&2 ls -l /opt/solr.tgz /opt/solr.tgz.asc) &&   gpg --batch --verify /opt/solr.tgz.asc /opt/solr.tgz &&   tar -C /opt/solr --extract --file /opt/solr.tgz --strip-components=1 &&   rm /opt/solr.tgz* &&   rm -Rf /opt/solr/docs/ &&   mkdir -p /opt/solr/server/solr/lib /opt/solr/server/solr/mycores /opt/solr/server/logs /docker-entrypoint-initdb.d /opt/docker-solr &&   sed -i -e 's/"\$(whoami)" == "root"/$(id -u) == 0/' /opt/solr/bin/solr &&   sed -i -e 's/lsof -PniTCP:/lsof -t -PniTCP:/' /opt/solr/bin/solr &&   sed -i -e '/-Dsolr.clustering.enabled=true/ a SOLR_OPTS="$SOLR_OPTS -Dsun.net.inetaddr.ttl=60 -Dsun.net.inetaddr.negative.ttl=60"' /opt/solr/bin/solr.in.sh &&   chown -R $SOLR_USER:$SOLR_GROUP /opt/solr
# Wed, 14 Mar 2018 11:16:49 GMT
COPY dir:559a3b850dcec4cf3808cc890e2a3da7dea47e3e083fe4065a61affa123bfbce in /opt/docker-solr/scripts 
# Wed, 14 Mar 2018 11:16:49 GMT
RUN chown -R $SOLR_USER:$SOLR_GROUP /opt/docker-solr
# Wed, 14 Mar 2018 11:16:49 GMT
EXPOSE 8983/tcp
# Wed, 14 Mar 2018 11:16:50 GMT
WORKDIR /opt/solr
# Wed, 14 Mar 2018 11:16:50 GMT
USER [solr]
# Wed, 14 Mar 2018 11:16:50 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Wed, 14 Mar 2018 11:16:50 GMT
CMD ["solr-foreground"]
```

-	Layers:
	-	`sha256:b1c81357f99190a5db0d8057d246a1f1ef9b85b2af5569523da5f1dc979989d3`  
		Last Modified: Wed, 14 Mar 2018 05:29:05 GMT  
		Size: 22.3 MB (22340478 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:512c47784c512985a2f670e2a9aebfa09511f48279b95d9891a337a558a3ad3a`  
		Last Modified: Wed, 14 Mar 2018 06:57:32 GMT  
		Size: 465.7 KB (465722 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2fc17c7b5f20c51c5f2c4f4d919514f4d98fd1056c2f72b08ab8a805bcacec06`  
		Last Modified: Wed, 14 Mar 2018 06:57:32 GMT  
		Size: 248.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7342609907d585fc4e70d60bdbe4417280ca389d6d95b71e976510cad8cecc9c`  
		Last Modified: Wed, 14 Mar 2018 06:57:32 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62f0cb60f876cb7ec62f2ebc8b8b14fa411ccd01ea143fcdae0ef98db9150793`  
		Last Modified: Wed, 14 Mar 2018 06:57:40 GMT  
		Size: 47.8 MB (47847164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:934c4b02a8c4a824b52a83bca3302d73067200edf9e3432864394932b2bb8fa7`  
		Last Modified: Wed, 14 Mar 2018 06:57:32 GMT  
		Size: 272.2 KB (272164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b5b9dbd842b1f5a1fc38f0a8437a117018884e20ac5e37a250c22fe2e398b50c`  
		Last Modified: Wed, 14 Mar 2018 11:18:35 GMT  
		Size: 4.0 MB (4029636 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a684a2a7983c3c1dae5f40dcad0873cf157a13f347032806f1320631bcef3de8`  
		Last Modified: Wed, 14 Mar 2018 11:20:44 GMT  
		Size: 4.4 KB (4359 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:73ec9023caceefd72e286015d572707daafae1c588cc7c7afde8b74c97ba6b39`  
		Last Modified: Wed, 14 Mar 2018 11:20:44 GMT  
		Size: 10.8 KB (10753 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28feeb4926aeaca97cb0157a7b9b585fa21068f6674861756154edf8997129d9`  
		Last Modified: Wed, 14 Mar 2018 11:20:54 GMT  
		Size: 147.4 MB (147443149 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea9f06e62a5d9f5ee6c081c8fc186eb6fcfa6d3647a5e30551b4a8d502b94204`  
		Last Modified: Wed, 14 Mar 2018 11:20:44 GMT  
		Size: 4.2 KB (4221 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f08c9a8d50480fdc571885c2db645d42b57c5e35ab19568ed70f28fe066c9ae`  
		Last Modified: Wed, 14 Mar 2018 11:20:44 GMT  
		Size: 4.2 KB (4231 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

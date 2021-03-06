## `kong:latest`

```console
$ docker pull kong@sha256:5a4e72d3fafa29e85239e2789d29e5461eda0e2f0764db72398c95e5b2dfce57
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `kong:latest` - linux; amd64

```console
$ docker pull kong@sha256:db6d221c6a24f056fc8e84cd8b00491730ffd3683c2fa6f1facfd4795d984fe3
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **123.3 MB (123294585 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6afbb6ef6005c77e827487c1cc8f7fc0a4e1fab65ba3a20b721dc9bc17ae608d`
-	Entrypoint: `["\/docker-entrypoint.sh"]`
-	Default Command: `["\/usr\/local\/openresty\/nginx\/sbin\/nginx","-c","\/usr\/local\/kong\/nginx.conf","-p","\/usr\/local\/kong\/"]`

```dockerfile
# Tue, 06 Mar 2018 00:48:12 GMT
ADD file:8d83f3e2c14f39e7f7b281117a45e245c1941668f2d560e9f7ac23da89d667a9 in / 
# Tue, 06 Mar 2018 00:48:12 GMT
LABEL name=CentOS Base Image vendor=CentOS license=GPLv2 build-date=20180302
# Tue, 06 Mar 2018 00:48:12 GMT
CMD ["/bin/bash"]
# Tue, 06 Mar 2018 06:39:33 GMT
MAINTAINER Marco Palladino, marco@mashape.com
# Tue, 13 Mar 2018 00:09:15 GMT
ENV KONG_VERSION=0.12.3
# Tue, 13 Mar 2018 00:09:35 GMT
RUN yum install -y wget https://bintray.com/kong/kong-community-edition-rpm/download_file?file_path=centos/7/kong-community-edition-$KONG_VERSION.el7.noarch.rpm &&     yum clean all
# Tue, 13 Mar 2018 00:09:35 GMT
COPY file:0ce55305f95ddcb78ffb96b9502c795c4dd1040025f4ec7c3e19e4b889022b90 in /docker-entrypoint.sh 
# Tue, 13 Mar 2018 00:09:35 GMT
ENTRYPOINT ["/docker-entrypoint.sh"]
# Tue, 13 Mar 2018 00:09:36 GMT
EXPOSE 8000/tcp 8001/tcp 8443/tcp 8444/tcp
# Tue, 13 Mar 2018 00:09:36 GMT
STOPSIGNAL [SIGTERM]
# Tue, 13 Mar 2018 00:09:36 GMT
CMD ["/usr/local/openresty/nginx/sbin/nginx" "-c" "/usr/local/kong/nginx.conf" "-p" "/usr/local/kong/"]
```

-	Layers:
	-	`sha256:5e35d10a3ebadf9d6ab606ce72e1e77f8646b2e2ff8dd3a60d4401c3e3a76f31`  
		Last Modified: Tue, 06 Mar 2018 01:04:21 GMT  
		Size: 73.0 MB (72980725 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b9c03bf803bd295d1e77060c16f61ca6b23cc7985885325c95356f27b33159fe`  
		Last Modified: Tue, 13 Mar 2018 00:12:03 GMT  
		Size: 50.3 MB (50313538 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02cf0bffddf0aeea794e4635172ff2086d892067447bad2271e9c7df6dbaabe3`  
		Last Modified: Tue, 13 Mar 2018 00:11:56 GMT  
		Size: 322.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

## `buildpack-deps:artful-curl`

```console
$ docker pull buildpack-deps@sha256:e6448d5b0777df52204d1e1d273883ad8dc9b216b09deaa21e2f613f893528bb
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; 386
	-	linux; ppc64le
	-	linux; s390x

### `buildpack-deps:artful-curl` - linux; amd64

```console
$ docker pull buildpack-deps@sha256:a5e6f65cf4bce52ed4210d0c2506e0b06ef087baf13384c7ec5442dab4fd61d2
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **46.4 MB (46399728 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:25ecf334b696ded1ccbe54634cafe53eb2caaa3cc85e83bd952dd8c43e5c29ec`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Tue, 06 Mar 2018 22:15:34 GMT
ADD file:226f9db1fb47304f5ea8acdc21cd88e3d08c5f4844962a442f85de2c3e915306 in / 
# Tue, 06 Mar 2018 22:15:34 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Tue, 06 Mar 2018 22:15:35 GMT
RUN rm -rf /var/lib/apt/lists/*
# Tue, 06 Mar 2018 22:15:36 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Tue, 06 Mar 2018 22:15:37 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Tue, 06 Mar 2018 22:15:37 GMT
CMD ["/bin/bash"]
# Wed, 07 Mar 2018 00:33:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 07 Mar 2018 00:33:09 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:c3b9c0688e3b7308958fed66631654b5c981e097c88ef30a25ef9dd59074bc81`  
		Last Modified: Wed, 28 Feb 2018 15:12:02 GMT  
		Size: 40.3 MB (40339484 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e9fb5affebb02d5f6c42a6c4fed277d21fa12df8f883081f9bbe17484f624a9e`  
		Last Modified: Tue, 06 Mar 2018 22:17:49 GMT  
		Size: 842.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0f1378f511addb056e3a4e992b743b52d6cabb5683d42ce3b7b98691a7f95b38`  
		Last Modified: Tue, 06 Mar 2018 22:17:49 GMT  
		Size: 615.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:96a961dc78435149727fe8313e00df9e2ecd1d5322051f85e5b75ff8ce446372`  
		Last Modified: Tue, 06 Mar 2018 22:17:49 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:16564141bc839850a774f399a35852a4c38c0f78c8b337d1a8bfdf03142c8075`  
		Last Modified: Tue, 06 Mar 2018 22:17:50 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b788e6d175abd746a87e5015bec57c36098609b15d57f5f3ee32cb267c66f155`  
		Last Modified: Wed, 07 Mar 2018 00:56:41 GMT  
		Size: 6.1 MB (6057769 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:artful-curl` - linux; arm variant v7

```console
$ docker pull buildpack-deps@sha256:7bb43deba42e1694ba12ee37d5194311a8a50762927ab5143886aa582cbbdd87
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **41.0 MB (40991789 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:b0cfdd7498e645c80cb6dec2bd1d9dc38e48eafeff846d8ed422a53f647cf123`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Wed, 07 Mar 2018 13:50:42 GMT
ADD file:8b51ab682f77ab0c2bf44f7e1dfe09ed5a549f6b969b949879dc00a72ac0e70e in / 
# Wed, 07 Mar 2018 13:50:43 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 07 Mar 2018 13:50:44 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 07 Mar 2018 13:50:45 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 07 Mar 2018 13:50:46 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 07 Mar 2018 13:50:46 GMT
CMD ["/bin/bash"]
# Wed, 07 Mar 2018 14:13:40 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 07 Mar 2018 14:13:41 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:41aadc2977f096b2b341c3a16df532ceaa4c29d195fb40f0eb0c7d29401a2cf4`  
		Last Modified: Wed, 07 Mar 2018 13:52:57 GMT  
		Size: 35.9 MB (35889369 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:254ccd6ee8b8f8521e8ae433699fa4198122c0c8f379f4cbdadf60f6af34849d`  
		Last Modified: Wed, 07 Mar 2018 13:52:47 GMT  
		Size: 843.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:446681d415b4dacfba6c706af11ebf6dc64d34e9b8dc0bd95bc7b43bd1b14f4e`  
		Last Modified: Wed, 07 Mar 2018 13:52:48 GMT  
		Size: 608.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e29d4fd7398ad0183aee62b84b3e1af75c750d3e82b4cce62fbfb2fefe3c6a9f`  
		Last Modified: Wed, 07 Mar 2018 13:52:48 GMT  
		Size: 854.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2686f47c3ac5b359ae178d83e0dd364e56c1fd43dc256bbbbd785e929dba2371`  
		Last Modified: Wed, 07 Mar 2018 13:52:47 GMT  
		Size: 187.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e782083103db20cfeeefbe9b1bf041d62387419c6b79c8aa32891b50e3acfc03`  
		Last Modified: Wed, 07 Mar 2018 14:27:12 GMT  
		Size: 5.1 MB (5099928 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:artful-curl` - linux; arm64 variant v8

```console
$ docker pull buildpack-deps@sha256:e1e46dbe1bdc96bfdd40d45c608844722ca9f40c2e2464bd79b10763ed74964f
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **42.6 MB (42550625 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0742ca3a9fb5df7aa2db05e0e2843e974f30708a11cc8e344e2b3393af0e3dc3`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Wed, 07 Mar 2018 15:01:00 GMT
ADD file:6cd192af1e5f8a7018833aa1e8834c2035fb429d25a2d878fc44d3dacba7e6e8 in / 
# Wed, 07 Mar 2018 15:01:01 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 07 Mar 2018 15:01:03 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 07 Mar 2018 15:01:04 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 07 Mar 2018 15:01:06 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 07 Mar 2018 15:01:06 GMT
CMD ["/bin/bash"]
# Wed, 07 Mar 2018 15:28:05 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 07 Mar 2018 15:28:07 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:6dfcd13daae87b365b334bf6ec6a95155314ab95e24324fbd45a72532e04eb7d`  
		Last Modified: Wed, 28 Feb 2018 15:21:20 GMT  
		Size: 37.2 MB (37210755 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:97ad7a1d72f5dd5c5fcdda678228937f47cd9c6c97a7b4e17ea4c634a9464a70`  
		Last Modified: Wed, 07 Mar 2018 15:03:59 GMT  
		Size: 844.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5dda6348a6b8ccc80cb88db5830e8cd07aa634f9176bbb3f9ab3825afc86ec25`  
		Last Modified: Wed, 07 Mar 2018 15:03:59 GMT  
		Size: 538.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6d8bc4f8442d9b0f44646b3a70b79df885149a46a2e21e0df26539b367154219`  
		Last Modified: Wed, 07 Mar 2018 15:03:59 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:356d08989eaf05f7aa089bbfa1826d2b319d456df078fe89e8ade7949ec6f25b`  
		Last Modified: Wed, 07 Mar 2018 15:03:59 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62565d5bfae769bad71fef4b2b1e014ca5e0394c75868bfcf1f98844e74cecfb`  
		Last Modified: Wed, 07 Mar 2018 16:18:51 GMT  
		Size: 5.3 MB (5337470 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:artful-curl` - linux; 386

```console
$ docker pull buildpack-deps@sha256:d8193835111173889e9d8d1275ef397520a2725cd2e2ca326e8ea706265cdaa4
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **47.3 MB (47258589 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bacd0111846b8516dc240cea28f53b6f91880959e920f70e71d14b062a0d3e60`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Thu, 08 Mar 2018 03:37:14 GMT
ADD file:21ae54b42598bdc4e53f9cc31f21c838a3febc013ec82f7fa2bde60715358ed6 in / 
# Thu, 08 Mar 2018 03:37:17 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Thu, 08 Mar 2018 03:37:18 GMT
RUN rm -rf /var/lib/apt/lists/*
# Thu, 08 Mar 2018 03:37:19 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Thu, 08 Mar 2018 03:37:20 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Thu, 08 Mar 2018 03:37:20 GMT
CMD ["/bin/bash"]
# Thu, 08 Mar 2018 09:40:00 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Thu, 08 Mar 2018 09:40:01 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:6f4f8c7764e3b9bf54c0b80551001c22563ee6c352468283d261aee662ce8507`  
		Last Modified: Wed, 28 Feb 2018 15:20:04 GMT  
		Size: 41.1 MB (41144382 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f328fe89f835d015452de62e5952c5463c19b8aec1b32b86a50c9331b2d79256`  
		Last Modified: Thu, 08 Mar 2018 04:50:09 GMT  
		Size: 846.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ce90b2869033e50b1e52f3e07387c198342a98b9e2766946037a2d5d46c9985`  
		Last Modified: Thu, 08 Mar 2018 04:50:09 GMT  
		Size: 578.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:564c6fdc53601ac6fc3c81c545e12adb0d3119e204d13351fecba8217713c2ab`  
		Last Modified: Thu, 08 Mar 2018 04:50:09 GMT  
		Size: 850.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1cce0c6dcf704eae01c9678d8e09c763b09a4e201b681976f95e05864be67638`  
		Last Modified: Thu, 08 Mar 2018 04:50:09 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:673992df52ad94b36caa585759e474d215323185cdf3e0760b07b6d9cb87ada6`  
		Last Modified: Thu, 08 Mar 2018 11:46:33 GMT  
		Size: 6.1 MB (6111770 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:artful-curl` - linux; ppc64le

```console
$ docker pull buildpack-deps@sha256:b923d52a527617116803abf7a14541593a433cd113898e0fadbe30c531052b82
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **49.6 MB (49647329 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f502b4387175d7f4510e3bb5a0e7bb7fd7b027060fdc81d027c4df8763399ff3`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Wed, 07 Mar 2018 03:40:20 GMT
ADD file:3e487052d516b784d12726e9545e5a4d20a8eb85cb61891cbb01c912b68a7a52 in / 
# Wed, 07 Mar 2018 03:40:25 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 07 Mar 2018 03:40:29 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 07 Mar 2018 03:40:34 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 07 Mar 2018 03:40:39 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 07 Mar 2018 03:40:41 GMT
CMD ["/bin/bash"]
# Wed, 07 Mar 2018 04:02:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 07 Mar 2018 04:02:20 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:be1681c90bdd83b6f79f79830c7b13d97ed94cdeec8548c93d9c76aa4aacc900`  
		Last Modified: Wed, 07 Mar 2018 03:43:04 GMT  
		Size: 43.5 MB (43513921 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3193734bf7db081d1b21d3e6f57753c7fc0b1acdd3139455ffcf6658e08e640e`  
		Last Modified: Wed, 07 Mar 2018 03:42:56 GMT  
		Size: 844.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:569811142bec37ed112c27989bcbd48b5d2e958e30a893cfc56b6939d49635c9`  
		Last Modified: Wed, 07 Mar 2018 03:42:57 GMT  
		Size: 579.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0de002a1280e9189b82d0c226285162c88c6eb450d09c132f3b88b727ffcc3c2`  
		Last Modified: Wed, 07 Mar 2018 03:42:56 GMT  
		Size: 856.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8c6f5c6d5c658f99f3ae7593ef57abc46ad69beb32428b85bf1d5d14738d7a6e`  
		Last Modified: Wed, 07 Mar 2018 03:42:56 GMT  
		Size: 188.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2dc148cf75d509a73cea91666e0c02cc3e4c1f38ba01bcc4a5702ad475adbe31`  
		Last Modified: Wed, 07 Mar 2018 04:58:39 GMT  
		Size: 6.1 MB (6130941 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `buildpack-deps:artful-curl` - linux; s390x

```console
$ docker pull buildpack-deps@sha256:40a083b6e411b4ee1a38b5dece77673461c2e7d0ff90030241ee62f8bc594402
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **44.7 MB (44717857 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a18778d4c5cfbaee85e60ec01b2e9999fd518dc6229e5f30f8f94fe779ec50ac`
-	Default Command: `["\/bin\/bash"]`

```dockerfile
# Wed, 07 Mar 2018 14:15:38 GMT
ADD file:f1a373b9a247ef914a640bd8984aaf97b386245579e4caa0f7660402e92d2741 in / 
# Wed, 07 Mar 2018 14:15:39 GMT
RUN set -xe 		&& echo '#!/bin/sh' > /usr/sbin/policy-rc.d 	&& echo 'exit 101' >> /usr/sbin/policy-rc.d 	&& chmod +x /usr/sbin/policy-rc.d 		&& dpkg-divert --local --rename --add /sbin/initctl 	&& cp -a /usr/sbin/policy-rc.d /sbin/initctl 	&& sed -i 's/^exit.*/exit 0/' /sbin/initctl 		&& echo 'force-unsafe-io' > /etc/dpkg/dpkg.cfg.d/docker-apt-speedup 		&& echo 'DPkg::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' > /etc/apt/apt.conf.d/docker-clean 	&& echo 'APT::Update::Post-Invoke { "rm -f /var/cache/apt/archives/*.deb /var/cache/apt/archives/partial/*.deb /var/cache/apt/*.bin || true"; };' >> /etc/apt/apt.conf.d/docker-clean 	&& echo 'Dir::Cache::pkgcache ""; Dir::Cache::srcpkgcache "";' >> /etc/apt/apt.conf.d/docker-clean 		&& echo 'Acquire::Languages "none";' > /etc/apt/apt.conf.d/docker-no-languages 		&& echo 'Acquire::GzipIndexes "true"; Acquire::CompressionTypes::Order:: "gz";' > /etc/apt/apt.conf.d/docker-gzip-indexes 		&& echo 'Apt::AutoRemove::SuggestsImportant "false";' > /etc/apt/apt.conf.d/docker-autoremove-suggests
# Wed, 07 Mar 2018 14:15:39 GMT
RUN rm -rf /var/lib/apt/lists/*
# Wed, 07 Mar 2018 14:15:40 GMT
RUN sed -i 's/^#\s*\(deb.*universe\)$/\1/g' /etc/apt/sources.list
# Wed, 07 Mar 2018 14:15:40 GMT
RUN mkdir -p /run/systemd && echo 'docker' > /run/systemd/container
# Wed, 07 Mar 2018 14:15:41 GMT
CMD ["/bin/bash"]
# Wed, 07 Mar 2018 14:34:08 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Wed, 07 Mar 2018 14:34:09 GMT
RUN set -ex; 	if ! command -v gpg > /dev/null; then 		apt-get update; 		apt-get install -y --no-install-recommends 			gnupg 			dirmngr 		; 		rm -rf /var/lib/apt/lists/*; 	fi
```

-	Layers:
	-	`sha256:0f6eb7d12e800009983e16b6f6c0a3de1ef520843ccce216de24f526637c049d`  
		Last Modified: Wed, 07 Mar 2018 14:16:21 GMT  
		Size: 39.0 MB (38972314 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c196638920379d9de85b4b285467a6218283aab953e74809b4743521803ef558`  
		Last Modified: Wed, 07 Mar 2018 14:16:15 GMT  
		Size: 841.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:54e34821a0806797acbbb0315cb2ee6508ec7a147e9691a9412de80bbb33a464`  
		Last Modified: Wed, 07 Mar 2018 14:16:16 GMT  
		Size: 538.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:02e8174dc25f68a73b6154e06a2cf8d5b8a238f62bc483d620eb3ba575ba0dc0`  
		Last Modified: Wed, 07 Mar 2018 14:16:14 GMT  
		Size: 855.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:334aca96d57386fe0bce7ebd11afeda51d8aa8a447118b7f29c595537e6f8f1f`  
		Last Modified: Wed, 07 Mar 2018 14:16:15 GMT  
		Size: 163.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f98f585f61c09b55ff9266d5fdedd1a9550061e1f72bce0ef8e3cf01253e5e9b`  
		Last Modified: Wed, 07 Mar 2018 14:51:06 GMT  
		Size: 5.7 MB (5743146 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

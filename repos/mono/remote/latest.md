## `mono:latest`

```console
$ docker pull mono@sha256:7eb698a27f6de28ffdc65b9e8b29282b10ee93bf3e0c1622c2d1fbada4af87ff
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm64 variant v8
	-	linux; 386

### `mono:latest` - linux; amd64

```console
$ docker pull mono@sha256:86b874309abb9e292c361e12a68f5033f7bfa68c8ffc32a6b8950466926564b6
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **174.6 MB (174624749 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:8f90d81585b35567261136b5f2e96fe9b8da4e5468974c32ccba0207aa2e0ac6`
-	Default Command: `["bash"]`

```dockerfile
# Tue, 13 Mar 2018 21:58:13 GMT
ADD file:080bac9a2cdcc70ad61e50045a26172f0e1acfd3a26360cb86b6e26a3307b2e1 in / 
# Tue, 13 Mar 2018 21:58:13 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 07:21:47 GMT
ENV MONO_VERSION=5.8.0.127
# Wed, 14 Mar 2018 07:21:54 GMT
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
# Wed, 14 Mar 2018 07:23:13 GMT
RUN echo "deb http://download.mono-project.com/repo/debian stable-jessie/snapshots/$MONO_VERSION main" > /etc/apt/sources.list.d/mono-official-stable.list   && apt-get update   && apt-get install -y mono-runtime   && rm -rf /var/lib/apt/lists/* /tmp/*
# Wed, 14 Mar 2018 07:33:45 GMT
RUN apt-get update   && apt-get install -y binutils curl mono-devel ca-certificates-mono fsharp mono-vbnc nuget referenceassemblies-pcl   && rm -rf /var/lib/apt/lists/* /tmp/*
```

-	Layers:
	-	`sha256:b0568b191983bc2844b2fdb48aeefa72452931bfead0a87e0515bfc602ea3b0c`  
		Last Modified: Tue, 13 Mar 2018 22:45:19 GMT  
		Size: 30.1 MB (30122402 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f41fd5726edd9f3f1977b65a4821afb616d239e3319df8be009446488f7d4ce3`  
		Last Modified: Wed, 14 Mar 2018 07:37:01 GMT  
		Size: 2.1 KB (2068 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a6be731cda004b97c2050c943945d71afc8ad94d592dc429aaa3924191d1a632`  
		Last Modified: Wed, 14 Mar 2018 07:37:11 GMT  
		Size: 27.4 MB (27362503 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ead69961751b24ab2d3dd7c5de6cef3032cbb60805a2b74631e97c3cf20581fc`  
		Last Modified: Wed, 14 Mar 2018 07:41:46 GMT  
		Size: 117.1 MB (117137776 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mono:latest` - linux; arm64 variant v8

```console
$ docker pull mono@sha256:9c3bce310eaabae961419780138801c92ace40bbb58f576e337f147389d2fb03
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **168.8 MB (168760444 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:abb6eb80e935bf4b4486a8046d62c2ba170d2b9fc06fdf99f7a25f7740b70e49`
-	Default Command: `["bash"]`

```dockerfile
# Wed, 14 Mar 2018 17:25:26 GMT
ADD file:0012468f66c7e5b0efd7217a1f29f5044d4dce5a19dcd39786aa7573bc927763 in / 
# Wed, 14 Mar 2018 17:25:26 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 21:53:54 GMT
ENV MONO_VERSION=5.8.0.127
# Wed, 14 Mar 2018 21:53:59 GMT
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
# Wed, 14 Mar 2018 21:55:50 GMT
RUN echo "deb http://download.mono-project.com/repo/debian stable-jessie/snapshots/$MONO_VERSION main" > /etc/apt/sources.list.d/mono-official-stable.list   && apt-get update   && apt-get install -y mono-runtime   && rm -rf /var/lib/apt/lists/* /tmp/*
# Wed, 14 Mar 2018 22:09:14 GMT
RUN apt-get update   && apt-get install -y binutils curl mono-devel ca-certificates-mono fsharp mono-vbnc nuget referenceassemblies-pcl   && rm -rf /var/lib/apt/lists/* /tmp/*
```

-	Layers:
	-	`sha256:784b6f32f75d9222c618727f66027b44ffa35120fc128790dfce4d1070befc90`  
		Last Modified: Wed, 14 Mar 2018 17:39:37 GMT  
		Size: 27.5 MB (27488177 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d0b6b1367b2d1c9afa214a230ea52e7bae7b50e6c2f4284b3fd7015beb8f1754`  
		Last Modified: Wed, 14 Mar 2018 22:16:29 GMT  
		Size: 2.1 KB (2067 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3baa15e7a3fae65ce6bf6d31d2d1a973d2545cf410b81d9d9340c4f3062abc9`  
		Last Modified: Wed, 14 Mar 2018 22:16:40 GMT  
		Size: 26.3 MB (26258233 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:90485d367026a123593f0b38e0742b10df0a9f6179acffb54a994d6f72a76428`  
		Last Modified: Wed, 14 Mar 2018 22:20:13 GMT  
		Size: 115.0 MB (115011967 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `mono:latest` - linux; 386

```console
$ docker pull mono@sha256:d7c9568f926aa763dbcc613d63827a9558e25cd3617f670fb3deb07442ce1ff7
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **176.8 MB (176848161 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c35810e1d40a00dd235ed947b13e6457a629cea1439a5f0471775a4eb136c64e`
-	Default Command: `["bash"]`

```dockerfile
# Thu, 15 Feb 2018 15:10:21 GMT
ADD file:d01127592c252b8d04a3bc643ddd1053a3e9cd036c81aa31b53bf3f51b542f6a in / 
# Thu, 15 Feb 2018 15:10:21 GMT
CMD ["bash"]
# Tue, 27 Feb 2018 02:02:15 GMT
ENV MONO_VERSION=5.8.0.127
# Tue, 27 Feb 2018 02:02:26 GMT
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
# Tue, 27 Feb 2018 02:03:33 GMT
RUN echo "deb http://download.mono-project.com/repo/debian stable-jessie/snapshots/$MONO_VERSION main" > /etc/apt/sources.list.d/mono-official-stable.list   && apt-get update   && apt-get install -y mono-runtime   && rm -rf /var/lib/apt/lists/* /tmp/*
# Tue, 27 Feb 2018 02:09:28 GMT
RUN apt-get update   && apt-get install -y binutils curl mono-devel ca-certificates-mono fsharp mono-vbnc nuget referenceassemblies-pcl   && rm -rf /var/lib/apt/lists/* /tmp/*
```

-	Layers:
	-	`sha256:2c3a67c6c38b2cc7ef92c7d27dfe86398e5a7297b5b0e03d825a82312b60bf9a`  
		Last Modified: Thu, 15 Feb 2018 00:53:43 GMT  
		Size: 30.3 MB (30273198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f72821c254faa67c4e9c36b9aa8d9c34d88984036cd0d4cd776a83af2c3e1f93`  
		Last Modified: Tue, 27 Feb 2018 02:29:31 GMT  
		Size: 2.1 KB (2069 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e63759fd1c514ea99227042c8db724ab962baa81d5b4a97c4f3eb45ad7875857`  
		Last Modified: Tue, 27 Feb 2018 02:29:42 GMT  
		Size: 29.1 MB (29135824 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:64310fe25d5665f939a1a8e651bad1b34ac87f1bc0fca6b6017e514697e3e2b1`  
		Last Modified: Tue, 27 Feb 2018 03:00:55 GMT  
		Size: 117.4 MB (117437070 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

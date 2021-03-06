## `openjdk:9-windowsservercore`

```console
$ docker pull openjdk@sha256:77d31425d981b72fd4d902a1a646846a96388d80fff6ccf5911224b6e49b7291
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	windows version 10.0.14393.2068; amd64
	-	windows version 10.0.16299.248; amd64

### `openjdk:9-windowsservercore` - windows version 10.0.14393.2068; amd64

```console
$ docker pull openjdk@sha256:70a4a289e57d28e51969078dc6fdf5ad4324ce53945a52cf5b518b89e7c52b07
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.6 GB (5579598096 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0655853da435f69dd8a90f4767ac1feffde16b8de9501a85fa0e5271294ccef3`
-	Default Command: `["jshell"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Tue, 13 Dec 2016 10:53:31 GMT
RUN Apply image 10.0.14393.0
# Tue, 13 Feb 2018 19:44:02 GMT
RUN Install update 10.0.14393.2068
# Wed, 14 Feb 2018 03:21:40 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Wed, 14 Feb 2018 10:02:55 GMT
ENV JAVA_HOME=C:\ojdkbuild
# Wed, 14 Feb 2018 10:04:13 GMT
RUN $newPath = ('{0}\bin;{1}' -f $env:JAVA_HOME, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Wed, 14 Feb 2018 10:04:13 GMT
ENV JAVA_VERSION=9.0.4
# Wed, 14 Feb 2018 10:04:14 GMT
ENV JAVA_OJDKBUILD_VERSION=9.0.4-1
# Wed, 14 Feb 2018 10:04:15 GMT
ENV JAVA_OJDKBUILD_ZIP=java-9-openjdk-9.0.4-1.b11.ojdkbuild.windows.x86_64.zip
# Wed, 14 Feb 2018 10:04:16 GMT
ENV JAVA_OJDKBUILD_SHA256=1333ab5bccc20e9043f0593b001825cbfa141f0e0c850d877af6b8e2c990cb47
# Wed, 14 Feb 2018 10:06:27 GMT
RUN $url = ('https://github.com/ojdkbuild/ojdkbuild/releases/download/{0}/{1}' -f $env:JAVA_OJDKBUILD_VERSION, $env:JAVA_OJDKBUILD_ZIP); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'ojdkbuild.zip'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $env:JAVA_OJDKBUILD_SHA256); 	if ((Get-FileHash ojdkbuild.zip -Algorithm sha256).Hash -ne $env:JAVA_OJDKBUILD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive ojdkbuild.zip -DestinationPath C:\; 		Write-Host 'Renaming ...'; 	Move-Item 		-Path ('C:\{0}' -f ($env:JAVA_OJDKBUILD_ZIP -Replace '.zip$', '')) 		-Destination $env:JAVA_HOME 	; 		Write-Host 'Verifying install ...'; 	Write-Host '  java -version'; java -version; 	Write-Host '  javac -version'; javac -version; 		Write-Host 'Removing ...'; 	Remove-Item ojdkbuild.zip -Force; 		Write-Host 'Complete.';
# Wed, 14 Feb 2018 10:06:29 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Last Modified: Tue, 13 Dec 2016 10:53:31 GMT  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:cfb27c9ba25f60372361ea8779c927f066c385b6339e29fda5c739feb3163686`  
		Last Modified: Tue, 13 Feb 2018 19:44:02 GMT  
		Size: 1.3 GB (1308156033 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:8611b5f5c0763027c0888bf4535b5f42b6c1a8f72d264baea9e7362a4907c2c3`  
		Last Modified: Wed, 14 Feb 2018 04:43:58 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b2bf3591de3ac4ce8aafac13ba82567a7ae73a7dbd57b90700d9af024e02cee`  
		Last Modified: Wed, 14 Feb 2018 10:19:21 GMT  
		Size: 1.2 KB (1201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c76230127daeeca83bdad7b0383493b1bc3db4d0897f9b2b3081249759abec51`  
		Last Modified: Wed, 14 Feb 2018 10:19:23 GMT  
		Size: 4.9 MB (4933056 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5889a9f550236cbfea4b6d87d65e61499fc7d4041a9aae54b119643a2dcaf012`  
		Last Modified: Wed, 14 Feb 2018 10:19:21 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38a2f98cda06d9f547c4fd77653ec8cb798262635ce564b9900f303dea7eddc5`  
		Last Modified: Wed, 14 Feb 2018 10:19:19 GMT  
		Size: 1.2 KB (1203 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40c0786cca21f70cb96dbafed5b5e7c8103968a2782ed63523958cc19ec813a9`  
		Last Modified: Wed, 14 Feb 2018 10:19:19 GMT  
		Size: 1.2 KB (1201 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:38b43057573362a901eedb2bd6ea0c5c90f84c971c46a2685ebfc6a8b5a922ad`  
		Last Modified: Wed, 14 Feb 2018 10:19:19 GMT  
		Size: 1.2 KB (1193 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e6439c53f178e60b7827f781611fc9f8f49d067e74a730e7e34c59cf1aaa58a5`  
		Last Modified: Wed, 14 Feb 2018 10:19:42 GMT  
		Size: 196.5 MB (196514725 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:142c09ab5ed34257e2c78c501319728197be00d8bfe73aebc47dd2b01274ce24`  
		Last Modified: Wed, 14 Feb 2018 10:19:19 GMT  
		Size: 1.2 KB (1198 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `openjdk:9-windowsservercore` - windows version 10.0.16299.248; amd64

```console
$ docker pull openjdk@sha256:035fbd5ac0fd6919672459c614158b2d2b0408cb9adecd7387a2faa3aa86c017
```

-	Docker Version: 17.06.1-ee-2
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **3.2 GB (3216349462 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:84110bd2f90a0863f1d235dfa5391a7a21ba1104bc9978a0420ac445b1afd402`
-	Default Command: `["jshell"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]`

```dockerfile
# Fri, 29 Sep 2017 14:43:28 GMT
RUN Apply image 10.0.16299.15
# Mon, 12 Feb 2018 05:08:44 GMT
RUN Install update 10.0.16299.248
# Wed, 14 Feb 2018 03:31:57 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';]
# Wed, 14 Feb 2018 10:06:38 GMT
ENV JAVA_HOME=C:\ojdkbuild
# Wed, 14 Feb 2018 10:08:40 GMT
RUN $newPath = ('{0}\bin;{1}' -f $env:JAVA_HOME, $env:PATH); 	Write-Host ('Updating PATH: {0}' -f $newPath); 	setx /M PATH $newPath;
# Wed, 14 Feb 2018 10:08:41 GMT
ENV JAVA_VERSION=9.0.4
# Wed, 14 Feb 2018 10:08:42 GMT
ENV JAVA_OJDKBUILD_VERSION=9.0.4-1
# Wed, 14 Feb 2018 10:08:43 GMT
ENV JAVA_OJDKBUILD_ZIP=java-9-openjdk-9.0.4-1.b11.ojdkbuild.windows.x86_64.zip
# Wed, 14 Feb 2018 10:08:44 GMT
ENV JAVA_OJDKBUILD_SHA256=1333ab5bccc20e9043f0593b001825cbfa141f0e0c850d877af6b8e2c990cb47
# Wed, 14 Feb 2018 10:10:49 GMT
RUN $url = ('https://github.com/ojdkbuild/ojdkbuild/releases/download/{0}/{1}' -f $env:JAVA_OJDKBUILD_VERSION, $env:JAVA_OJDKBUILD_ZIP); 	Write-Host ('Downloading {0} ...' -f $url); 	Invoke-WebRequest -Uri $url -OutFile 'ojdkbuild.zip'; 	Write-Host ('Verifying sha256 ({0}) ...' -f $env:JAVA_OJDKBUILD_SHA256); 	if ((Get-FileHash ojdkbuild.zip -Algorithm sha256).Hash -ne $env:JAVA_OJDKBUILD_SHA256) { 		Write-Host 'FAILED!'; 		exit 1; 	}; 		Write-Host 'Expanding ...'; 	Expand-Archive ojdkbuild.zip -DestinationPath C:\; 		Write-Host 'Renaming ...'; 	Move-Item 		-Path ('C:\{0}' -f ($env:JAVA_OJDKBUILD_ZIP -Replace '.zip$', '')) 		-Destination $env:JAVA_HOME 	; 		Write-Host 'Verifying install ...'; 	Write-Host '  java -version'; java -version; 	Write-Host '  javac -version'; javac -version; 		Write-Host 'Removing ...'; 	Remove-Item ojdkbuild.zip -Force; 		Write-Host 'Complete.';
# Wed, 14 Feb 2018 10:10:50 GMT
CMD ["jshell"]
```

-	Layers:
	-	`sha256:5847a47b8593f7c39aa5e3db09e50b76d42aa8898c0440c70cc9c69747d4c479`  
		Last Modified: Tue, 17 Oct 2017 15:51:05 GMT  
		Size: 2.3 GB (2274300585 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:bb504a9304958e903c60656a737272249571ee918bcdc7a9024d802898a187a2`  
		Last Modified: Tue, 13 Feb 2018 21:04:02 GMT  
		Size: 741.2 MB (741177838 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:0d60bc5daa3667e432684b61a1df89fd1f6e92e6a95029d9abf1a5aad8cf0864`  
		Last Modified: Wed, 14 Feb 2018 04:45:53 GMT  
		Size: 1.2 KB (1206 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0c590c494a8eef87aa4497444ff6ca680c81c3f7672ebe45598ff509d43a01f5`  
		Last Modified: Wed, 14 Feb 2018 10:20:09 GMT  
		Size: 1.2 KB (1174 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:701bef3b2d01e8c14e581962761a25ca788b9aef91ed3091b4cf60ea2730c47d`  
		Last Modified: Wed, 14 Feb 2018 10:20:10 GMT  
		Size: 4.6 MB (4627995 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e14a2005cefb5c5ce683002e1f136045a4a1d64673ca804a1e3e4174c108392`  
		Last Modified: Wed, 14 Feb 2018 10:20:08 GMT  
		Size: 1.2 KB (1199 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea50491702cf0f1a893a5d130826726c642fd8bd7a888002b18d9c76a4dfe9f2`  
		Last Modified: Wed, 14 Feb 2018 10:20:06 GMT  
		Size: 1.2 KB (1195 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:43085a58bae3b95ae94886517089899d66c189cc6ace906c799f1f7717069991`  
		Last Modified: Wed, 14 Feb 2018 10:20:06 GMT  
		Size: 1.2 KB (1202 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e9d5c93b5ddc47e946e0fbb104c4f950d68a9612c37ee7c765e28074574cd84`  
		Last Modified: Wed, 14 Feb 2018 10:20:05 GMT  
		Size: 1.2 KB (1196 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a38ff65ce50c8192bb0143a48bc5c8b42df710ece5840d4622e4ca2be7849e99`  
		Last Modified: Wed, 14 Feb 2018 10:20:28 GMT  
		Size: 196.2 MB (196234672 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:74c5a2b7379369b621709cc5c2bd581b356209b2c8ec9e63ab05f9604584814b`  
		Last Modified: Wed, 14 Feb 2018 10:20:05 GMT  
		Size: 1.2 KB (1200 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

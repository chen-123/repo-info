## `tomcat:9-jre9-slim`

```console
$ docker pull tomcat@sha256:584f62e15d885e83767ccfcd328f88bc60fa7af82e12ea528a838befb2b42c8f
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64
	-	linux; arm variant v5
	-	linux; arm variant v7
	-	linux; arm64 variant v8
	-	linux; ppc64le
	-	linux; s390x

### `tomcat:9-jre9-slim` - linux; amd64

```console
$ docker pull tomcat@sha256:a35b910efb7e5167873e94a723f3edc38e8190210c086d28083a276b8ab6acbc
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **114.4 MB (114369084 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3c277456e174379455e27e0d6358b0ac39c4e178178e1f846940f44a083b694c`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Tue, 13 Mar 2018 22:21:43 GMT
ADD file:abc56f5a5510633481f0de7469b312f4f4cdcfbbe92bf1d7bddb5d716a2a5820 in / 
# Tue, 13 Mar 2018 22:21:44 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 09:56:18 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 10:30:14 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 10:30:15 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 14 Mar 2018 10:30:16 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 14 Mar 2018 10:30:16 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 14 Mar 2018 10:30:16 GMT
ENV JAVA_VERSION=9.0.1+11
# Wed, 14 Mar 2018 10:30:16 GMT
ENV JAVA_DEBIAN_VERSION=9.0.1+11-1
# Wed, 14 Mar 2018 10:30:42 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-9-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 15 Mar 2018 14:27:47 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Thu, 15 Mar 2018 14:27:47 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 15 Mar 2018 14:27:48 GMT
RUN mkdir -p "$CATALINA_HOME"
# Thu, 15 Mar 2018 14:27:49 GMT
WORKDIR /usr/local/tomcat
# Thu, 15 Mar 2018 14:27:49 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Thu, 15 Mar 2018 14:27:49 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Thu, 15 Mar 2018 14:27:49 GMT
ENV OPENSSL_VERSION=1.1.0f-3+deb9u1
# Thu, 15 Mar 2018 14:27:50 GMT
RUN set -ex; 	currentVersion="$(dpkg-query --show --showformat '${Version}\n' openssl)"; 	if dpkg --compare-versions "$currentVersion" '<<' "$OPENSSL_VERSION"; then 		if ! grep -q stretch /etc/apt/sources.list; then 			{ 				echo 'deb http://deb.debian.org/debian stretch main'; 				echo 'deb http://security.debian.org stretch/updates main'; 				echo 'deb http://deb.debian.org/debian stretch-updates main'; 			} > /etc/apt/sources.list.d/stretch.list; 			{ 				echo 'Package: *'; 				echo 'Pin: release n=stretch*'; 				echo 'Pin-Priority: -10'; 				echo; 				echo 'Package: openssl libssl*'; 				echo "Pin: version $OPENSSL_VERSION"; 				echo 'Pin-Priority: 990'; 			} > /etc/apt/preferences.d/stretch-openssl; 		fi; 		apt-get update; 		apt-get install -y --no-install-recommends openssl="$OPENSSL_VERSION"; 		rm -rf /var/lib/apt/lists/*; 	fi
# Thu, 15 Mar 2018 14:27:57 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 	&& rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 14:37:40 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Thu, 15 Mar 2018 14:37:40 GMT
ENV TOMCAT_MAJOR=9
# Thu, 15 Mar 2018 14:37:40 GMT
ENV TOMCAT_VERSION=9.0.6
# Thu, 15 Mar 2018 14:37:41 GMT
ENV TOMCAT_SHA1=8cea5d0701773da1a0b2c2a6ec744b66eb8b2f34
# Thu, 15 Mar 2018 14:37:41 GMT
ENV TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz
# Thu, 15 Mar 2018 14:37:41 GMT
ENV TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc
# Thu, 15 Mar 2018 14:39:30 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 		apt-get install -y --no-install-recommends gnupg dirmngr; 		export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 		apt-get install -y --no-install-recommends wget ca-certificates; 		success=; 	for url in $TOMCAT_TGZ_URLS; do 		if wget -O tomcat.tar.gz "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		echo "$TOMCAT_SHA1 *tomcat.tar.gz" | sha1sum -c -; 		success=; 	for url in $TOMCAT_ASC_URLS; do 		if wget -O tomcat.tar.gz.asc "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz; 	tar -xvf tomcat.tar.gz --strip-components=1; 	rm bin/*.bat; 	rm tomcat.tar.gz*; 	rm -rf "$GNUPGHOME"; 		nativeBuildDir="$(mktemp -d)"; 	tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1; 	apt-get install -y --no-install-recommends 		dpkg-dev 		gcc 		libapr1-dev 		libssl-dev 		make 		"openjdk-${JAVA_VERSION%%[.~bu-]*}-jdk=$JAVA_DEBIAN_VERSION" 	; 	( 		export CATALINA_HOME="$PWD"; 		cd "$nativeBuildDir/native"; 		gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 		./configure 			--build="$gnuArch" 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes; 		make -j "$(nproc)"; 		make install; 	); 	rm -rf "$nativeBuildDir"; 	rm bin/tomcat-native.tar.gz; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 	rm -rf /var/lib/apt/lists/*; 		find ./bin/ -name '*.sh' -exec sed -ri 's|^#!/bin/sh$|#!/usr/bin/env bash|' '{}' +
# Thu, 15 Mar 2018 14:39:35 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Thu, 15 Mar 2018 14:39:35 GMT
EXPOSE 8080/tcp
# Thu, 15 Mar 2018 14:39:35 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:8d602e635a7063b254ddcd64997153b2e8f74c29ff4648089ae116a4ca3ea8e3`  
		Last Modified: Tue, 13 Mar 2018 22:50:19 GMT  
		Size: 25.7 MB (25713113 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:45b0cb5bfff7921055b3160e463c0cbbd0da8804c54c0e81870e32789de17696`  
		Last Modified: Wed, 14 Mar 2018 11:50:29 GMT  
		Size: 460.3 KB (460326 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:31aaf5b382af90e713d7581c352ac81060358c641b90a3708b45268486ae3911`  
		Last Modified: Wed, 14 Mar 2018 12:30:26 GMT  
		Size: 239.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5713db526a481e662cb137cca84372e8433d562ce47cab6f445157cd465a6caf`  
		Last Modified: Wed, 14 Mar 2018 12:30:26 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bb22346cd0b6d5a8a0d3d1f34b2605d322b127db6f2f817040e41ac8ec7fbb4e`  
		Last Modified: Wed, 14 Mar 2018 12:30:40 GMT  
		Size: 76.6 MB (76556214 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1e1611d189327af5878f6c2ba3f55f6ebd43c6fe18484997199e3d6973ce5d3e`  
		Last Modified: Thu, 15 Mar 2018 14:54:02 GMT  
		Size: 137.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1afaa4073e04587d334ffa5be597c730f16a009eccad7b5d9d9c879418fd1d96`  
		Last Modified: Thu, 15 Mar 2018 14:54:02 GMT  
		Size: 409.6 KB (409607 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:eba3910e44e1634c9109cb3f44e5a51a41d02f21b6ed43c3fa1d2894a9adb382`  
		Last Modified: Thu, 15 Mar 2018 14:59:19 GMT  
		Size: 11.2 MB (11229153 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0cdb0249ed4a07cd02ca63ca3a6b43e626654d1a49eb67075584b94890c67706`  
		Last Modified: Thu, 15 Mar 2018 14:59:16 GMT  
		Size: 164.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomcat:9-jre9-slim` - linux; arm variant v5

```console
$ docker pull tomcat@sha256:20ce495247462d6e6e612d3ba99d60540f6173a5cf17c8832283c71fe966db63
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **97.6 MB (97569989 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:6ab1c2d0b9b520549bbe6c4316508ef00fa08b6e49f5d811e74664b1bcd9ceb6`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 14 Mar 2018 19:59:20 GMT
ADD file:b829fe1b85a76eaae255627baf7572a89310e31a86d94c40353cdf5184a08296 in / 
# Wed, 14 Mar 2018 19:59:21 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 22:37:38 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 22:42:18 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 22:42:19 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 14 Mar 2018 22:42:20 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 14 Mar 2018 22:42:20 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 14 Mar 2018 22:42:20 GMT
ENV JAVA_VERSION=9.0.1+11
# Wed, 14 Mar 2018 22:42:21 GMT
ENV JAVA_DEBIAN_VERSION=9.0.1+11-1
# Wed, 14 Mar 2018 22:43:01 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-9-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 15 Mar 2018 02:05:49 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Thu, 15 Mar 2018 02:05:50 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 15 Mar 2018 02:05:51 GMT
RUN mkdir -p "$CATALINA_HOME"
# Thu, 15 Mar 2018 02:05:51 GMT
WORKDIR /usr/local/tomcat
# Thu, 15 Mar 2018 02:05:51 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Thu, 15 Mar 2018 02:06:00 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Thu, 15 Mar 2018 02:06:00 GMT
ENV OPENSSL_VERSION=1.1.0f-3+deb9u1
# Thu, 15 Mar 2018 02:06:01 GMT
RUN set -ex; 	currentVersion="$(dpkg-query --show --showformat '${Version}\n' openssl)"; 	if dpkg --compare-versions "$currentVersion" '<<' "$OPENSSL_VERSION"; then 		if ! grep -q stretch /etc/apt/sources.list; then 			{ 				echo 'deb http://deb.debian.org/debian stretch main'; 				echo 'deb http://security.debian.org stretch/updates main'; 				echo 'deb http://deb.debian.org/debian stretch-updates main'; 			} > /etc/apt/sources.list.d/stretch.list; 			{ 				echo 'Package: *'; 				echo 'Pin: release n=stretch*'; 				echo 'Pin-Priority: -10'; 				echo; 				echo 'Package: openssl libssl*'; 				echo "Pin: version $OPENSSL_VERSION"; 				echo 'Pin-Priority: 990'; 			} > /etc/apt/preferences.d/stretch-openssl; 		fi; 		apt-get update; 		apt-get install -y --no-install-recommends openssl="$OPENSSL_VERSION"; 		rm -rf /var/lib/apt/lists/*; 	fi
# Thu, 15 Mar 2018 02:06:10 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 	&& rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 02:13:57 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Thu, 15 Mar 2018 02:13:57 GMT
ENV TOMCAT_MAJOR=9
# Thu, 15 Mar 2018 02:13:58 GMT
ENV TOMCAT_VERSION=9.0.6
# Thu, 15 Mar 2018 02:13:58 GMT
ENV TOMCAT_SHA1=8cea5d0701773da1a0b2c2a6ec744b66eb8b2f34
# Thu, 15 Mar 2018 02:13:58 GMT
ENV TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz
# Thu, 15 Mar 2018 02:13:58 GMT
ENV TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc
# Thu, 15 Mar 2018 02:15:29 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 		apt-get install -y --no-install-recommends gnupg dirmngr; 		export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 		apt-get install -y --no-install-recommends wget ca-certificates; 		success=; 	for url in $TOMCAT_TGZ_URLS; do 		if wget -O tomcat.tar.gz "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		echo "$TOMCAT_SHA1 *tomcat.tar.gz" | sha1sum -c -; 		success=; 	for url in $TOMCAT_ASC_URLS; do 		if wget -O tomcat.tar.gz.asc "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz; 	tar -xvf tomcat.tar.gz --strip-components=1; 	rm bin/*.bat; 	rm tomcat.tar.gz*; 	rm -rf "$GNUPGHOME"; 		nativeBuildDir="$(mktemp -d)"; 	tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1; 	apt-get install -y --no-install-recommends 		dpkg-dev 		gcc 		libapr1-dev 		libssl-dev 		make 		"openjdk-${JAVA_VERSION%%[.~bu-]*}-jdk=$JAVA_DEBIAN_VERSION" 	; 	( 		export CATALINA_HOME="$PWD"; 		cd "$nativeBuildDir/native"; 		gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 		./configure 			--build="$gnuArch" 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes; 		make -j "$(nproc)"; 		make install; 	); 	rm -rf "$nativeBuildDir"; 	rm bin/tomcat-native.tar.gz; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 	rm -rf /var/lib/apt/lists/*; 		find ./bin/ -name '*.sh' -exec sed -ri 's|^#!/bin/sh$|#!/usr/bin/env bash|' '{}' +
# Thu, 15 Mar 2018 02:15:39 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Thu, 15 Mar 2018 02:15:41 GMT
EXPOSE 8080/tcp
# Thu, 15 Mar 2018 02:15:42 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:1df428c58793052c39aa67c5a0cfc437c4f5e97e12915970ffa3b5a637915c81`  
		Last Modified: Wed, 14 Mar 2018 20:10:52 GMT  
		Size: 23.7 MB (23719570 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:41ea34fa7879bc512ea22a1ff5fd2caeccec4a4a30a175ae662a07c22e57532a`  
		Last Modified: Wed, 14 Mar 2018 23:01:39 GMT  
		Size: 453.8 KB (453792 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3d53ef6ceaeefa22395981d0871593abdf315d62946258906c10c78378424bd2`  
		Last Modified: Wed, 14 Mar 2018 23:01:38 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a94ee72e00db1ec221beadb93954960dbae55a4101ae2563b8b4f26818118ce`  
		Last Modified: Wed, 14 Mar 2018 23:01:37 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9482aa60387089158551c617e09219bff9b940a41b947f564f942f8d4d3e9e8`  
		Last Modified: Wed, 14 Mar 2018 23:01:55 GMT  
		Size: 61.9 MB (61915409 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a2ef73ee4adfb3b4bf61fba07f19557eec053b2fe453b48c51ae72f08d6181b`  
		Last Modified: Thu, 15 Mar 2018 02:28:27 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6617b16977210ad6ed2a24ffffd8c8b44169b6d318a8e7aee340db532abad855`  
		Last Modified: Thu, 15 Mar 2018 02:28:27 GMT  
		Size: 393.3 KB (393282 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:847e4a59e4d0a53765ccabc9b6f6983389fdba6ead2e403d44de9f4b0108afe7`  
		Last Modified: Thu, 15 Mar 2018 02:31:53 GMT  
		Size: 11.1 MB (11087264 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:67be44629ce6cada97eb0738e23e063fe8c23842653b8e9264aaed06a989dd7f`  
		Last Modified: Thu, 15 Mar 2018 02:31:51 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomcat:9-jre9-slim` - linux; arm variant v7

```console
$ docker pull tomcat@sha256:2085634a632edb4ebf7d974a0a39ee0a1fb013e8c93db12ccd321d4a8fd22dc5
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **97.4 MB (97448698 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ac7b8d65f0f14a1cbf752e156a3f8f6ff5be80c8babcbc1069957c40bf3b364e`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 14 Mar 2018 12:30:51 GMT
ADD file:01a57c20f154d841f3d0067187339035634947891cdd63b93cf26c052ccec8a9 in / 
# Wed, 14 Mar 2018 12:30:52 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 13:49:45 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 13:56:59 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 13:57:00 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 14 Mar 2018 13:57:11 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 14 Mar 2018 13:57:11 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 14 Mar 2018 13:57:12 GMT
ENV JAVA_VERSION=9.0.1+11
# Wed, 14 Mar 2018 13:57:12 GMT
ENV JAVA_DEBIAN_VERSION=9.0.1+11-1
# Wed, 14 Mar 2018 13:57:43 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-9-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 14 Mar 2018 18:26:36 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Wed, 14 Mar 2018 18:26:36 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 14 Mar 2018 18:26:37 GMT
RUN mkdir -p "$CATALINA_HOME"
# Wed, 14 Mar 2018 18:26:38 GMT
WORKDIR /usr/local/tomcat
# Wed, 14 Mar 2018 18:26:38 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Wed, 14 Mar 2018 18:26:38 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Wed, 14 Mar 2018 18:26:39 GMT
ENV OPENSSL_VERSION=1.1.0f-3+deb9u1
# Wed, 14 Mar 2018 18:26:40 GMT
RUN set -ex; 	currentVersion="$(dpkg-query --show --showformat '${Version}\n' openssl)"; 	if dpkg --compare-versions "$currentVersion" '<<' "$OPENSSL_VERSION"; then 		if ! grep -q stretch /etc/apt/sources.list; then 			{ 				echo 'deb http://deb.debian.org/debian stretch main'; 				echo 'deb http://security.debian.org stretch/updates main'; 				echo 'deb http://deb.debian.org/debian stretch-updates main'; 			} > /etc/apt/sources.list.d/stretch.list; 			{ 				echo 'Package: *'; 				echo 'Pin: release n=stretch*'; 				echo 'Pin-Priority: -10'; 				echo; 				echo 'Package: openssl libssl*'; 				echo "Pin: version $OPENSSL_VERSION"; 				echo 'Pin-Priority: 990'; 			} > /etc/apt/preferences.d/stretch-openssl; 		fi; 		apt-get update; 		apt-get install -y --no-install-recommends openssl="$OPENSSL_VERSION"; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 14 Mar 2018 18:26:46 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 18:33:32 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Wed, 14 Mar 2018 18:33:33 GMT
ENV TOMCAT_MAJOR=9
# Wed, 14 Mar 2018 18:33:33 GMT
ENV TOMCAT_VERSION=9.0.6
# Wed, 14 Mar 2018 18:33:34 GMT
ENV TOMCAT_SHA1=8cea5d0701773da1a0b2c2a6ec744b66eb8b2f34
# Wed, 14 Mar 2018 18:33:34 GMT
ENV TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz
# Wed, 14 Mar 2018 18:33:35 GMT
ENV TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc
# Wed, 14 Mar 2018 18:35:02 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 		apt-get install -y --no-install-recommends gnupg dirmngr; 		export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 		apt-get install -y --no-install-recommends wget ca-certificates; 		success=; 	for url in $TOMCAT_TGZ_URLS; do 		if wget -O tomcat.tar.gz "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		echo "$TOMCAT_SHA1 *tomcat.tar.gz" | sha1sum -c -; 		success=; 	for url in $TOMCAT_ASC_URLS; do 		if wget -O tomcat.tar.gz.asc "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz; 	tar -xvf tomcat.tar.gz --strip-components=1; 	rm bin/*.bat; 	rm tomcat.tar.gz*; 	rm -rf "$GNUPGHOME"; 		nativeBuildDir="$(mktemp -d)"; 	tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1; 	apt-get install -y --no-install-recommends 		dpkg-dev 		gcc 		libapr1-dev 		libssl-dev 		make 		"openjdk-${JAVA_VERSION%%[.~bu-]*}-jdk=$JAVA_DEBIAN_VERSION" 	; 	( 		export CATALINA_HOME="$PWD"; 		cd "$nativeBuildDir/native"; 		gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 		./configure 			--build="$gnuArch" 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes; 		make -j "$(nproc)"; 		make install; 	); 	rm -rf "$nativeBuildDir"; 	rm bin/tomcat-native.tar.gz; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 	rm -rf /var/lib/apt/lists/*; 		find ./bin/ -name '*.sh' -exec sed -ri 's|^#!/bin/sh$|#!/usr/bin/env bash|' '{}' +
# Wed, 14 Mar 2018 18:35:08 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Wed, 14 Mar 2018 18:35:08 GMT
EXPOSE 8080/tcp
# Wed, 14 Mar 2018 18:35:08 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:eb4d24f57aa2e9887d736ab5ae837254043a7420798488e113011250c3d45c6b`  
		Last Modified: Wed, 14 Mar 2018 12:42:40 GMT  
		Size: 21.7 MB (21736182 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fb6632e794ba04784b0b45265566f4f18a26d40bdfdd4aa6726c2df55600f62e`  
		Last Modified: Wed, 14 Mar 2018 14:18:56 GMT  
		Size: 436.4 KB (436377 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8e62fee9928c709ea5d7c9da848769f94473ffc5f05cbc085072d2748d08a374`  
		Last Modified: Wed, 14 Mar 2018 14:28:29 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:32560089ba434ee40f6a777c55ff859bb6881157813c5da6c1fdabef6b843be5`  
		Last Modified: Wed, 14 Mar 2018 14:28:29 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8fd24bf9369ec2fa688dcf25c4089ad6df2f3f9a2f450c732f01ef26dd78c9b0`  
		Last Modified: Wed, 14 Mar 2018 14:28:45 GMT  
		Size: 63.8 MB (63835750 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8770f156949f5dae399221af669cfde921b044a72a3130a1e24531c457500b18`  
		Last Modified: Wed, 14 Mar 2018 18:51:37 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de5096c9fd8f8ac7f08721f6c7936d916529b36a2a2193470981b3166c633453`  
		Last Modified: Wed, 14 Mar 2018 18:51:37 GMT  
		Size: 383.0 KB (383027 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:20dc0e24552181322f1880b0401e676866d256765d86de798d7c89ce36844fbc`  
		Last Modified: Wed, 14 Mar 2018 18:55:08 GMT  
		Size: 11.1 MB (11056691 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:855e547da73de4b8dbc71d69462ae572016b3161427775466bc10d9afef0e65a`  
		Last Modified: Wed, 14 Mar 2018 18:55:06 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomcat:9-jre9-slim` - linux; arm64 variant v8

```console
$ docker pull tomcat@sha256:8e5b8ffc6a5d165990393604a7f56d68464527f457126a8aa3ba1e65a1a0c830
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **100.5 MB (100522765 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:3eef8fa4e22500683df907913a02d7871678b2e593ce6f0faf56fba62a1cee98`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 14 Mar 2018 17:28:31 GMT
ADD file:e02f4f3766155e52cc84a63120d6a2789b8ecbc9d3d5311e6fde66f676f7bb09 in / 
# Wed, 14 Mar 2018 17:28:32 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 19:56:09 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 20:20:33 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 20:20:40 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 14 Mar 2018 20:20:45 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 14 Mar 2018 20:20:46 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 14 Mar 2018 20:20:46 GMT
ENV JAVA_VERSION=9.0.1+11
# Wed, 14 Mar 2018 20:20:47 GMT
ENV JAVA_DEBIAN_VERSION=9.0.1+11-1
# Wed, 14 Mar 2018 20:22:07 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-9-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 15 Mar 2018 08:25:11 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Thu, 15 Mar 2018 08:25:12 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 15 Mar 2018 08:25:14 GMT
RUN mkdir -p "$CATALINA_HOME"
# Thu, 15 Mar 2018 08:25:15 GMT
WORKDIR /usr/local/tomcat
# Thu, 15 Mar 2018 08:25:16 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Thu, 15 Mar 2018 08:25:17 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Thu, 15 Mar 2018 08:25:18 GMT
ENV OPENSSL_VERSION=1.1.0f-3+deb9u1
# Thu, 15 Mar 2018 08:25:21 GMT
RUN set -ex; 	currentVersion="$(dpkg-query --show --showformat '${Version}\n' openssl)"; 	if dpkg --compare-versions "$currentVersion" '<<' "$OPENSSL_VERSION"; then 		if ! grep -q stretch /etc/apt/sources.list; then 			{ 				echo 'deb http://deb.debian.org/debian stretch main'; 				echo 'deb http://security.debian.org stretch/updates main'; 				echo 'deb http://deb.debian.org/debian stretch-updates main'; 			} > /etc/apt/sources.list.d/stretch.list; 			{ 				echo 'Package: *'; 				echo 'Pin: release n=stretch*'; 				echo 'Pin-Priority: -10'; 				echo; 				echo 'Package: openssl libssl*'; 				echo "Pin: version $OPENSSL_VERSION"; 				echo 'Pin-Priority: 990'; 			} > /etc/apt/preferences.d/stretch-openssl; 		fi; 		apt-get update; 		apt-get install -y --no-install-recommends openssl="$OPENSSL_VERSION"; 		rm -rf /var/lib/apt/lists/*; 	fi
# Thu, 15 Mar 2018 08:25:37 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 	&& rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 08:54:52 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Thu, 15 Mar 2018 08:54:53 GMT
ENV TOMCAT_MAJOR=9
# Thu, 15 Mar 2018 08:54:54 GMT
ENV TOMCAT_VERSION=9.0.6
# Thu, 15 Mar 2018 08:54:54 GMT
ENV TOMCAT_SHA1=8cea5d0701773da1a0b2c2a6ec744b66eb8b2f34
# Thu, 15 Mar 2018 08:54:55 GMT
ENV TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz
# Thu, 15 Mar 2018 08:54:56 GMT
ENV TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc
# Thu, 15 Mar 2018 09:06:53 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 		apt-get install -y --no-install-recommends gnupg dirmngr; 		export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 		apt-get install -y --no-install-recommends wget ca-certificates; 		success=; 	for url in $TOMCAT_TGZ_URLS; do 		if wget -O tomcat.tar.gz "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		echo "$TOMCAT_SHA1 *tomcat.tar.gz" | sha1sum -c -; 		success=; 	for url in $TOMCAT_ASC_URLS; do 		if wget -O tomcat.tar.gz.asc "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz; 	tar -xvf tomcat.tar.gz --strip-components=1; 	rm bin/*.bat; 	rm tomcat.tar.gz*; 	rm -rf "$GNUPGHOME"; 		nativeBuildDir="$(mktemp -d)"; 	tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1; 	apt-get install -y --no-install-recommends 		dpkg-dev 		gcc 		libapr1-dev 		libssl-dev 		make 		"openjdk-${JAVA_VERSION%%[.~bu-]*}-jdk=$JAVA_DEBIAN_VERSION" 	; 	( 		export CATALINA_HOME="$PWD"; 		cd "$nativeBuildDir/native"; 		gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 		./configure 			--build="$gnuArch" 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes; 		make -j "$(nproc)"; 		make install; 	); 	rm -rf "$nativeBuildDir"; 	rm bin/tomcat-native.tar.gz; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 	rm -rf /var/lib/apt/lists/*; 		find ./bin/ -name '*.sh' -exec sed -ri 's|^#!/bin/sh$|#!/usr/bin/env bash|' '{}' +
# Thu, 15 Mar 2018 09:06:59 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Thu, 15 Mar 2018 09:07:11 GMT
EXPOSE 8080/tcp
# Thu, 15 Mar 2018 09:07:12 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:793dde53d6e905ab81ddaae8c8ff711e51c5782e6ff5c8065a2f2017b116e00c`  
		Last Modified: Wed, 14 Mar 2018 17:43:12 GMT  
		Size: 23.1 MB (23087383 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fd912422d8771b9bce422bc6af0c49132976576aa3834e0baccfc7c50ebd2ef9`  
		Last Modified: Wed, 14 Mar 2018 21:04:08 GMT  
		Size: 445.1 KB (445107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d547b26b9f7cb3ede348dd4e8f8d68fbb9c762a4bcd74738fd220c848c542972`  
		Last Modified: Wed, 14 Mar 2018 21:22:59 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b497df78fddfa0a48758ce249e8008ee03e6e16ab3325b17130d54deacb85a1`  
		Last Modified: Wed, 14 Mar 2018 21:22:59 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8a89746f64d836370efce225af2bc61bddf83555ecc16a5639429a40ac4cd9ac`  
		Last Modified: Wed, 14 Mar 2018 21:23:38 GMT  
		Size: 65.4 MB (65375636 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:27d29c5b3f65ee66714f383538cd6ff9a31d1467b282ab110028591e5cacdab5`  
		Last Modified: Thu, 15 Mar 2018 09:21:29 GMT  
		Size: 138.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5b2445c8422f98433cab04f3215585bede25edae1be6bc655f4c9efbb1144d6c`  
		Last Modified: Thu, 15 Mar 2018 09:21:29 GMT  
		Size: 394.5 KB (394458 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e97a968f6369b536a096cf2fce93cd7c1b1caca38f02a788944bed240d94f8f5`  
		Last Modified: Thu, 15 Mar 2018 09:29:39 GMT  
		Size: 11.2 MB (11219543 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5a15fbbfb16b7f2bd7722a651c7550ee430bedc267bccabf2eaf1fdc166e4cd5`  
		Last Modified: Thu, 15 Mar 2018 09:29:36 GMT  
		Size: 132.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomcat:9-jre9-slim` - linux; ppc64le

```console
$ docker pull tomcat@sha256:a977b445dd1d7701f46c75b8a48be576b57a9b20109e34c62004218507815008
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **105.7 MB (105722468 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:623b63b550f836cc8f42f0e6a96d39166dae506d356185585ecdbf9a40557169`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 14 Mar 2018 00:33:55 GMT
ADD file:e890898916a686430a0d7cea9f16c3859f35938952b26ba20163570f64ab383c in / 
# Wed, 14 Mar 2018 00:33:57 GMT
CMD ["bash"]
# Thu, 15 Mar 2018 04:03:31 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 04:17:57 GMT
ENV LANG=C.UTF-8
# Thu, 15 Mar 2018 04:18:03 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Thu, 15 Mar 2018 04:18:08 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Thu, 15 Mar 2018 04:18:11 GMT
ENV JAVA_HOME=/docker-java-home
# Thu, 15 Mar 2018 04:18:14 GMT
ENV JAVA_VERSION=9.0.1+11
# Thu, 15 Mar 2018 04:18:16 GMT
ENV JAVA_DEBIAN_VERSION=9.0.1+11-1
# Thu, 15 Mar 2018 04:20:52 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-9-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Thu, 15 Mar 2018 14:01:08 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Thu, 15 Mar 2018 14:01:10 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Thu, 15 Mar 2018 14:01:15 GMT
RUN mkdir -p "$CATALINA_HOME"
# Thu, 15 Mar 2018 14:01:19 GMT
WORKDIR /usr/local/tomcat
# Thu, 15 Mar 2018 14:01:22 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Thu, 15 Mar 2018 14:01:23 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Thu, 15 Mar 2018 14:01:27 GMT
ENV OPENSSL_VERSION=1.1.0f-3+deb9u1
# Thu, 15 Mar 2018 14:01:32 GMT
RUN set -ex; 	currentVersion="$(dpkg-query --show --showformat '${Version}\n' openssl)"; 	if dpkg --compare-versions "$currentVersion" '<<' "$OPENSSL_VERSION"; then 		if ! grep -q stretch /etc/apt/sources.list; then 			{ 				echo 'deb http://deb.debian.org/debian stretch main'; 				echo 'deb http://security.debian.org stretch/updates main'; 				echo 'deb http://deb.debian.org/debian stretch-updates main'; 			} > /etc/apt/sources.list.d/stretch.list; 			{ 				echo 'Package: *'; 				echo 'Pin: release n=stretch*'; 				echo 'Pin-Priority: -10'; 				echo; 				echo 'Package: openssl libssl*'; 				echo "Pin: version $OPENSSL_VERSION"; 				echo 'Pin-Priority: 990'; 			} > /etc/apt/preferences.d/stretch-openssl; 		fi; 		apt-get update; 		apt-get install -y --no-install-recommends openssl="$OPENSSL_VERSION"; 		rm -rf /var/lib/apt/lists/*; 	fi
# Thu, 15 Mar 2018 14:01:54 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 	&& rm -rf /var/lib/apt/lists/*
# Thu, 15 Mar 2018 14:52:39 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Thu, 15 Mar 2018 14:52:40 GMT
ENV TOMCAT_MAJOR=9
# Thu, 15 Mar 2018 14:52:41 GMT
ENV TOMCAT_VERSION=9.0.6
# Thu, 15 Mar 2018 14:52:43 GMT
ENV TOMCAT_SHA1=8cea5d0701773da1a0b2c2a6ec744b66eb8b2f34
# Thu, 15 Mar 2018 14:52:44 GMT
ENV TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz
# Thu, 15 Mar 2018 14:52:45 GMT
ENV TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc
# Thu, 15 Mar 2018 15:13:21 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 		apt-get install -y --no-install-recommends gnupg dirmngr; 		export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 		apt-get install -y --no-install-recommends wget ca-certificates; 		success=; 	for url in $TOMCAT_TGZ_URLS; do 		if wget -O tomcat.tar.gz "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		echo "$TOMCAT_SHA1 *tomcat.tar.gz" | sha1sum -c -; 		success=; 	for url in $TOMCAT_ASC_URLS; do 		if wget -O tomcat.tar.gz.asc "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz; 	tar -xvf tomcat.tar.gz --strip-components=1; 	rm bin/*.bat; 	rm tomcat.tar.gz*; 	rm -rf "$GNUPGHOME"; 		nativeBuildDir="$(mktemp -d)"; 	tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1; 	apt-get install -y --no-install-recommends 		dpkg-dev 		gcc 		libapr1-dev 		libssl-dev 		make 		"openjdk-${JAVA_VERSION%%[.~bu-]*}-jdk=$JAVA_DEBIAN_VERSION" 	; 	( 		export CATALINA_HOME="$PWD"; 		cd "$nativeBuildDir/native"; 		gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 		./configure 			--build="$gnuArch" 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes; 		make -j "$(nproc)"; 		make install; 	); 	rm -rf "$nativeBuildDir"; 	rm bin/tomcat-native.tar.gz; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 	rm -rf /var/lib/apt/lists/*; 		find ./bin/ -name '*.sh' -exec sed -ri 's|^#!/bin/sh$|#!/usr/bin/env bash|' '{}' +
# Thu, 15 Mar 2018 15:13:26 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Thu, 15 Mar 2018 15:13:27 GMT
EXPOSE 8080/tcp
# Thu, 15 Mar 2018 15:13:29 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:b3949de4c16b03531582180df6c78e53e16851fa35f1a3ab12ac83a511cae577`  
		Last Modified: Wed, 14 Mar 2018 00:41:23 GMT  
		Size: 26.9 MB (26942453 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6ecfa491131fe3c43d09dfae52d8bf81576df7e7c5fa65cc8ca02dd14a07330c`  
		Last Modified: Thu, 15 Mar 2018 06:00:01 GMT  
		Size: 455.0 KB (454980 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:84cd6dec31efd7f104c93e0092e096437e0fd71c847ebb04861345763d94a407`  
		Last Modified: Thu, 15 Mar 2018 06:00:00 GMT  
		Size: 237.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d11873e1792eb622e309cc818dbfe177c0e164e2fd83f1b6a56413a55ec2a7c9`  
		Last Modified: Thu, 15 Mar 2018 06:00:01 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c8f4b263d3fed8005378e84e1aaeabcb9381e037a49fa96c7b04abfddbe5e806`  
		Last Modified: Thu, 15 Mar 2018 06:00:16 GMT  
		Size: 66.6 MB (66568094 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:edcf469ecf48bbd684ff47d86c0cd5e52ad2fb3b70ac08e77d1c733b22188959`  
		Last Modified: Thu, 15 Mar 2018 15:22:47 GMT  
		Size: 171.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:40dd4d5b94156eecd6b35b1d4a2be8f6c3150da4234d550fdc2dc5669ad59844`  
		Last Modified: Thu, 15 Mar 2018 15:22:48 GMT  
		Size: 406.5 KB (406494 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9b766c5053e45844a83c9df94440bb09fc5dbae01f78786fdc1863ed0324939d`  
		Last Modified: Thu, 15 Mar 2018 15:25:17 GMT  
		Size: 11.3 MB (11349775 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:de3c2bc48662367dd0238456d750c95de362ac22e4ddbe639ab9fe1d5ee2eab8`  
		Last Modified: Thu, 15 Mar 2018 15:25:15 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

### `tomcat:9-jre9-slim` - linux; s390x

```console
$ docker pull tomcat@sha256:32f4af19a0a6fb37fa3329c2feb2e9c306e78c7a2a5b9f7ebe122f1b0e1e958a
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **103.4 MB (103420967 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:e3a1350de9f414b96f5a64a758e44534e96b7d29604eb79b08562325807bf228`
-	Default Command: `["catalina.sh","run"]`

```dockerfile
# Wed, 14 Mar 2018 05:23:08 GMT
ADD file:6f68d1b98f1844e4f556be18e2db7a2f1262097f9dea14071f46d5f8dfbd22e7 in / 
# Wed, 14 Mar 2018 05:23:08 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 06:35:36 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 06:39:52 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 06:39:53 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Wed, 14 Mar 2018 06:39:54 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Wed, 14 Mar 2018 06:39:54 GMT
ENV JAVA_HOME=/docker-java-home
# Wed, 14 Mar 2018 06:39:54 GMT
ENV JAVA_VERSION=9.0.1+11
# Wed, 14 Mar 2018 06:39:54 GMT
ENV JAVA_DEBIAN_VERSION=9.0.1+11-1
# Wed, 14 Mar 2018 06:40:13 GMT
RUN set -ex; 		if [ ! -d /usr/share/man/man1 ]; then 		mkdir -p /usr/share/man/man1; 	fi; 		apt-get update; 	apt-get install -y 		openjdk-9-jre-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Wed, 14 Mar 2018 11:35:35 GMT
ENV CATALINA_HOME=/usr/local/tomcat
# Wed, 14 Mar 2018 11:35:35 GMT
ENV PATH=/usr/local/tomcat/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 14 Mar 2018 11:35:35 GMT
RUN mkdir -p "$CATALINA_HOME"
# Wed, 14 Mar 2018 11:35:35 GMT
WORKDIR /usr/local/tomcat
# Wed, 14 Mar 2018 11:35:36 GMT
ENV TOMCAT_NATIVE_LIBDIR=/usr/local/tomcat/native-jni-lib
# Wed, 14 Mar 2018 11:35:36 GMT
ENV LD_LIBRARY_PATH=/usr/local/tomcat/native-jni-lib
# Wed, 14 Mar 2018 11:35:36 GMT
ENV OPENSSL_VERSION=1.1.0f-3+deb9u1
# Wed, 14 Mar 2018 11:35:37 GMT
RUN set -ex; 	currentVersion="$(dpkg-query --show --showformat '${Version}\n' openssl)"; 	if dpkg --compare-versions "$currentVersion" '<<' "$OPENSSL_VERSION"; then 		if ! grep -q stretch /etc/apt/sources.list; then 			{ 				echo 'deb http://deb.debian.org/debian stretch main'; 				echo 'deb http://security.debian.org stretch/updates main'; 				echo 'deb http://deb.debian.org/debian stretch-updates main'; 			} > /etc/apt/sources.list.d/stretch.list; 			{ 				echo 'Package: *'; 				echo 'Pin: release n=stretch*'; 				echo 'Pin-Priority: -10'; 				echo; 				echo 'Package: openssl libssl*'; 				echo "Pin: version $OPENSSL_VERSION"; 				echo 'Pin-Priority: 990'; 			} > /etc/apt/preferences.d/stretch-openssl; 		fi; 		apt-get update; 		apt-get install -y --no-install-recommends openssl="$OPENSSL_VERSION"; 		rm -rf /var/lib/apt/lists/*; 	fi
# Wed, 14 Mar 2018 11:35:40 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		libapr1 	&& rm -rf /var/lib/apt/lists/*
# Wed, 14 Mar 2018 11:39:35 GMT
ENV GPG_KEYS=05AB33110949707C93A279E3D3EFE6B686867BA6 07E48665A34DCAFAE522E5E6266191C37C037D42 47309207D818FFD8DCD3F83F1931D684307A10A5 541FBE7D8F78B25E055DDEE13C370389288584E7 61B832AC2F1C5A90F0F9B00A1C506407564C17A3 79F7026C690BAA50B92CD8B66A3AD3F4F22C4FED 9BA44C2621385CB966EBA586F72C284D731FABEE A27677289986DB50844682F8ACB77FC2E86E29AC A9C5DF4D22E99998D9875A5110C01C5A2F6059E7 DCFD35E0BF8CA7344752DE8B6FB21E8933C60243 F3A04C595DB5B6A5F1ECA43E3B7BBB100D811BBE F7DA48BB64BCB84ECBA7EE6935CD23C10D498E23
# Wed, 14 Mar 2018 11:39:35 GMT
ENV TOMCAT_MAJOR=9
# Wed, 14 Mar 2018 11:39:35 GMT
ENV TOMCAT_VERSION=9.0.6
# Wed, 14 Mar 2018 11:39:35 GMT
ENV TOMCAT_SHA1=8cea5d0701773da1a0b2c2a6ec744b66eb8b2f34
# Wed, 14 Mar 2018 11:39:35 GMT
ENV TOMCAT_TGZ_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz
# Wed, 14 Mar 2018 11:39:36 GMT
ENV TOMCAT_ASC_URLS=https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www-us.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://www.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc 	https://archive.apache.org/dist/tomcat/tomcat-9/v9.0.6/bin/apache-tomcat-9.0.6.tar.gz.asc
# Wed, 14 Mar 2018 11:40:55 GMT
RUN set -eux; 		savedAptMark="$(apt-mark showmanual)"; 	apt-get update; 		apt-get install -y --no-install-recommends gnupg dirmngr; 		export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 		apt-get install -y --no-install-recommends wget ca-certificates; 		success=; 	for url in $TOMCAT_TGZ_URLS; do 		if wget -O tomcat.tar.gz "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		echo "$TOMCAT_SHA1 *tomcat.tar.gz" | sha1sum -c -; 		success=; 	for url in $TOMCAT_ASC_URLS; do 		if wget -O tomcat.tar.gz.asc "$url"; then 			success=1; 			break; 		fi; 	done; 	[ -n "$success" ]; 		gpg --batch --verify tomcat.tar.gz.asc tomcat.tar.gz; 	tar -xvf tomcat.tar.gz --strip-components=1; 	rm bin/*.bat; 	rm tomcat.tar.gz*; 	rm -rf "$GNUPGHOME"; 		nativeBuildDir="$(mktemp -d)"; 	tar -xvf bin/tomcat-native.tar.gz -C "$nativeBuildDir" --strip-components=1; 	apt-get install -y --no-install-recommends 		dpkg-dev 		gcc 		libapr1-dev 		libssl-dev 		make 		"openjdk-${JAVA_VERSION%%[.~bu-]*}-jdk=$JAVA_DEBIAN_VERSION" 	; 	( 		export CATALINA_HOME="$PWD"; 		cd "$nativeBuildDir/native"; 		gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; 		./configure 			--build="$gnuArch" 			--libdir="$TOMCAT_NATIVE_LIBDIR" 			--prefix="$CATALINA_HOME" 			--with-apr="$(which apr-1-config)" 			--with-java-home="$(docker-java-home)" 			--with-ssl=yes; 		make -j "$(nproc)"; 		make install; 	); 	rm -rf "$nativeBuildDir"; 	rm bin/tomcat-native.tar.gz; 		apt-mark auto '.*' > /dev/null; 	[ -z "$savedAptMark" ] || apt-mark manual $savedAptMark; 	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; 	rm -rf /var/lib/apt/lists/*; 		find ./bin/ -name '*.sh' -exec sed -ri 's|^#!/bin/sh$|#!/usr/bin/env bash|' '{}' +
# Wed, 14 Mar 2018 11:40:58 GMT
RUN set -e 	&& nativeLines="$(catalina.sh configtest 2>&1)" 	&& nativeLines="$(echo "$nativeLines" | grep 'Apache Tomcat Native')" 	&& nativeLines="$(echo "$nativeLines" | sort -u)" 	&& if ! echo "$nativeLines" | grep 'INFO: Loaded APR based Apache Tomcat Native library' >&2; then 		echo >&2 "$nativeLines"; 		exit 1; 	fi
# Wed, 14 Mar 2018 11:40:58 GMT
EXPOSE 8080/tcp
# Wed, 14 Mar 2018 11:40:58 GMT
CMD ["catalina.sh" "run"]
```

-	Layers:
	-	`sha256:298af72285f6bd87726f47a71d44a9089da15048e0eb38a6b2ad0d5f6eef4cff`  
		Last Modified: Wed, 14 Mar 2018 05:27:48 GMT  
		Size: 24.9 MB (24881607 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46fa0f98e9ab2b7efe654e711de6bbee6c0afc5d2a8d62d21d8f7b9f5dd611b9`  
		Last Modified: Wed, 14 Mar 2018 06:49:13 GMT  
		Size: 471.1 KB (471066 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:145731487640b0c37253c269f62de8cb9a3e791ad045f4100fe13271ed4fe7ac`  
		Last Modified: Wed, 14 Mar 2018 06:53:15 GMT  
		Size: 238.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cef137134e11a09aa4335e2221819e8c3b177b5e2d92cc5e8e34975efceafb81`  
		Last Modified: Wed, 14 Mar 2018 06:53:15 GMT  
		Size: 133.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:366d0599cbc7400eca567abc4aab3d36cf776d3169b80cd39ba978ec38cae26d`  
		Last Modified: Wed, 14 Mar 2018 06:53:26 GMT  
		Size: 66.4 MB (66396920 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:cad7933780a5ba0dc9d08557f0c39ade98ea7c4420841598f7ccfa8ddb9adcdb`  
		Last Modified: Wed, 14 Mar 2018 11:45:02 GMT  
		Size: 137.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4a786790187d5fd7c514c98cb81b079e2fc6febc7804493d0f887f1ca026254f`  
		Last Modified: Wed, 14 Mar 2018 11:45:01 GMT  
		Size: 412.0 KB (412030 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c120667e45726b6016c7f3db83f2150a47adcc28648ce58fc07d0ff8e832f628`  
		Last Modified: Wed, 14 Mar 2018 11:46:07 GMT  
		Size: 11.3 MB (11258706 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f36e5d11e58db2bc335ada7507fdde342eedae55d2c4045fa79bf7b9d241cab`  
		Last Modified: Wed, 14 Mar 2018 11:46:06 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

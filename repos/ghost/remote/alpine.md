## `ghost:alpine`

```console
$ docker pull ghost@sha256:1beb8d09d033f9e84e8338b29e8ef49726a535df98856dfa116796cf216036c0
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `ghost:alpine` - linux; amd64

```console
$ docker pull ghost@sha256:6dbebf6926d1ee891e6aa412ab121993108bb5c2628860b59c062e5d2ee5888e
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **136.5 MB (136459374 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bc059f73e07f708c565443f8ef95285a4aa42d8f1e42bd16c08e0cf0eda8862d`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["node","current\/index.js"]`

```dockerfile
# Tue, 09 Jan 2018 21:12:40 GMT
ADD file:69848cb51056edaf120230b6f218a79968ac797295c2cef6728332e1801357be in / 
# Tue, 09 Jan 2018 21:12:40 GMT
CMD ["/bin/sh"]
# Wed, 07 Mar 2018 19:50:17 GMT
ENV NODE_VERSION=6.13.1
# Wed, 07 Mar 2018 20:02:16 GMT
RUN addgroup -g 1000 node     && adduser -u 1000 -G node -s /bin/sh -D node     && apk add --no-cache         libstdc++     && apk add --no-cache --virtual .build-deps         binutils-gold         curl         g++         gcc         gnupg         libgcc         linux-headers         make         python   && for key in     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     B9AE9905FFD7803F25714661B63B535A4C206CA9     56730D5401028683275BD23C23EFEFE93C4CFFFE     77984A986EBC2AA786BC0F66B01FBB92821C587A   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.xz"     && curl -SLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xf "node-v$NODE_VERSION.tar.xz"     && cd "node-v$NODE_VERSION"     && ./configure     && make -j$(getconf _NPROCESSORS_ONLN)     && make install     && apk del .build-deps     && cd ..     && rm -Rf "node-v$NODE_VERSION"     && rm "node-v$NODE_VERSION.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt
# Wed, 07 Mar 2018 20:02:16 GMT
ENV YARN_VERSION=1.5.1
# Fri, 16 Mar 2018 17:44:17 GMT
RUN apk add --no-cache --virtual .build-deps-yarn curl gnupg tar   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver hkp://p80.pool.sks-keyservers.net:80 --recv-keys "$key" ||     gpg --keyserver hkp://ipv4.pool.sks-keyservers.net --recv-keys "$key" ||     gpg --keyserver hkp://pgp.mit.edu:80 --recv-keys "$key" ;   done   && curl -fSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz"   && curl -fSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz.asc"   && gpg --batch --verify yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && mkdir -p /opt   && tar -xzf yarn-v$YARN_VERSION.tar.gz -C /opt/   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarn /usr/local/bin/yarn   && ln -s /opt/yarn-v$YARN_VERSION/bin/yarnpkg /usr/local/bin/yarnpkg   && rm yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && apk del .build-deps-yarn
# Fri, 16 Mar 2018 17:44:17 GMT
CMD ["node"]
# Fri, 16 Mar 2018 19:39:25 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Fri, 16 Mar 2018 19:39:27 GMT
RUN apk add --no-cache 		bash
# Fri, 16 Mar 2018 19:39:28 GMT
ENV NODE_ENV=production
# Fri, 16 Mar 2018 19:39:28 GMT
ENV GHOST_CLI_VERSION=1.5.2
# Fri, 16 Mar 2018 19:39:51 GMT
RUN npm install -g "ghost-cli@$GHOST_CLI_VERSION"
# Fri, 16 Mar 2018 19:39:52 GMT
ENV GHOST_INSTALL=/var/lib/ghost
# Fri, 16 Mar 2018 19:39:52 GMT
ENV GHOST_CONTENT=/var/lib/ghost/content
# Fri, 16 Mar 2018 19:39:52 GMT
ENV GHOST_VERSION=1.21.5
# Fri, 16 Mar 2018 19:40:32 GMT
RUN set -ex; 	mkdir -p "$GHOST_INSTALL"; 	chown node:node "$GHOST_INSTALL"; 		su-exec node ghost install "$GHOST_VERSION" --db sqlite3 --no-prompt --no-stack --no-setup --dir "$GHOST_INSTALL"; 		cd "$GHOST_INSTALL"; 	su-exec node ghost config --ip 0.0.0.0 --port 2368 --no-prompt --db sqlite3 --url http://localhost:2368 --dbpath "$GHOST_CONTENT/data/ghost.db"; 	su-exec node ghost config paths.contentPath "$GHOST_CONTENT"; 		su-exec node ln -s config.production.json "$GHOST_INSTALL/config.development.json"; 	readlink -f "$GHOST_INSTALL/config.development.json"; 		mv "$GHOST_CONTENT" "$GHOST_INSTALL/content.orig"; 	mkdir -p "$GHOST_CONTENT"; 	chown node:node "$GHOST_CONTENT"; 		"$GHOST_INSTALL/current/node_modules/knex-migrator/bin/knex-migrator" --version
# Fri, 16 Mar 2018 19:40:33 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/var/lib/ghost/current/node_modules/knex-migrator/bin
# Fri, 16 Mar 2018 19:40:33 GMT
WORKDIR /var/lib/ghost
# Fri, 16 Mar 2018 19:40:33 GMT
VOLUME [/var/lib/ghost/content]
# Fri, 16 Mar 2018 19:40:34 GMT
COPY file:fe4f8ce065580d78daf2ea3ae3ab9174f3edd7740df8b95889926dc1cdfe77b0 in /usr/local/bin 
# Fri, 16 Mar 2018 19:40:34 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 16 Mar 2018 19:40:35 GMT
EXPOSE 2368/tcp
# Fri, 16 Mar 2018 19:40:35 GMT
CMD ["node" "current/index.js"]
```

-	Layers:
	-	`sha256:81033e7c1d6a5b44a94bb6b40033a6e589f50fd6b61578da6fc809e61f83898d`  
		Last Modified: Tue, 09 Jan 2018 21:15:04 GMT  
		Size: 2.4 MB (2387570 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f477172e31073346486b31dc1a9b36876b824665ccfb691e0a3f3c6bce9fbf3a`  
		Last Modified: Wed, 07 Mar 2018 20:26:57 GMT  
		Size: 15.5 MB (15506590 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:e33a8ebeba9b7af7c6cdaeb9b14af078a4422f7c3faf75aaa638bbbbda0b5c12`  
		Last Modified: Fri, 16 Mar 2018 18:05:30 GMT  
		Size: 1.1 MB (1067487 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:276e95c4e07b3de1798b8c0af32ac99e1da48b2f50842909920ed0c26d7d7012`  
		Last Modified: Fri, 16 Mar 2018 20:00:51 GMT  
		Size: 8.4 KB (8363 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c2f78b73b1205c5bdcaf8db79968b6f00ffe8738c605c5b1f7f6e1b4689dcf53`  
		Last Modified: Fri, 16 Mar 2018 20:00:57 GMT  
		Size: 1.1 MB (1119100 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f427570f8a6cfadde0634fb758da178ad548c38d6f176bfbe2a4f8e0610b76e1`  
		Last Modified: Fri, 16 Mar 2018 20:01:13 GMT  
		Size: 19.4 MB (19428467 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:68378df9853c1d3de894da9f507e4233605442774f5d290d52a4f3ceca140278`  
		Last Modified: Fri, 16 Mar 2018 20:01:42 GMT  
		Size: 96.9 MB (96941242 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8179b7885b8df80f071cd971fd79bd32f8c59d59ea1df8477844beaddd24a3f6`  
		Last Modified: Fri, 16 Mar 2018 20:00:51 GMT  
		Size: 555.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

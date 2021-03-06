## `odoo:latest`

```console
$ docker pull odoo@sha256:ac26773a69ed97cea0d48ac407567f6ea920fae5315296ea92518642e11facf1
```

-	Manifest MIME: `application/vnd.docker.distribution.manifest.list.v2+json`
-	Platforms:
	-	linux; amd64

### `odoo:latest` - linux; amd64

```console
$ docker pull odoo@sha256:d998d02981ccc55282b12a6804b99fbb0d1ef12014211981652195b637058ecd
```

-	Docker Version: 17.06.2-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **414.7 MB (414715049 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:eb5619fb027cfd867da0e90f87c1e9f5658e0ae8fd50abcba2a26b345a6bfb04`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["odoo"]`

```dockerfile
# Tue, 13 Mar 2018 22:26:49 GMT
ADD file:b380df301ccb5ca09f0d7cd5697ed402fa55f3e9bc5df2f4d489ba31f28de58a in / 
# Tue, 13 Mar 2018 22:26:49 GMT
CMD ["bash"]
# Wed, 14 Mar 2018 08:46:03 GMT
MAINTAINER Odoo S.A. <info@odoo.com>
# Wed, 14 Mar 2018 08:46:03 GMT
ENV LANG=C.UTF-8
# Wed, 14 Mar 2018 08:46:34 GMT
RUN set -x;         apt-get update         && apt-get install -y --no-install-recommends             ca-certificates             curl             node-less             python3-pip             python3-setuptools             python3-renderpm             libssl1.0-dev             xz-utils         && curl -o wkhtmltox.tar.xz -SL https://github.com/wkhtmltopdf/wkhtmltopdf/releases/download/0.12.4/wkhtmltox-0.12.4_linux-generic-amd64.tar.xz         && echo '3f923f425d345940089e44c1466f6408b9619562 wkhtmltox.tar.xz' | sha1sum -c -         && tar xvf wkhtmltox.tar.xz         && cp wkhtmltox/lib/* /usr/local/lib/         && cp wkhtmltox/bin/* /usr/local/bin/         && cp -r wkhtmltox/share/man/man1 /usr/local/share/man/
# Wed, 14 Mar 2018 08:46:34 GMT
ENV ODOO_VERSION=11.0
# Wed, 14 Mar 2018 08:46:35 GMT
ENV ODOO_RELEASE=20180122
# Wed, 14 Mar 2018 08:48:01 GMT
RUN set -x;         curl -o odoo.deb -SL http://nightly.odoo.com/${ODOO_VERSION}/nightly/deb/odoo_${ODOO_VERSION}.${ODOO_RELEASE}_all.deb         && echo '56f61789bc655aaa2c014a3c5f63d80805408359 odoo.deb' | sha1sum -c -         && dpkg --force-depends -i odoo.deb         && apt-get update         && apt-get -y install -f --no-install-recommends         && rm -rf /var/lib/apt/lists/* odoo.deb
# Wed, 14 Mar 2018 08:48:05 GMT
RUN pip3 install num2words xlwt
# Wed, 14 Mar 2018 08:48:05 GMT
COPY file:33fddeba88e5214ff2c7cd05a02348dc417a5de70b767d6ff559e871ee6d046a in / 
# Wed, 14 Mar 2018 08:48:06 GMT
COPY file:db43c8e34bfc1a07c1c22547437af17629fbadb6633084c02cbfc0bb6069c9fd in /etc/odoo/ 
# Wed, 14 Mar 2018 08:48:06 GMT
RUN chown odoo /etc/odoo/odoo.conf
# Wed, 14 Mar 2018 08:48:07 GMT
RUN mkdir -p /mnt/extra-addons         && chown -R odoo /mnt/extra-addons
# Wed, 14 Mar 2018 08:48:07 GMT
VOLUME [/var/lib/odoo /mnt/extra-addons]
# Wed, 14 Mar 2018 08:48:08 GMT
EXPOSE 8069/tcp 8071/tcp
# Wed, 14 Mar 2018 08:48:08 GMT
ENV ODOO_RC=/etc/odoo/odoo.conf
# Wed, 14 Mar 2018 08:48:08 GMT
USER [odoo]
# Wed, 14 Mar 2018 08:48:08 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Wed, 14 Mar 2018 08:48:09 GMT
CMD ["odoo"]
```

-	Layers:
	-	`sha256:c73ab1c6897bf5c11da3c95cab103e7ca8cf10a6d041eda2ff836f45a40e3d3b`  
		Last Modified: Tue, 13 Mar 2018 22:52:31 GMT  
		Size: 45.1 MB (45135077 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0a6f980695bb9dfa1de664d408e3dfdcd300c3086ae8cd20b25c34fe02e8f8c4`  
		Last Modified: Wed, 14 Mar 2018 09:14:34 GMT  
		Size: 221.5 MB (221537124 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b73e0e7a3b918689a658437330ac41a78078778c90d09ce357a246ad28f6e438`  
		Last Modified: Wed, 14 Mar 2018 09:14:53 GMT  
		Size: 147.6 MB (147578733 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5afc2f80aad92600eda26c8ed1b2f013900ee475ed1c5fc12b4348e1dc08e75`  
		Last Modified: Wed, 14 Mar 2018 09:13:57 GMT  
		Size: 462.3 KB (462278 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d8bd5f10d197bfee5ffd9465e26e1d5b24fc3b80fcdfa44bc31329b61ba1a85b`  
		Last Modified: Wed, 14 Mar 2018 09:13:56 GMT  
		Size: 601.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c92b1fcea1db450544201546d0a36026e25be2d8c3a4f26d99b1dcf0a23f4cdd`  
		Last Modified: Wed, 14 Mar 2018 09:13:57 GMT  
		Size: 551.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1ed9bd876a976dd0ef5c00c43ea24d8c9b22719b7d0fdb289b4cba6bcb5b2419`  
		Last Modified: Wed, 14 Mar 2018 09:13:57 GMT  
		Size: 557.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:db29c30f1033b502f0b58534f3a35f9ecdfed9bf192d8df3c1f1955dc85dd812`  
		Last Modified: Wed, 14 Mar 2018 09:13:56 GMT  
		Size: 128.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip

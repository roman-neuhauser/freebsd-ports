# Created by: Roman Neuhauser <rneuhauser@sigpipe.cz>
# $FreeBSD$

PORTNAME=	s6-dns
PORTVERSION=	2.1.0.0
CATEGORIES=	dns
MASTER_SITES=	http://www.skarnet.org/software/${PORTNAME}/

MAINTAINER=	rneuhauser@sigpipe.cz
COMMENT=	Suite of DNS client programs and libraries

LICENSE=	ISCL
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS+=	libskarnet.so>=2.4:devel/skalibs

USES=		gmake

USE_LDCONFIG=	yes
HAS_CONFIGURE=	yes
CONFIGURE_ARGS=	--prefix=${PREFIX} \
		--with-include=${LOCALBASE}/include \
		--with-dynlib=${LOCALBASE}/lib \
		--with-lib=${LOCALBASE}/lib/skalibs \
		--with-sysdeps=${LOCALBASE}/lib/skalibs/sysdeps \
		--enable-shared

DOCS=		AUTHORS README doc/*.html doc/*/*.html

OPTIONS_DEFINE=	DOCS

do-install:
	${GMAKE} -C "${INSTALL_WRKSRC}" strip install DESTDIR="${STAGEDIR}"

post-install-DOCS-on:
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	cd "${INSTALL_WRKSRC}" && ${INSTALL_DATA} ${DOCS} "${STAGEDIR}${DOCSDIR}"

.include <bsd.port.mk>

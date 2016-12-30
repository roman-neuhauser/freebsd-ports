# Created by: Roman Neuhauser <rneuhauser@sigpipe.cz>
# $FreeBSD$

PORTNAME=	s6-networking
PORTVERSION=	2.2.1.0
CATEGORIES=	net
MASTER_SITES=	http://www.skarnet.org/software/${PORTNAME}/

MAINTAINER=	rneuhauser@sigpipe.cz
COMMENT=	Suite of small networking utilities

LICENSE=	ISCL
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS+=	libskarnet.so>=2.4:devel/skalibs
BUILD_DEPENDS+=	s6>=2.4.0.0:sysutils/s6
BUILD_DEPENDS+=	execline>=2.2.0.0:lang/execline
RUN_DEPENDS+=	execlineb:lang/execline

USES=		gmake

USE_LDCONFIG=	yes
HAS_CONFIGURE=	yes
CONFIGURE_ARGS=	--prefix=${PREFIX} \
		--with-include=${LOCALBASE}/include \
		--with-dynlib=${LOCALBASE}/lib \
		--with-sysdeps=${LOCALBASE}/lib/skalibs/sysdeps \
		--with-lib=${LOCALBASE}/lib/skalibs \
		--with-lib=${LOCALBASE}/lib/execline \
		--with-lib=${LOCALBASE}/lib/s6 \
		--with-lib=${LOCALBASE}/lib/s6-dns \
		--enable-shared

DOCS=		AUTHORS README doc/*.html

OPTIONS_DEFINE=	DOCS

do-install:
	${GMAKE} -C "${INSTALL_WRKSRC}" strip install DESTDIR="${STAGEDIR}"

post-install-DOCS-on:
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	cd "${INSTALL_WRKSRC}" && ${INSTALL_DATA} ${DOCS} "${STAGEDIR}${DOCSDIR}"

.include <bsd.port.mk>

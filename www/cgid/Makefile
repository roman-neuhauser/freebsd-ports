# Created by: Roman Neuhauser <neuhauser+cgid@sigpipe.cz>
# $FreeBSD$

PORTNAME=	cgid
PORTVERSION=	0.1.0
CATEGORIES=	www

MAINTAINER=	neuhauser+cgid@sigpipe.cz
COMMENT=	UCSPI compatible CGI server

LICENSE=	MIT

BUILD_DEPENDS=	cargo:devel/cargo

USE_GITHUB=	yes
GH_ACCOUNT=	frioux
GH_PROJECT=	${PORTNAME}
GH_TAGNAME=	v${PORTVERSION}

do-build:
	cd "${WRKSRC}" && cargo build -v --release

do-install:
	${INSTALL_PROGRAM} "${WRKSRC}/target/release/cgid" "${STAGEDIR}${PREFIX}/bin/cgid"

.include <bsd.port.mk>

# Created by: rfarmer@predatorlabs.net
# $FreeBSD$

PORTNAME=	matio
PORTVERSION=	1.5.2
PORTREVISION=	6
CATEGORIES=	math
MASTER_SITES=	SF

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Library for reading and writing Matlab MAT files

LICENSE=	BSD2CLAUSE

GNU_CONFIGURE=	yes
USES=		libtool pathfix
USE_LDCONFIG=	yes
INSTALL_TARGET=	install-strip

OPTIONS_DEFINE=	HDF5
OPTIONS_DEFAULT=	HDF5

HDF5_DESC=	Support for MAT file version 7.3
HDF5_LIB_DEPENDS=	libhdf5.so:science/hdf5
HDF5_CONFIGURE_ON=	--enable-mat73=yes \
			--with-hdf5=${LOCALBASE}

.include <bsd.port.mk>

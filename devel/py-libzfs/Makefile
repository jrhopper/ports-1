# Created by: William Grzybowski <wg@FreeBSD.org>
# $FreeBSD$

PORTNAME=	libzfs
PORTVERSION=	1.0.202006081806
CATEGORIES=	devel python
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	wg@FreeBSD.org
COMMENT=	Python libzfs bindings

LICENSE=	BSD2CLAUSE

RUN_DEPENDS=	${PY_ENUM34}

USE_GITHUB=     yes
GH_ACCOUNT=	freenas
GH_PROJECT=	py-libzfs
GH_TAGNAME=	6874c842ea3905d6442038bf91247012c7e2a12e

HAS_CONFIGURE=	yes
USES=		compiler:c11 python
USE_PYTHON=	autoplist distutils cython

CONFIGURE_ENV=	freebsd_src=${SRC_BASE}
MAKE_ENV=	freebsd_src=${SRC_BASE}

# Py-libzfs needs libzfs to be built
.if !exists(/sbin/zpool)
BUILD_DEPENDS+=        openzfs>=0:sysutils/openzfs
RUN_DEPENDS+=  openzfs>=0:sysutils/openzfs
.endif

# Py-libzfs needs libzfs to be built
.if !exists(/sbin/zpool)
BUILD_DEPENDS+=        openzfs>=0:sysutils/openzfs
RUN_DEPENDS+=  openzfs>=0:sysutils/openzfs
.endif

.include <bsd.port.options.mk>

.if !exists(${SRC_BASE}/sys/Makefile)
IGNORE=	requires kernel source files in ${SRC_BASE}
.endif

.include <bsd.port.mk>

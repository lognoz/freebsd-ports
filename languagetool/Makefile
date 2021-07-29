# Created by: Marc-Antoine Loignon <developer@lognoz.org>

PORTNAME=	languagetool
PORTVERSION=	5.4
CATEGORIES=	textproc java
MASTER_SITES=	https://www.languagetool.org/download/
DISTNAME=	LanguageTool-${PORTVERSION}.zip:buildtools

MAINTAINER=	developer@lognoz.org
COMMENT=	Style and Grammar Checker for 25+ Languages

LICENSE=	GPLv2

RUN_DEPENDS=	unzip>=0:archivers/unzip \
		bash:shells/bash

USE_JAVA=	yes
JAVA_VERSION=	8+
JAVA_OS=	native
JAVA_VENDOR=	openjdk

WRKSRC=		${WRKDIR}/LanguageTool-${PORTVERSION}
NO_BUILD=	yes

do-install:
	${MKDIR} ${STAGEDIR}${JAVAJARDIR}/languagetool \
		${STAGEDIR}${DATADIR}
	(cd ${WRKSRC} && ${COPYTREE_SHARE} . ${STAGEDIR}${DATADIR})
	${RM} ${STAGEDIR}${DATADIR}/*jar
	${RM} -rf ${STAGEDIR}${DATADIR}/libs
	${INSTALL_DATA} ${WRKSRC}/*.jar ${STAGEDIR}${JAVAJARDIR}/languagetool
	${INSTALL_DATA} ${WRKSRC}/libs/*.jar ${STAGEDIR}${JAVAJARDIR}/languagetool
	${INSTALL_SCRIPT} ${FILESDIR}/languagetool ${STAGEDIR}${PREFIX}/bin
	${INSTALL_SCRIPT} ${FILESDIR}/languagetool-cli ${STAGEDIR}${PREFIX}/bin

.include <bsd.port.mk>

PKG_NAME = pngquant
PKG_VERS = 2.12.5
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_NAME)-$(PKG_VERS)-src.$(PKG_EXT)
PKG_DIST_SITE = https://pngquant.org
PKG_DIR = $(PKG_NAME)-$(PKG_VERS)

DEPENDS = cross/libpng cross/libimagequant

HOMEPAGE = http://pngquant.org/
COMMENT  = pngquant is a command-line utility and a library for lossy compression of PNG images.
LICENSE  = GPL

GNU_CONFIGURE = 1
ADDITIONAL_CFLAGS = -O3
CONFIGURE_ARGS = --with-libimagequant

ifeq ($(findstring $(ARCH), $(x64_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --enable-sse
else
CONFIGURE_ARGS += --disable-sse
endif

include ../../mk/spksrc.cross-cc.mk

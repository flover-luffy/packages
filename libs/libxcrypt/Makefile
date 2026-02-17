#
# Copyright (C) 2024 ImmortalWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libxcrypt
PKG_VERSION:=4.4.36
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/besser82/libxcrypt/releases/download/v$(PKG_VERSION)
PKG_HASH:=e5e1f4ca9b933333469e38d438096e85744f6f81e7d2e08620e7c5b65123d51b

PKG_MAINTAINER:=
PKG_LICENSE:=LGPL-2.1-or-later
PKG_LICENSE_FILES:=COPYING.LIB

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libxcrypt
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Extended crypt library
  URL:=https://github.com/besser82/libxcrypt
  PROVIDES:=libcrypt-compat
endef

define Package/libxcrypt/description
  libxcrypt is a modern library for one-way hashing of passwords.
  It supports a wide variety of hashing methods, including traditional DES,
  MD5, SHA-256, SHA-512, and bcrypt.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/*.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libcrypt.so* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig/*.pc $(1)/usr/lib/pkgconfig/
endef

define Package/libxcrypt/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libcrypt.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libxcrypt))

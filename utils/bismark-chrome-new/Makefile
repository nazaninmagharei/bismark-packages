#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bismark-chrome-new
PKG_VERSION:=0.9.0
PKG_RELEASE:=5
PKG_REV:=2693afcf4c08c41067ac11177a1da3a033d6c6c0
# PKG_VERSION:=20110517

include $(INCLUDE_DIR)/package.mk

define Package/bismark-chrome-new
   SECTION:=utils
   CATEGORY:=Utilities
   TITLE:=Web server files for bismark
   URL:=http://www.gtnoise.net/
   MAINTAINER:=Bismark Development List <bismark-devel@lists.bufferbloat.net>
   DEPENDS:=
endef

define Package/bismark-chrome-new/description
	The bismark-chrome package provides a reference local web page
	for network resources.
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) -pr ./files/* $(PKG_BUILD_DIR)
endef

define Build/Compile
	
endef

define Package/bismark-chrome-new/install
	$(INSTALL_DIR) $(1)/www
	$(CP) -p $(PKG_BUILD_DIR)/www/* $(1)/www/
endef

define Package/bismark-chrome-new/postinst
#!/bin/sh
# Bismark management post-install script
if [[ -e /www/index.html ]] && [[ -e /www/index.htm ]]; then
    rm -f /www/index.html
fi
endef

$(eval $(call BuildPackage,bismark-chrome-new))

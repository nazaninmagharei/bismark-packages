#
# Copyright (C) 2006-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=passivetr
PKG_VERSION:=1.0
PKG_RELEASE:=3

include $(INCLUDE_DIR)/package.mk

define Package/passivetr
	SECTION:=net
	CATEGORY:=Network
	TITLE:=Traceroute to IP addresses of passive traffic
	URL:=http://www.cc.gatech.edu/~partha/diffprobe/passive-trace.html
	DEPENDS:=+libpthread +zlib
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)
endef

define Package/passivetr/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/passive-trace $(1)/usr/bin/passive-trace
endef

$(eval $(call BuildPackage,passivetr))

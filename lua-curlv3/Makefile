#
# Copyright (C) 20015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-curlv3
PKG_VERSION:=0.3.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/Lua-cURL/Lua-cURLv3
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_MAINTAINER:=Neutron Soutmun <neo.neutron@gmail.com>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/lua-curlv3
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Lua binding to libcurl
	URL:=https://github.com/Lua-cURL/Lua-cURLv3
	DEPENDS:=+lua +libcurl +librt
endef

define Package/lua-curlv3/description
	Lua cURLv3 provides the high level API which is on top of low level pure C
	binding to libcurl.
endef

define Package/lua-curlv3/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/cURL
	$(INSTALL_DIR) $(1)/usr/lib/lua/cURL/impl
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/lua/cURL.lua $(1)/usr/lib/lua
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/lua/cURL/safe.lua $(1)/usr/lib/lua/cURL
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/lua/cURL/utils.lua $(1)/usr/lib/lua/cURL
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/lua/cURL/impl/cURL.lua $(1)/usr/lib/lua/cURL/impl
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/lcurl.so $(1)/usr/lib/lua
endef

$(eval $(call BuildPackage,lua-curlv3,+lua,+libcurl,+librt))

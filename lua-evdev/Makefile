#
# Copyright (C) 20015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-evdev
PKG_VERSION:=2.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/Tangent128/lua-evdev.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=evdev-$(PKG_VERSION)
PKG_MAINTAINER:=Neutron Soutmun <neo.neutron@gmail.com>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

MAKE_FLAGS += \
	MYCFLAGS="-I$(STAGING_DIR)/usr/include -DCOMPAT53_PREFIX=lua53"

define Package/lua-evdev
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Lua evdev module for interacting with input devices 
	URL:=https://github.com/Tangent128/lua-evdev
	DEPENDS:=+lua +libc
endef

define Package/lua-evdev/description
	Lua evdev module for interacting with input devices on Linux.
        You can read events with a "Device" object, or create a virtual input
        device with a "Uinput" object.
endef

define Package/lua-evdev/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/evdev
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/evdev.lua $(1)/usr/lib/lua
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/evdev/constants.lua $(1)/usr/lib/lua/evdev
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/evdev/core.so $(1)/usr/lib/lua/evdev
endef

$(eval $(call BuildPackage,lua-evdev,+lua,+libc))

#
# Copyright (C) 2019 mleaf.org
# 微信公众号【WiFi物联网】
#
# This is free software, licensed under the GNU General Public License v3.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mwol
PKG_VERSION:=1.0.0
PKG_RELEASE=1


PKG_LICENSE:=GPL-3.0
PKG_MAINTAINER:=ylhsieh  <yilin.hsieh@hawkeyetech.com.tw>
PKG_LICENSE_FILES:=COPYING

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/yilinhsieh/mwol.git
PKG_SOURCE_VERSION:=c7f5dad01f550be60489a3a41dccd4a26a430421
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz


PKG_INSTALL:=1
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/mwol
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=+libpthread +libmosquitto-ssl +luci-lib-json +libopenssl
  TITLE:=MQTT Wake On Lan
  URL:= 
endef

define Package/mwol/description
	mwol is a project that uses mqtt to implement reverse proxy and wake up the computer.
endef

define Package/mwol/install
	$(INSTALL_DIR) $(1)/usr/share/mwol/ssl
	$(CP) files/ssl/* $(1)/usr/share/mwol/ssl/
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/mwol $(1)/usr/sbin/mwol
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DATA) files/mwol.config $(1)/etc/config/mwol
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) files/mwol.init $(1)/etc/init.d/mwol
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) files/mwol_config_json $(1)/usr/sbin/mwol_config_json
endef

$(eval $(call BuildPackage,mwol))

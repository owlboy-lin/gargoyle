#
# Copyright (C) 2010-2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=openvpn-gargoyle-easy-rsa

PKG_REV:=ff5bfd1dd8e548cb24d302742af3894f893ef92f
PKG_VERSION:=2013-01-30
PKG_RELEASE=2

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/OpenVPN/easy-rsa.git
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_REV).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_LICENSE:=GPL-2.0

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)/$(PKG_SOURCE_SUBDIR)

include $(INCLUDE_DIR)/package.mk

define Package/openvpn-gargoyle-easy-rsa
  TITLE:=Simple shell scripts to manage a Certificate Authority
  SECTION:=net
  CATEGORY:=Network
  URL:=http://openvpn.net
  SUBMENU:=VPN
  DEPENDS:=+openssl-util
endef

define Build/Configure

endef

define Build/Compile

endef

define Package/openvpn-gargoyle-easy-rsa/install
	$(INSTALL_DIR)                                                                                                              $(1)/usr/lib/easy-rsa
	$(CP) $(PKG_BUILD_DIR)/easy-rsa/2.0/{build-*,clean-all,inherit-inter,list-crl,pkitool,revoke-full,sign-req,whichopensslcnf} $(1)/usr/lib/easy-rsa
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/easy-rsa/2.0/openssl-1.0.0.cnf                                                             $(1)/usr/lib/easy-rsa/openssl-1.1.0.cnf
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/easy-rsa/2.0/vars                                                                          $(1)/usr/lib/easy-rsa/vars
	$(INSTALL_DIR)                                                                                                              $(1)/usr/lib/easy-rsa/keys
	$(INSTALL_DATA) files/easy-rsa.index                                                                                        $(1)/usr/lib/easy-rsa/keys/index.txt
	$(INSTALL_DATA) files/easy-rsa.serial                                                                                       $(1)/usr/lib/easy-rsa/keys/serial
endef

$(eval $(call BuildPackage,openvpn-gargoyle-easy-rsa))

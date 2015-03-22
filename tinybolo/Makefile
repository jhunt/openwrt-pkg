include $(TOPDIR)/rules.mk

PKG_NAME:=tinybolo
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://download.jameshunt.us/

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/tinybolo
    SECTION:=utils
    CATEGORY:=Utilities
    TITLE:=tinybolo
    DEPENDS:=+libzmq4
    URL:=http://jameshunt.us
    MAINTAINER:=james@jameshunt.us
endef

define Package/tinybolo/description
    A lightweight metrics collector for the bolo platform.
endef

define Build/Configure
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default)
endef

define Package/tinybolo/install
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tinybolo $(1)/sbin/
	$(INSTALL_DIR) $(1)/lib/bolo
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/openwrt $(1)/lib/bolo
endef

$(eval $(call BuildPackage,tinybolo))

include $(TOPDIR)/rules.mk

PKG_NAME:=libzmq3
PKG_VERSION:=4.0.4
PKG_RELEASE:=1

PKG_SOURCE:=zeromq-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://download.zeromq.org/

include $(INCLUDE_DIR)/package.mk

define Package/libzmq3
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=libzmq3
  DEPENDS:=+libstdcpp +libpthread +librt
  URL:=http://www.zeromq.org/
  MAINTAINER:=james@jameshunt.us
endef

define Package/libzmq3/description
  ØMQ is a library which extends the standard socket interfaces with features
  traditionally provided by specialised messaging middleware products.

  ØMQ sockets provide an abstraction of asynchronous message queues, multiple
  messaging patterns, message filtering (subscriptions), seamless access to
  multiple transport protocols and more.

  This package contains the libzmq shared library.
endef

define Build/Configure
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*         $(1)/usr/lib/
	$(CP) $(PKG_INSTALL_DIR)/usr/include/*     $(1)/usr/include/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/pkgconfig $(1)/usr/lib/
endef

define Package/libzmq3/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/*.so* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libzmq3))

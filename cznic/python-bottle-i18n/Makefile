#
# Copyright (C) 2013 CZ.NIC z.s.p.o. (http://www.nic.cz/)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bottle-i18n
PKG_VERSION:=0.1.5
PKG_RELEASE:=1

PKG_SOURCE:=bottle-i18n-0.1.5.tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/b/bottle-i18n/
PKG_MD5SUM:=f0942f05fec0f4a3c45765623863cb68

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-bottle-i18n
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=python-bottle-i18n
	URL:=https://github.com/iocast/bottle-i18n
	DEPENDS:=+python-light +python-bottle
	MAINTAINER:=CZ.NIC <packaging@turris.cz>
endef

define Package/python-bottle-i18n/description
	i18n support for bottle.py
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/python-bottle-i18n/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-bottle-i18n))

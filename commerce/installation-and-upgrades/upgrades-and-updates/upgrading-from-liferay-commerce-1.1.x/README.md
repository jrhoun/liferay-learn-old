# Upgrading from 1.1.x

This article documents how to upgrade Liferay Commerce to the latest maintenance version. Store administrators should upgrade regularly because the latest versions contain the critical fixes and new features. Because Liferay Commerce is built on Liferay DXP, it is necessary to have an existing DXP 7.1 instance running.

To upgrade Liferay Commerce:

1. Download the latest Liferay Commerce `LPKG`.
    * Enterprise subscribers can download the latest `LPKG` from [Help Center](https://customer.liferay.com/downloads?p_p_id=com_liferay_osb_customer_downloads_display_web_DownloadsDisplayPortlet&_com_liferay_osb_customer_downloads_display_web_DownloadsDisplayPortlet_productAssetCategoryId=118190997&_com_liferay_osb_customer_downloads_display_web_DownloadsDisplayPortlet_fileTypeAssetCategoryId=118191001).
    * The latest open source `LPKG` may be obtained from the [Liferay Commerce Community Site](https://commerce.liferay.dev/download).

1. Deploy the `LPKG` to the `${liferay.home}/deploy` folder.
    > To learn more about deploying applications to Liferay DXP, see [Liferay Home](https://help.liferay.com/hc/en-us/articles/360028712272-Liferay-Home).
1. Verify that that the following message appears in the application server console:

    ```
    2019-08-12 21:53:43.847 INFO  [com.liferay.portal.kernel.deploy.auto.AutoDeployScanner][AutoDeployDir:261] Processing Liferay Commerce Enterprise 2.0.2.lpkg
    2019-08-13 18:12:56.713 INFO  [fileinstall-/../../liferay-commerce-enterprise-1.1.6/osgi/marketplace][LPKGArtifactInstaller:202] The portal instance needs to be restarted to complete the installation of file:/../../liferay-commerce-enterprise-1.1.6/osgi/marketplace/Liferay%20Commerce%20-%20API.lpkg
    2019-08-13 18:12:56.715 INFO  [fileinstall-/../../liferay-commerce-enterprise-1.1.6/osgi/marketplace][LPKGArtifactInstaller:202] The portal instance needs to be restarted to complete the installation of file:/../../liferay-commerce-enterprise-1.1.6/osgi/marketplace/Liferay%20Commerce%20-%20Impl.lpkg
    ```

1. Shut down the application server.
1. Navigate to the `${liferay.home}/osgi` folder.
1. Delete the `${liferay.home}/osgi/state` folder.
    > To learn more about OSGi folders, see [Installing Apps Manually](https://help.liferay.com/hc/en-us/articles/360017895412-Installing-Apps-Manually#using-your-file-system-to-install-apps).
1. Start the application server.
1. Verify that the `LPKG` has begun the upgrade process by looking for messages similar to this:

    ```
    2019-08-13 18:26:26.082 INFO  [main][UpgradeProcess:93] Upgrading com.liferay.commerce.account.internal.upgrade.v1_2_0.CommerceAccountGroupCommerceAccountRelUpgradeProcess
    2019-08-13 18:26:26.106 INFO  [main][UpgradeProcess:107] Completed upgrade process com.liferay.commerce.account.internal.upgrade.v1_2_0.CommerceAccountGroupCommerceAccountRelUpgradeProcess in 24 ms
    2019-08-13 18:26:26.116 INFO  [main][UpgradeProcess:93] Upgrading com.liferay.commerce.account.internal.upgrade.v1_2_0.CommerceAccountGroupRelUpgradeProcess
    2019-08-13 18:26:26.124 INFO  [main][UpgradeProcess:107] Completed upgrade process com.liferay.commerce.account.internal.upgrade.v1_2_0.CommerceAccountGroupRelUpgradeProcess in 8 ms
    2019-08-13 18:26:26.130 INFO  [main][UpgradeProcess:93] Upgrading com.liferay.commerce.account.internal.upgrade.v1_2_0.CommerceAccountGroupUpgradeProcess
    2019-08-13 18:26:26.142 INFO  [main][UpgradeProcess:107] Completed upgrade process com.liferay.commerce.account.internal.upgrade.v1_2_0.CommerceAccountGroupUpgradeProcess in 12 ms
    2019-08-13 18:26:26.148 INFO  [main][UpgradeProcess:93] Upgrading com.liferay.commerce.account.internal.upgrade.v1_3_0.CommerceAccountNameUpgradeProcess
    2019-08-13 18:26:26.160 INFO  [main][LoggingTimer:83] Starting com.liferay.portal.kernel.upgrade.UpgradeProcess#alter
    2019-08-13 18:26:26.200 INFO  [main][LoggingTimer:43] Completed com.liferay.portal.kernel.upgrade.UpgradeProcess#alter in 40 ms
    2019-08-13 18:26:26.208 INFO  [main][UpgradeProcess:107] Completed upgrade process com.liferay.commerce.account.internal.upgrade.v1_3_0.CommerceAccountNameUpgradeProcess in 60 ms
    2019-08-13 18:26:26.246 INFO  [main][LoggingTimer:83] Starting com.liferay.portal.upgrade.internal.index.updater.IndexUpdaterUtil#updateIndexes#Updating database indexes for com.liferay.commerce.account.service
    2019-08-13 18:26:26.346 INFO  [main][BaseDB:812] Dropping stale indexes
    2019-08-13 18:26:26.400 INFO  [main][BaseDB:84] Adding indexes
    ```
    and then...
    ```
    2019-08-13 18:28:19.439 INFO  [main][VerifyProcess:65] Verifying com.liferay.commerce.product.internal.verify.CommerceCatalogServiceVerifyProcess
    2019-08-13 18:28:19.443 INFO  [main][LoggingTimer:83] Starting com.liferay.commerce.product.internal.verify.CommerceCatalogServiceVerifyProcess#verifyMasterCommerceCatalog
    2019-08-13 18:28:19.445 INFO  [main][LoggingTimer:43] Completed com.liferay.commerce.product.internal.verify.CommerceCatalogServiceVerifyProcess#verifyMasterCommerceCatalog in 2 ms
    2019-08-13 18:28:19.446 INFO  [main][VerifyProcess:80] Completed verification process com.liferay.commerce.product.internal.verify.CommerceCatalogServiceVerifyProcess in 7 ms
    2019-08-13 18:28:32.471 INFO  [main][ThemeHotDeployListener:108] 1 theme for admin-theme is available for use
    2019-08-13 18:28:34.296 INFO  [main][ThemeHotDeployListener:108] 1 theme for classic-theme is available for use
    2019-08-13 18:28:38.667 INFO  [main][ThemeHotDeployListener:108] 1 theme for minium-theme is available for use
    ```

The Liferay Commerce instance has been upgraded.

### Post-Upgrade

After upgrading from Liferay Commerce 1.1.x to the latest version, it is necessary to execute a reindex because of the changes in the index caused by the upgrade. This is because during the upgrade process, the _Breccia_ Accelerator was removed and many Liferay Commerce features and functions were migrated. Furthermore, the new Commerce _Products_ menu initially does not display products.

To resolve this issue:

1. Navigate to the _Control Panel_ → _Configuration_ → _Search_.
1. Click _Execute_ next to _Reindex all search indexes_.
1. Wait for the reindex to finish.
1. Navigate to the _Control Panel_ → _Commerce_ → _Products_.
1. Verify all the products are displayed again.

Once reindexing is complete, the new Liferay Commerce instance is ready for use.

## Additional Information

* What's New in Liferay Commerce 2.0
* [Installing Apps Manually](https://help.liferay.com/hc/en-us/articles/360017895412-Installing-Apps-Manually#using-your-file-system-to-install-apps)
* [Liferay Commerce Fix Delivery Method](../../get-help/commerce-enterprise-support/liferay-commerce-fix-delivery-method/README.md)
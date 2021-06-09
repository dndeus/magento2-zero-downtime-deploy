# [Magento 2 Zero Downtime deploy](https://magefan.com/blog/magento-2-zero-downtime-deployment) by [Magefan](https://magefan.com/magento2-extensions)


## Attention! This script is deprecated, we strongly recommend to use [Magento 2 Zero Downtime Deployment Extension](https://magefan.com/magento-2-zero-downtime-deployment).


<a href="https://magefan.com/magento-2-zero-downtime-deployment"><img width="300" height="60" src="https://cm.magefan.com/mf_webp/png/media/wysiwyg/DOWNLOAD_NOW.webp"></a>


  * [Installation](https://magefan.com/blog/magento-2-zero-downtime-deployment#installation)
  * [Configuration](https://magefan.com/blog/magento-2-zero-downtime-deployment#configuration)
  * [Usage](https://magefan.com/blog/magento-2-zero-downtime-deployment#usage)

## 1. Install Magento 2 zero-downtime deployment script
```
wget -O deploy.zip https://github.com/dndeus/magento2-zero-downtime-deploy/archive/master.zip
unzip deploy.zip
rm -f deploy.zip
mv magento2-zero-downtime-deploy-master/ deploy
cp deploy/app/static-content-deploy.sh.sample deploy/app/static-content-deploy.sh
cp app/etc/env.php deploy/app/env.php
echo $'\n'deploy/app/env.php >> .gitignore
chmod +x deploy/run
```

## 2. Configure zero-downtime script
If you use specific static-content deploy commands then edit the file
```
deploy/app/static-content-deploy.sh
```
By default, it has commands to deploy all Magento 2 themes in en_US locale.

If you use Redis or other non-folder storage for session or cache, then edit the file
```
deploy/app/env.php
```
Make sure that the cache and session are stored in a folder.

## 3. Use M2 zero-downtime deploy script

To deploy Magento static content (bin/magento setup:static-content:deploy) with NO downtime, use the CLI command:
```
deploy/run -s
```
To generated code and dependency injection configuration (bin/magento setup:di:compile) with NO downtime, use the CLI command:
```
deploy/run -d
```
You can also run the script with multiple parameters, e.g:
```
deploy/run -d -s
```
To update Magento 2 modules database data and schema (bin/magento setup:upgrade), use the CLI command:
```
deploy/run
```
If you install new extensions then run this command:
```
deploy/run -m Vendor_Module1 Vendor_Module2
```
Note that these commands will also run DI and static content generation and this is the only command that put Magento 2 store into maintenance mode for a few seconds while setup:upgrade is running.

## Magento 2 Extensions by Magefan
  * [Magento 2 Blog Extension](https://magefan.com/magento2-blog-extension)
  * [Magento 2 Blog Plus Extension](https://magefan.com/magento2-blog-extension/pricing)
  * [Magento 2 Blog Extra Extension](https://magefan.com/magento2-blog-extension/pricing)
  * [Magento 2 Login As Customer Extension](https://magefan.com/login-as-customer-magento-2-extension)
  * [Magento 2 Convert Guest to Customer Extension](https://magefan.com/magento2-convert-guest-to-customer)
  * [Magento 2 Facebook Open Graph Extension](https://magefan.com/magento-2-open-graph-extension-og-tags)
  * [Magento 2 Auto Currency Switcher Extension](https://magefan.com/magento-2-currency-switcher-auto-currency-by-country)
  * [Magento 2 Auto Language Switcher Extension](https://magefan.com/magento-2-auto-language-switcher)
  * [Magento 2 GeoIP Switcher Extension](https://magefan.com/magento-2-geoip-switcher-extension)
  * [Magento 2 YouTube Widget Extension](https://magefan.com/magento2-youtube-extension)
  * [Magento 2 Product Widget Advanced Extension](https://magefan.com/magento-2-product-widget)
  * [Magento 2 Conflict Detector Extension](https://magefan.com/magento2-conflict-detector)
  * [Magento 2 Lazy Load Extension](https://magefan.com/magento-2-image-lazy-load-extension)
  * [Magento 2 Rocket JavaScript Extension](https://magefan.com/rocket-javascript-deferred-javascript)
  * [Magento 2 CLI Extension](https://magefan.com/magento2-cli-extension)
  * [Magento Twitter Cards Extension](https://magefan.com/magento-2-twitter-cards-extension)
  * [Magento 2 Mautic Integration Extension](https://magefan.com/magento-2-mautic-extension)
  * [Magento 2 Alternate Hreflang Extension](https://magefan.com/magento2-alternate-hreflang-extension)
  * [Magento 2 Better Order Grid Extension](https://magefan.com/magento-2-better-order-grid-extension)
  * [Magento 2 Admin Email Notifications](https://magefan.com/magento-2-admin-email-notifications)

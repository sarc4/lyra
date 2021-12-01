<h1 align="center">Lyracons - Tienda Amiga</h1>
<p align="center"><a href="https://www.tiendaamiga.com.bo/" target="_blank"><img src="https://www.tiendaamiga.com.bo/media/logo/stores/1/logo.png" alt="Tienda Amiga" width=220></a></p>
  
## Contenido

- [Objetivo del documento](#objetivo-del-documento)
- [Datos generales](#datos-generales)
- [Detalle de los modulos](#detalle-de-los-modulos)
- [Estado actual de las integraciones](#estado-actual-de-las-integraciones)
- [Listado de modulos habilitados](#listado-de-modulos-habilitados)
- [Listado de modulos deshabilitados](#listado-de-modulos-deshabilitados)

## Objetivo del documento
<p>
Se realiza una revisión de la instalación Magento 2.4.0 Cloud para relevar los módulos instalados, la compatibilidad de su versión, su funcionalidad y se relevan si existen customizaciones de código. En ese caso se analizará si cumplen con los estándares de Magento. Se realizará un informe de performance.

Code review Doc: <a href="https://1drv.ms/w/s!AvC6OhHWKuyngf8sYbdJb4kMuq0GXA?e=0XnuM8" target="_blank">DOC</a>
</p>

## Datos generales
<p>
Ambientes:

- <a href="https://mcstaging.tiendaamiga.com.bo/" target="_blank">Staging Front End</a>

- <a href="https://mcstaging.tiendaamiga.com.bo/admin_YkHNH9dENhn84" target="_blank">Staging Back End</a>

- <a href="https://master-7rqtwti-ghyk5x72cay3a.us-5.magentosite.cloud/" target="_blank">Master</a> (actualmente no productivo)

- <a href="https://integration-5ojmyuq-ghyk5x72cay3a.us-5.magentosite.cloud/" target="_blank">Integration</a>

Integration: 

</p>

## Detalle de los modulos

| Modulo | Ubicación | Description | Activo
| ---------- | ----------- | ----------- | -----------:
| Dangs (dangs/tax-info-hide) | app/code | Esta extensión se utiliza para ocultar la información del total de impuestos cuando se aplica. | SI
| Ebizmarts (mailchimp/mc-magento2) | app/code | Es una plataforma externa de email marketing que también permite informar carritos abandonados. | SI
|[Pack Magebig](#Pack-Magebig-contiene) | app/code | Es un Multipurpose Magento 2 pack que contiene el layout y  varios módulos para manejar apariencia de la tienda (cms. widget) y también contiene el ajax para filtros, carrito, buscador etc. Tiene similitudes a lo ofrecido en Mageplaza y Amasty con el layered navigation. En este módulo se esta basando la construcción del theme de  la tienda en  la carpeta “desing/frontend/MageBig/matfury”. | SI
| Magefan/Blog (magefan/module-blog) | app/code | Extensión que te permite administrar  un blog sin tener que depender de ninguna segunda plataforma. No está en uso, tiene solamente un post test. | SI
| Magefan/Community (magefan/module-community) | app/code | Módulo base de Magefan y requerido en cualquier instalación de otro módulo del mismo proveedor. | SI
| Magefan/Product Widget Advanced (magefan/module-wysiwyg-advanced) | app/code | Es un editor que permite cargar un widget de producto, páginas de CMS o contenidos de bloques de CMS utilizando el editor WYSIWYG. También puede insertar Product Widget en bloques específicos en las páginas de su tienda. Está activo pero no veo uso en la tienda. | SI
| Paradox Labs/Cybersource (paradoxlabs/cybersource) | app/code | Es una pasarela de pagos para tarjetas de crédito, es actualmente con lo que están realizando las transacciones a parte de pago en efectivo. | **NO**
| Paradox Labs/Token Base (paradoxlabs/tokenbase) | app/code | Módulo base para los métodos de pago de tokenización de Paradox Labs. | **NO**
| Stamped/Core | app/code | Permite mostrar contenido generado por el usuario (CGU), como reseñas y calificaciones con estrellas, mediante el uso de encuestas automatizadas y formularios en el correo electrónico. Está activo y en uso. | SI
|[Pack Magecomp SMS](#Pack-Magecomp-SMS-contiene) | app/code | Extensión de notificación por SMS. Envía a los clientes avisos sobre diversas actividades de estado de pedidos a través de mensajes de texto. Se encuentra en la versión Pro del pack. Está activo y en uso con un celular de prueba.  | SI
| Mcfadyen/Sap Integration (mcfadyen/module-sapintegration) | app/code | Es el módulo por el cual generan sus integraciones con el sistema SAP, actualmente con el endpoint de test. Endpoint: https://test.apitiendaamiga.com/api/Orders / Carpetas de desarrollos custom a revisar. (Revisar la instalación completa de Mcfayden pack). | SI
| TiendaAmiga | app/code | .. | SI
|[Pack Mageworx](#Pack-Mageworx-contiene) | vendor | Este paquete se encarga de todo lo referido a store locator y pickup llamando a google api para sus operaciones, se encuentra actualmente en su versión 1.6.1. Está activo y en uso. | SI
| Cweagans (weagans/composer-patches) | vendor | Modulo para instalar patches en  Magento 2. | **NO**
| Mageplaza/Social Login (mageplaza/magento-2-social-login) | vendor | Extensión para que el usuario haga un login con sus redes sociales o gmail. Se encuentra en su versión 2.8.3. Se encuentra activo y en uso. | SI
| Mageplaza/Spanish pack (mageplaza/magento-2-spanish-language-pack) | vendor | Realiza el cambio de idioma a través del diccionario de traducción en línea en la tienda Magento 2. Se encuentra en la versión dev-master. Se encuentra activo y en uso. | SI
| Mirasvit Gift (mirasvit/module-gift-registry) | vendor | Permite confeccionar una lista de regalos por parte del cliente. Se encuentra en su versión 1.2.36. Está activo y en uso. | SI
| Magento Cloud MetaPackage (magento/magento-cloud-metapackage) | vendor | Componentes base de cloud para Magento 2.x. Se encuentra en su versión  2.4.0. Está activo y en uso. | SI **~**

<h3>Pack Magebig contiene</h3>

| Modulo | Package
| ----------- | -----------
| magebig/AjaxSearch | magebig/module-ajaxcart
| magebig/module-smartmenu | magebig/ajaxcompare
| magebig/ajaxfilter | magebig/magento-2-social-login
| magebig/AjaxInfiniteScroll | magebig/module-syntaxcms
| magebig/AjaxSearch | magebig/module-widgetplus
| magebig/ajaxwishlist | magebig/module-wysiwygfiles
| magebig/module-newsletter | 

<h3>Pack Magecomp SMS contiene</h3>

| Modulo | Package
| ----------- | -----------
| magecomp/magento-2-base | magecomp/module-smsinfobip
| magecomp/magento-2-international-telephone-input | magecomp/module-smskutility
| magecomp/magento-2-reviewreminder | magecomp/module-smsmsgclub
| magecomp/module-smsbulksms | magecomp/module-smsmsg91
| magecomp/module-smsglobalt | magecomp/module-smsplivo
| magecomp/module-smsgupshup | magecomp/magento-2-smspro
| magecomp/module-smstextlocal | magecomp/module-smstwilio

<h3>Pack Mageworx contiene</h3>

| Modulo | Package
| ----------- | -----------
| mageworx/module-deliverydatemeta | mageworx/module-geoip
| mageworx/module-searchsuiteautocomplete | mageworx/module-geoip
| mageworx/module-storelocatormeta | mageworx/module-geoip

## Estado actual de las integraciones
- <p><h3>Catalogo:</h3>
    Para la integración de precios el cliente cuenta con un middleware que se encarga de captar los cambios en su sistema SAP, estos son colocados en el servidor en formato csv para ser consumidos mediante un cron de Magento vía sftp que se corre periódicamente. (Una vez por dia en la actualidad).</p>

- <p><h3>Stock:</h3>
    La integración de stock se genera mediante dos situaciones:</p>

    1) El middleware que de la misma forma que con los precios deja un csv para ser consumido por un cron de Magento a ejecutar una vez por día.
    2) De forma inmediata mediante la API REST de Magento, esto en las ocasiones especiales que el cliente necesite.

- <p><h3>Ordenes:</h3>
    La tienda  tiene un módulo de integración con el middleware. Recibe una orden por vez y encola el proceso. (En la reunión de integración se barajó la idea de poder lotear la cantidad de órdenes a mandar en días de eventos especiales como el Cyber monday en donde reciben alrededor de 250 en una jornada, diariamente son 10 aproximadas por dia. Esta opción sería configurable.</p>

## Listado de modulos habilitados
| Modulos Habilitados | 
| :----------- | 
Magento_AdminAnalytics
Magento_Store
Magento_AdminGwsStaging
Magento_Directory
Magento_AdobeIms
Magento_AdobeImsApi
Magento_AdobeStockAdminUi
Magento_MediaGallery
Magento_AdobeStockAssetApi
Magento_AdobeStockClient
Magento_AdobeStockClientApi
Magento_AdobeStockImage
Magento_Theme
Magento_AdobeStockImageApi
Magento_Eav
Magento_Customer
Magento_AdvancedPricingImportExport
Magento_Rule
Magento_AdminNotification
Magento_Backend
Magento_Amqp
Magento_AmqpStore
Magento_Config
Magento_User
Magento_Authorization
Magento_Indexer
Magento_Backup
Magento_Variable
Magento_Cms
Magento_Catalog
Magento_Quote
Magento_Bundle
Magento_GraphQl
Magento_BundleImportExport
Magento_BundleImportExportStaging
Magento_SalesSequence
Magento_CacheInvalidate
Magento_MediaStorage
Magento_Payment
Magento_AdvancedCatalog
Magento_Security
Magento_CmsGraphQl
Magento_EavGraphQl
Magento_Search
Magento_StoreGraphQl
Magento_CatalogImportExport
Magento_CatalogImportExportStaging
Magento_Sales
Magento_CatalogInventory
Magento_Checkout
Magento_CatalogPageBuilderAnalytics
Magento_CatalogPageBuilderAnalyticsStaging
Magento_CatalogUrlRewrite
Magento_Widget
Magento_Msrp
Magento_CatalogRuleGraphQl
Magento_SalesRule
Magento_Captcha
Magento_CatalogRule
Magento_Ui
Magento_Downloadable
Magento_GiftCard
Magento_CatalogGraphQl
Magento_Wishlist
Magento_VersionsCms
Magento_CatalogEvent
Magento_CheckoutAddressSearch
Magento_GiftRegistry
Magento_CheckoutAgreements
Magento_CheckoutAgreementsGraphQl
Magento_Staging
Magento_CloudComponents
Magento_MediaGalleryUi
Magento_CatalogCmsGraphQl
Magento_CmsPageBuilderAnalytics
Magento_CmsPageBuilderAnalyticsStaging
Magento_CmsStaging
Magento_CmsUrlRewrite
Magento_CmsUrlRewriteGraphQl
Magento_Integration
Magento_ConfigurableProduct
Magento_CatalogRuleConfigurable
Magento_QuoteGraphQl
Magento_ConfigurableProductSales
Magento_PageCache
Magento_Contact
Magento_Cookie
Magento_Cron
Magento_CurrencySymbol
Magento_CustomAttributeManagement
Magento_AdvancedCheckout
Magento_Analytics
Magento_CustomerBalance
Magento_CustomerBalanceGraphQl
Magento_CatalogWidget
Magento_DownloadableGraphQl
Magento_CustomerFinance
Magento_CustomerGraphQl
Magento_CustomerImportExport
Magento_ProductAlert
Magento_Deploy
Magento_Developer
Magento_Dhl
Magento_AdvancedSearch
Magento_DirectoryGraphQl
Magento_CatalogSearch
Magento_CustomerDownloadableGraphQl
Magento_ImportExport
Magento_WebsiteRestriction
Magento_AdvancedRule
Magento_CatalogCustomerGraphQl
Magento_Elasticsearch
Magento_Elasticsearch6
Magento_Elasticsearch7
Magento_CatalogPermissions
Magento_Email
Magento_EncryptionKey
Magento_Enterprise
Magento_Fedex
Magento_CustomerCustomAttributes
Magento_GiftCardAccount
Magento_GiftCardAccountGraphQl
Magento_GiftCardGraphQl
Magento_GiftCardImportExport
Magento_CustomerSegment
Magento_GiftMessage
Magento_GiftMessageStaging
Magento_Tax
Magento_GiftWrapping
Magento_GiftWrappingStaging
Magento_GoogleAdwords
Magento_GoogleAnalytics
Magento_GoogleOptimizer
Magento_GoogleOptimizerStaging
Magento_GoogleShoppingAds
Magento_TargetRule
Magento_BundleGraphQl
Magento_GraphQlCache
Magento_GroupedProduct
Magento_GroupedImportExport
Magento_GroupedCatalogInventory
Magento_GroupedProductGraphQl
Magento_GroupedProductStaging
Magento_DownloadableImportExport
Magento_AdminGws
Magento_InstantPurchase
Magento_CatalogAnalytics
Magento_Inventory
Magento_InventoryAdminUi
Magento_InventoryAdvancedCheckout
Magento_InventoryApi
Magento_InventoryBundleImportExport
Magento_InventoryBundleProduct
Magento_InventoryBundleProductAdminUi
Magento_InventoryBundleProductIndexer
Magento_InventoryCatalog
Magento_InventorySales
Magento_InventoryCatalogAdminUi
Magento_InventoryCatalogApi
Magento_InventoryCatalogSearch
Magento_InventoryConfigurableProduct
Magento_InventoryConfigurableProductAdminUi
Magento_InventoryConfigurableProductIndexer
Magento_InventoryConfiguration
Magento_InventoryConfigurationApi
Magento_InventoryDistanceBasedSourceSelection
Magento_InventoryDistanceBasedSourceSelectionAdminUi
Magento_InventoryDistanceBasedSourceSelectionApi
Magento_InventoryElasticsearch
Magento_InventoryExportStockApi
Magento_InventoryIndexer
Magento_InventorySalesApi
Magento_InventoryGroupedProduct
Magento_InventoryGroupedProductAdminUi
Magento_InventoryGroupedProductIndexer
Magento_InventoryImportExport
Magento_InventoryInStorePickupApi
Magento_InventoryInStorePickupAdminUi
Magento_InventorySourceSelectionApi
Magento_InventoryInStorePickup
Magento_InventoryInStorePickupGraphQl
Magento_Shipping
Magento_InventoryInStorePickupShippingApi
Magento_InventoryInStorePickupQuoteGraphQl
Magento_InventoryInStorePickupSales
Magento_InventoryInStorePickupSalesApi
Magento_InventoryInStorePickupQuote
Magento_InventoryInStorePickupShipping
Magento_InventoryInStorePickupShippingAdminUi
Magento_Multishipping
Magento_Webapi
Magento_InventoryCache
Magento_InventoryLowQuantityNotification
Magento_Reports
Magento_InventoryLowQuantityNotificationApi
Magento_InventoryMultiDimensionalIndexerApi
Magento_InventoryProductAlert
Magento_InventoryRequisitionList
Magento_InventoryReservations
Magento_InventoryReservationCli
Magento_InventoryReservationsApi
Magento_InventoryExportStock
Magento_InventorySalesAdminUi
Magento_CatalogInventoryGraphQl
Magento_InventorySalesFrontendUi
Magento_InventorySetupFixtureGenerator
Magento_InventoryShipping
Magento_InventoryShippingAdminUi
Magento_InventorySourceDeductionApi
Magento_InventorySourceSelection
Magento_InventoryInStorePickupFrontend
Magento_Invitation
Magento_LayeredNavigation
Magento_LayeredNavigationStaging
Magento_Logging
Magento_LoginAsCustomer
Magento_LoginAsCustomerAdminUi
Magento_LoginAsCustomerApi
Magento_LoginAsCustomerFrontendUi
Magento_LoginAsCustomerLog
Magento_LoginAsCustomerLogging
Magento_LoginAsCustomerPageCache
Magento_LoginAsCustomerQuote
Magento_LoginAsCustomerSales
Magento_LoginAsCustomerWebsiteRestriction
Magento_Marketplace
Magento_MediaContent
Magento_MediaContentApi
Magento_MediaContentCatalog
Magento_MediaContentCatalogStaging
Magento_MediaContentCms
Magento_MediaContentSynchronization
Magento_MediaContentSynchronizationApi
Magento_MediaContentSynchronizationCatalog
Magento_MediaContentSynchronizationCms
Magento_AdobeStockAsset
Magento_MediaGalleryApi
Magento_MediaGalleryCatalog
Magento_MediaGalleryIntegration
Magento_MediaGallerySynchronization
Magento_MediaGallerySynchronizationApi
Magento_AdobeStockImageAdminUi
Magento_MediaGalleryUiApi
Magento_VisualMerchandiser
Magento_MessageQueue
Magento_ConfigurableImportExport
Magento_MsrpConfigurableProduct
Magento_MsrpGroupedProduct
Magento_MsrpStaging
Magento_MultipleWishlist
Magento_InventoryInStorePickupMultishipping
Magento_MysqlMq
Magento_NewRelicReporting
Magento_Newsletter
Magento_OfflinePayments
Magento_OfflineShipping
Magento_Banner
Magento_PageBuilder
Magento_Weee
Magento_BannerPageBuilderAnalytics
Magento_PaymentStaging
Magento_Vault
Magento_Paypal
Magento_PaypalGraphQl
Magento_PaypalOnBoarding
Magento_Persistent
Magento_PersistentHistory
Magento_PricePermissions
Magento_CatalogStaging
Magento_ProductVideo
Magento_ProductVideoStaging
Magento_PromotionPermissions
Magento_CatalogRuleStaging
Magento_QuoteAnalytics
Magento_ConfigurableProductGraphQl
Magento_ReCaptchaAdminUi
Magento_ReCaptchaCheckout
Magento_ReCaptchaContact
Magento_ReCaptchaCustomer
Magento_ReCaptchaFrontendUi
Magento_ReCaptchaMigration
Magento_ReCaptchaNewsletter
Magento_ReCaptchaPaypal
Magento_ReCaptchaReview
Magento_ReCaptchaSendFriend
Magento_ReCaptchaUi
Magento_ReCaptchaUser
Magento_ReCaptchaValidation
Magento_ReCaptchaValidationApi
Magento_ReCaptchaVersion2Checkbox
Magento_ReCaptchaVersion2Invisible
Magento_ReCaptchaVersion3Invisible
Magento_RelatedProductGraphQl
Magento_ReleaseNotification
Magento_Reminder
Magento_InventoryLowQuantityNotificationAdminUi
Magento_RequireJs
Magento_ResourceConnections
Magento_Review
Magento_ReviewAnalytics
Magento_ReviewStaging
Magento_Reward
Magento_RewardGraphQl
Magento_AdvancedSalesRule
Magento_Rma
Magento_RmaGraphQl
Magento_RmaStaging
Magento_Robots
Magento_Rss
Magento_SalesRuleStaging
Magento_CardinalCommerce
Magento_SalesAnalytics
Magento_SalesArchive
Magento_SalesGraphQl
Magento_SalesInventory
Magento_BannerCustomerSegment
Magento_RewardStaging
Magento_DownloadableStaging
Magento_UrlRewrite
Magento_ScalableCheckout
Magento_ScalableInventory
Magento_ScalableOms
Magento_ScheduledImportExport
Magento_CatalogUrlRewriteStaging
Magento_SearchStaging
Magento_CustomerAnalytics
Magento_Securitytxt
Magento_SendFriend
Magento_SendFriendGraphQl
Magento_InventoryInStorePickupSalesAdminUi
Magento_Sitemap
Magento_StagingGraphQl
Magento_CatalogStagingGraphQl
Magento_StagingPageBuilder
Magento_GiftCardStaging
Magento_UrlRewriteGraphQl
Magento_Support
Magento_Swagger
Magento_SwaggerWebapi
Magento_SwaggerWebapiAsync
Magento_Swatches
Magento_SwatchesGraphQl
Magento_SwatchesLayeredNavigation
Magento_BundleStaging
Magento_ConfigurableProductStaging
Magento_TaxGraphQl
Magento_TaxImportExport
Magento_GoogleTagManager
Magento_ThemeGraphQl
Magento_Tinymce3
Magento_Tinymce3Banner
Magento_Translation
Magento_CheckoutStaging
Magento_Ups
Magento_SampleData
Magento_CatalogUrlRewriteGraphQl
Magento_AsynchronousOperations
Magento_Usps
Magento_InventoryGraphQl
Magento_PaypalCaptcha
Magento_VaultGraphQl
Magento_Version
Magento_BannerPageBuilder
Magento_VersionsCmsUrlRewrite
Magento_CatalogStagingPageBuilder
Magento_InventoryInStorePickupWebapiExtension
Magento_WebapiAsync
Magento_WebapiSecurity
Magento_ElasticsearchCatalogPermissions
Magento_CatalogInventoryStaging
Magento_WeeeGraphQl
Magento_WeeeStaging
Magento_PageBuilderAnalytics
Magento_CheckoutAddressSearchGiftRegistry
Magento_WishlistAnalytics
Magento_WishlistGraphQl
Aheadworks_Sbp
Amazon_Core
Amazon_Login
Amazon_Payment
CyberSource_AccountUpdater
CyberSource_Core
CyberSource_ApplePay
CyberSource_Atp
CyberSource_BankTransfer
CyberSource_SecureAcceptance
CyberSource_ECheck
CyberSource_GooglePay
CyberSource_KlarnaFinancial
CyberSource_VisaCheckout
CyberSource_Address
CyberSource_Tax
CyberSource_ThreeDSecure
CyberSource_PayPal
CyberSource_WeChatPay
Dangs_TaxInfoHide
Dotdigitalgroup_Email
Dotdigitalgroup_Chat
Dotdigitalgroup_Enterprise
Ebizmarts_MailChimp
Fastly_Cdn
Klarna_Core
Klarna_Ordermanagement
Klarna_Onsitemessaging
Klarna_Kp
Lyracons_GoogleTagManagerEnhanced
MageBig_MbLib
MageBig_AjaxInfiniteScroll
MageBig_Ajaxcompare
MageBig_Ajaxwishlist
MageBig_MbFrame
MageBig_AjaxCart
MageBig_NewsPopup
MageBig_QuickView
MageBig_SmartMenu
MageBig_SyntaxCms
MageBig_WidgetPlus
MageBig_WysiwygFiles
MageWorx_DeliveryDate
MageWorx_GeoIP
MageWorx_GoogleApi
MageWorx_Info
MageWorx_Locations
MageWorx_StoreLocator
MageWorx_Pickup
MageWorx_LocationPages
Magecomp_Base
Magecomp_Smspro
Magecomp_Reviewreminder
Magecomp_Smsbulksms
Magecomp_Smsglobal
Magecomp_Smsgupshup
Magecomp_Smsinfobip
Magecomp_Smskutility
Magecomp_Smsmsg91
Magecomp_Smsmsgclub
Magecomp_Smsplivo
Magecomp_Countryflag
Magecomp_Smstextlocal
Magecomp_Smstwilio
Magefan_Community
Magefan_Blog
Magefan_WysiwygAdvanced
Mageplaza_Core
Mageplaza_GoogleRecaptcha
Mageplaza_Smtp
Mageplaza_SocialLogin
McFadyen_AjaxWishlist
McFadyen_Catalog
McFadyen_CategoryImage
McFadyen_Checkout
McFadyen_CustomOptions
McFadyen_Customer
McFadyen_Fastly
McFadyen_Imports
McFadyen_PriceSort
McFadyen_Sales
McFadyen_SapIntegration
McFadyen_SapInventoryCheck
McFadyen_SapOrderExport
McFadyen_ShippingZone
McFadyen_SmsCustomerAccountRecovery
McFadyen_SocialLogin
McFadyen_StoreLocator
McFadyen_Wishlist
Mirasvit_Core
Mirasvit_Giftr
Temando_ShippingRemover
TiendaAmiga_Csp
TiendaAmiga_CybersourceMdd
TiendaAmiga_McFadyenExtended
Vertex_Tax
Vertex_AddressValidation
Yotpo_Yotpo

## Listado de modulos deshabilitados
| Modulos Deshabilitados | 
| :----------- |
Magento_Csp
Magento_TwoFactorAuth
MageBig_AjaxFilter
MageBig_AjaxSearch
MageBig_SocialLogin
MageWorx_SearchSuiteAutocomplete
PayPal_Braintree
PayPal_BraintreeGraphQl
Stamped_Core
TiendaAmiga_MageBigBundle 


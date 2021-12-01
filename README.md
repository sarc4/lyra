<p align="center"><a href="https://www.tiendaamiga.com.bo/" target="_blank"><img src="https://www.tiendaamiga.com.bo/media/logo/stores/1/logo.png" alt="Tienda Amiga" width=220></a><h2 align="center">Lyracons - Tienda Amiga</h2></p>
  
## Contenido

- [Objetivo del documento](#objetivo-del-documento)
- [Datos generales](#datos-generales)
- [Detalle de los modulos](#detalle-de-los-modulos)
- [Estado actual de las integraciones](#estado-actual-de-las-integraciones)

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

| Modulo | Ubicación | Description
| ---------- | ----------- | -----------
| Dags (dangs/tax-info-hide) | app/code | Esta extensión se utiliza para ocultar la información del total de impuestos cuando se aplica.
| Ebizmarts (mailchimp/mc-magento2) | app/code | Es una plataforma externa de email marketing que también permite informar carritos abandonados.
|[Pack Magebig](#Pack-Magebig-contiene) | app/code | Es un Multipurpose Magento 2 pack que contiene el layout y  varios módulos para manejar apariencia de la tienda (cms. widget) y también contiene el ajax para filtros, carrito, buscador etc. Tiene similitudes a lo ofrecido en Mageplaza y Amasty con el layered navigation. En este módulo se esta basando la construcción del theme de  la tienda en  la carpeta “desing/frontend/MageBig/matfury”. Está activo y en uso.
| Magefan/Blog (magefan/module-blog) | app/code | Extensión que te permite administrar  un blog sin tener que depender de ninguna segunda plataforma. No está en uso, tiene solamente un post test.
| Magefan/Community (magefan/module-community) | app/code | Módulo base de Magefan y requerido en cualquier instalación de otro módulo del       mismo proveedor.
| Magefan/Product Widget Advanced (magefan/module-wysiwyg-advanced) | app/code | Es un editor que permite cargar un widget de producto, páginas de CMS o contenidos de bloques de CMS utilizando el editor WYSIWYG. También puede insertar Product Widget en bloques específicos en las páginas de su tienda. Está activo pero no veo uso en la tienda.
| Paradox Labs/Cybersource (paradoxlabs/cybersource) | app/code | Es una pasarela de pagos para tarjetas de crédito, es actualmente con lo que están realizando las transacciones a parte de pago en efectivo. Está activo y en uso.
| Paradox Labs/Token Base (paradoxlabs/tokenbase) | app/code | Módulo base para los métodos de pago de tokenización de Paradox Labs. Está activo y en uso.
| Stamped/Core | app/code | Permite mostrar contenido generado por el usuario (CGU), como reseñas y calificaciones con estrellas, mediante el uso de encuestas automatizadas y formularios en el correo electrónico. Está activo y en uso.
|[Pack Magecomp SMS](#Pack-Magecomp-SMS-contiene) | app/code | Extensión de notificación por SMS. Envía a los clientes avisos sobre diversas actividades de estado de pedidos a través de mensajes de texto. Se encuentra en la versión Pro del pack. Está activo y en uso con un celular de prueba. 
| Mcfadyen/Sap Integration (mcfadyen/module-sapintegration) | app/code | Es el módulo por el cual generan sus integraciones con el sistema SAP, actualmente con el endpoint de test. Endpoint: https://test.apitiendaamiga.com/api/Orders / Carpetas de desarrollos custom a revisar. (Revisar la instalación completa de Mcfayden pack).
|[Pack Mageworx](#Pack-Mageworx-contiene) | vendor | Este paquete se encarga de todo lo referido a store locator y pickup llamando a google api para sus operaciones, se encuentra actualmente en su versión 1.6.1. Está activo y en uso. 
| Cweagans (weagans/composer-patches) | vendor | Modulo para instalar patches en  Magento 2. Está activo y en uso.
| Mageplaza/Social Login (mageplaza/magento-2-social-login) | vendor | Extensión para que el usuario haga un login con sus redes sociales o gmail. Se encuentra en su versión 2.8.3. Se encuentra activo y en uso.
| Mageplaza/Spanish pack (mageplaza/magento-2-spanish-language-pack) | vendor | Realiza el cambio de idioma a través del diccionario de traducción en línea en la tienda Magento 2. Se encuentra en la versión dev-master. Se encuentra activo y en uso.
| Mirasvit Gift (mirasvit/module-gift-registry) | vendor | Permite confeccionar una lista de regalos por parte del cliente. Se encuentra en su versión 1.2.36. Está activo y en uso.
| Magento Cloud MetaPackage (magento/magento-cloud-metapackage) | vendor | Componentes base de cloud para Magento 2.x. Se encuentra en su versión  2.4.0. Está activo y en uso.

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
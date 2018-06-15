# Piwik for Joomla 1.0


##簡介 Introduction 
本外掛可以直接整合Joomla，直接呼叫Piwik API，不使用Javascript，從HTML Code完全看不出有安裝第三方的流量分析工具，也不使用Cookie，完全符合GDPR的規範
This plugin allows you to integrate Piwik in your Joomla site, while not using any client-side code. The benefit of this is first of all that the Piwik integration will not slow down the client side loading. Additionally, it is fully compliant with EU cookie-regulations and requires no cookie banner to ask for user permission. All tracking is done on the server side.

##安裝 Setup
- Install the plugin in the Extension Manager
- Enable the plugin in the Plugin Manager
- Configure your Piwik API in the plugin settings

##使用 Usage
- Install this plugin using the Extension Manager
- Within the Plugin Manager, enable and configure this plugin
- Configure the (numeric) website ID: This is found under the Websites-tab in Piwik itself.
- Configure the API-token. This is found under the API-page in Piwik.

如果您的Joomla網站有自訂的404錯誤頁面，您必須修改佈景主題內的error.php檔案，將下面的PHP程式加到此檔案內
To use Piwik within your 404 pages as well, you need to modify the error.php file of your Joomla template. Add the following code:

    include_once JPATH_SITE . '/plugins/system/piwik/piwik.php';
    if (class_exists('PlgSystemPiwik')) {
        PlgSystemPiwik::callPiwik();
    }



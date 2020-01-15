---
title: Configurazione di Internet Information Services 7.0 per Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 41eedcf78d8ca6f10fcd0380e43420dcc1b328f1
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964514"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Configurazione di Internet Information Services 7.0 per Windows Communication Foundation

Internet Information Services (IIS) 7.0 dispone di una progettazione modulare che consente di installare in modo selettivo i componenti necessari. This design is based on the new manifest-driven componentization technology introduced in Windows Vista. There are more than 40 standalone feature components of IIS 7.0 that can be installed independently. I professionisti IT possono così personalizzare con facilità l'installazione in base alle esigenze. This topic discusses how to configure IIS 7.0 for use with Windows Communication Foundation (WCF) and determine which components are required.

## <a name="minimal-installation-installing-was"></a>Installazione minima: installazione di WAS
 The minimal installation of the whole IIS 7.0 package is to install the Windows Process Activation Service (WAS). WAS is a standalone feature and it is the only feature from the IIS 7.0 that is available for all Windows Vista operating systems (Home Basic, Home Premium, Business, and Ultimate and Enterprise).

 From the Control Panel, click **Programs** and then click **Turn Windows features on or off** which is listed under **Programs and Features**, the WAS component is shown in the list as in the following illustration.

 ![Turn Features On or Off Dialog](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")

 Questa funzionalità presenta i sottocomponenti seguenti:

- Ambiente .NET

- API di configurazione

- Modello di processo

 If you select the root node of WAS, only the **Process Model** sub-node is checked by default. Si noti che con questa installazione verrà installato solo il servizio WAS poiché non è disponibile alcun supporto per un server Web.

 To make WCF or any ASP.NET application work, check the **.NET Environment** checkbox. This means that all of WAS components are required to make WCF and ASP.NET to work well. Questi verranno selezionati automaticamente una volta installati tali componenti.

## <a name="iis-70-default-installation"></a>IIS 7.0: installazione predefinita
 By checking the **Internet Information Services** feature, some of the sub-nodes are automatically checked as shown in the following illustration.

 ![Default settings for IIS 7.0 features](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")

 This is the default installation of IIS 7.0. With this installation, you can use IIS 7.0 to service static content (such as HTML pages and other content). However, you cannot run ASP.NET or CGI applications or host WCF services.

## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: installazione con supporto ASP.NET
 You must install ASP.NET to make ASP.NET work on IIS 7.0. After checking **ASP.NET**, your screen should look like the following illustration.

 ![Asp.NET required settings](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")

 This is the minimal environment for both WCF and ASP.NET applications to work in IIS 7.0.

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: installazione con componenti compatibilità gestione IIS 6.0
 When installing IIS 7.0 on a system with Visual Studio 2005 or some other automation scripts or tools (such as Adsutil.vbs) that configure virtual applications that use IIS 6.0 Metabase API, ensure that you check the IIS 6.0 **Scripting Tools**. This automatically checks the other sub-nodes of IIS 6.0 **Management Compatibility**. The following illustration shows the screen after this is done:

 ![IIS 6.0 Management Compatibility Settings](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")

 With this installation, you have everything required to use IIS 7.0, ASP.NET and WCF features and samples available on the Web.

## <a name="request-limits"></a>Limiti richiesta
 In Windows Vista con IIS 7 il valore predefinito del `maxUri` e le impostazioni di `maxQueryStringSize` sono state modificate. Per impostazione predefinita, il filtro di richiesta in IIS 7.0 consente una lunghezza dell'URL di 4096 caratteri e una lunghezza della stringa di query di 2048 caratteri. Per modificare questi valori predefiniti, aggiungere il codice XML seguente al file App.config:

```xml
 <system.webServer>
    <security>
        <requestFiltering>
            <requestLimits maxUrl="8192" maxQueryString="8192" />
        </requestFiltering>
    </security>
 </system.webServer>
 ```

## <a name="see-also"></a>Vedere anche

- [Architettura di attivazione di WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [Configurazione di WAS per l'uso con WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [Procedura: Installare e configurare componenti di attivazione WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))

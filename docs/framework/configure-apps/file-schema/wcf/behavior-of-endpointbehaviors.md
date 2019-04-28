---
title: <behavior> di <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 34306f99f2343c987700e964aaa9800aa3f488fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673550"
---
# <a name="behavior-of-endpointbehaviors"></a>\<comportamento > di \<endpointBehaviors >
L'elemento `behavior` contiene una raccolta di impostazioni per il comportamento di un endpoint. Ogni comportamento è indicizzato in base al relativo `name`. Gli endpoint possono essere collegati a ciascun comportamento tramite questo nome. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|name|Stringa univoca che contiene il nome di configurazione del comportamento. Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per altre informazioni sulla configurazione predefinita e associazioni privi di nome e i comportamenti, vedere [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) e [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Specifica le credenziali usate per autenticare il client presso un servizio.|  
|[\<callbackDebug>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbackdebug.md)|Specifica il debug del servizio per un oggetto di callback Windows Communication Foundation (WCF).|  
|[\<callbackTimeouts>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbacktimeouts.md)|Specifica il timeout per il callback client.|  
|[\<clientVia>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientvia.md)|Specifica la route che un messaggio deve prendere.|  
|[\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer.md)|Contiene i dati di configurazione per DataContractSerializer.|  
|[\<dispatcherSynchronization>](../../../../../docs/framework/configure-apps/file-schema/wcf/dispatchersynchronization.md)|Specifica un comportamento dell'endpoint che consente a un servizio di inviare risposte in modo asincrono.|  
|[\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)|Abilita il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX. Questo comportamento deve essere usato solo in combinazione con il \<webHttpBinding > associazione standard, o \<webMessageEncoding > elemento di associazione.|  
|[\<endpointDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.|  
|[\<soapProcessing>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)|Definisce il comportamento dell'endpoint client usato per effettuare il marshalling dei messaggi tra versioni del messaggio e tipi di associazione diversi.|  
|[\<synchronousReceive>](../../../../../docs/framework/configure-apps/file-schema/wcf/synchronousreceive-element.md)|Specifica il comportamento di run-time per la ricezione di messaggi in un'applicazione client o di servizio. Non prevede attributi o elementi figlio.|  
|[\<transactedBatching>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactedbatching.md)|Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.|  
|[\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)|Specifica il WebHttpBehavior in un endpoint tramite configurazione. Questo comportamento, quando viene usato in combinazione con il \<webHttpBinding > associazione standard, attiva il modello di programmazione Web per un servizio WCF.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<endpointBehaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|Raccolta di elementi di comportamento dell'endpoint.|

---
title: <behavior> di <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 489678a5adeae3965acae90a847c4b087478354d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140804"
---
# <a name="behavior-of-endpointbehaviors"></a>\<behavior> di \<endpointBehaviors>
L'elemento `behavior` contiene una raccolta di impostazioni per il comportamento di un endpoint. Ogni comportamento è indicizzato in base al relativo `name`. Gli endpoint possono essere collegati a ciascun comportamento tramite questo nome. A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
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
|name|Stringa univoca che contiene il nome di configurazione del comportamento. Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento. A partire da .NET Framework 4, le associazioni e i comportamenti non devono avere un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Specifica le credenziali usate per autenticare il client presso un servizio.|  
|[\<callbackDebug>](callbackdebug.md)|Specifica il debug del servizio per un oggetto callback di Windows Communication Foundation (WCF).|  
|[\<callbackTimeouts>](callbacktimeouts.md)|Specifica il timeout per il callback client.|  
|[\<clientVia>](clientvia.md)|Specifica la route che un messaggio deve prendere.|  
|[\<dataContractSerializer>](datacontractserializer.md)|Contiene i dati di configurazione per DataContractSerializer.|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|Specifica un comportamento dell'endpoint che consente a un servizio di inviare risposte in modo asincrono.|  
|[\<enableWebScript>](enablewebscript.md)|Abilita il comportamento dell'endpoint che rende possibile l'uso del servizio da pagine Web ASP.NET AJAX. Il comportamento deve essere usato solo in combinazione con l' \<webHttpBinding> associazione standard o con l' \<webMessageEncoding> elemento di associazione.|  
|[\<endpointDiscovery>](endpointdiscovery.md)|Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.|  
|[\<soapProcessing>](soapprocessing.md)|Definisce il comportamento dell'endpoint client usato per effettuare il marshalling dei messaggi tra versioni del messaggio e tipi di associazione diversi.|  
|[\<synchronousReceive>](synchronousreceive-element.md)|Specifica il comportamento di run-time per la ricezione di messaggi in un'applicazione client o di servizio. Non prevede attributi o elementi figlio.|  
|[\<transactedBatching>](transactedbatching.md)|Specifica se il batch delle transazioni è supportato per le operazioni di ricezione.|  
|[\<webHttp>](webhttp.md)|Specifica il WebHttpBehavior in un endpoint tramite configurazione. Questo comportamento, se utilizzato in combinazione con l' \<webHttpBinding> associazione standard, Abilita il modello di programmazione Web per un servizio WCF.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Raccolta di elementi di comportamento dell'endpoint.|

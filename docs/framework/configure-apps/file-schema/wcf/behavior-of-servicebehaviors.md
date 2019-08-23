---
title: <behavior> di <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 8c847368934cc4cd8ccaab017ede00b7b8963897
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926411"
---
# <a name="behavior-of-servicebehaviors"></a>\<comportamento > di \<serviceBehaviors >
L'elemento `behavior` contiene una raccolta di impostazioni per il comportamento di un servizio. Ogni comportamento è indicizzato in base al relativo `name`. I servizi possono collegarsi a ogni comportamento tramite questo nome `behaviorConfiguration` usando l'attributo [ \<](endpoint-element.md) dell'elemento > dell'endpoint. In questo modo gli endpoint possono condividere configurazioni del comportamento comuni senza ridefinire le impostazioni. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
> Gli elementi di comportamento specifici delle attività del flusso di lavoro di Windows, ad esempio l' [ \<elemento > sendMessageChannelCache](../windows-workflow-foundation/sendmessagechannelcache.md) , sono documentati nella pagina relativa al [ \<comportamento > della pagina > di \<serviceBehaviors](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) .  
  
 \<system.ServiceModel>  
\<comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|name|Stringa univoca che contiene il nome di configurazione del comportamento. Questo valore è una stringa definita dall'utente che deve essere univoca in quanto funge da stringa di identificazione dell'elemento. A partire da [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], non è necessario che le associazioni e i comportamenti dispongano di un nome. Per ulteriori informazioni sulla configurazione predefinita e le associazioni e i comportamenti senza nome, vedere [Configurazione semplificata](../../../wcf/simplified-configuration.md) e [Configurazione semplificata per i servizi WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-element.md)|Contiene i dati di configurazione per DataContractSerializer.|  
|[\<persistenceProvider>](persistenceprovider.md)|Specifica il tipo di implementazione del provider di persistenza da usare, nonché il timeout da usare per le operazioni di persistenza.|  
|[\<routing>](routing-of-servicebehavior.md)|Fornisce l'accesso in fase di esecuzione al servizio di routing per consentire la modifica dinamica della configurazione di routing.|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|Fornisce un elemento di configurazione del flusso di lavoro che stabilisce a livello di servizio la validità di una trasmissione, di un messaggio o di un creatore.|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|Specifica le impostazioni che autorizzano l'accesso alle operazioni del servizio.|  
|[\<serviceCredentials>](servicecredentials.md)|Specifica la credenziale da usare nell'autenticazione del servizio e le impostazioni relative alla convalida delle credenziali client.|  
|[\<serviceDebug>](servicedebug.md)|Specifica le funzionalità di debug e di informazioni della Guida per un servizio Windows Communication Foundation (WCF).|  
|[\<serviceDiscovery>](servicediscovery.md)|Specifica l'individuabilità degli endpoint del servizio.|  
|[\<serviceMetadata>](servicemetadata.md)|Specifica la pubblicazione dei metadati del servizio e delle informazioni associate.|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|Specifica impostazioni che abilitano controllo di eventi di sicurezza durante le operazioni del servizio.|  
|[\<serviceThrottling>](servicethrottling.md)|Specifica il meccanismo di limitazione di un servizio WCF.|  
|[\<serviceTimeouts>](servicetimeouts.md)|Specifica il timeout per un servizio.|  
|[\<workflowRuntime>](workflowruntime.md)|Specifica le impostazioni per un'istanza di WorkflowRuntime per l'hosting di servizi WCF basati sul flusso di lavoro.|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|Abilita il recupero di informazioni sull'indirizzo di metadati dalle intestazioni del messaggio di richiesta.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|Raccolta di elementi di comportamento del servizio.|

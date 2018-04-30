---
title: '&lt;sendMessageChannelCache&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 739115dfdf26dd184d4fc217a1819dda7d7c73a0
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="ltsendmessagechannelcachegt"></a>&lt;sendMessageChannelCache&gt;
Un comportamento del servizio che consente la personalizzazione della condivisione a livelli, le impostazioni della cache della channel factory e le impostazioni della cache del canale per i flussi di lavoro che inviano messaggi agli endpoint del servizio tramite l'attività di messaggistica di trasmissione della cache.  
  
\<system.ServiceModel>  
\<i comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
\<sendMessageChannelCache >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|allowUnsafeCaching|Valore booleano che indica se attivare la memorizzazione nella cache. Se il servizio flusso di lavoro dispone di associazioni o comportamenti personalizzati, la memorizzazione nella cache potrebbe non essere sicura e pertanto essere disabilitata per impostazione predefinita. Tuttavia, se si desidera attivare la memorizzazione nella cache in impostare questa proprietà su **true**.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<channelSettings >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|Specifica le impostazioni della cache del canale.|  
|[\<factorySettings >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|Specifica le impostazioni della cache della channel factory.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<comportamento > di \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Specifica un elemento di comportamento.|  
  
## <a name="remarks"></a>Note  
 Questo comportamento del servizio è designato per flussi di lavoro che inviano messaggi a endpoint di servizio. Questi sono in genere flussi di lavoro del client ma potrebbero essere anche servizi del flusso di lavoro ospitati in un oggetto <xref:System.ServiceModel.WorkflowServiceHost>.  
  
 Per impostazione predefinita, in un flusso di lavoro ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache usata da attività di messaggistica <xref:System.ServiceModel.Activities.Send> è condivisa attraverso tutte le istanze del flusso di lavoro in <xref:System.ServiceModel.WorkflowServiceHost> (memorizzazione nella cache a livello di host). Per un flusso di lavoro del client che non è ospitato da un oggetto <xref:System.ServiceModel.WorkflowServiceHost>, la cache è disponibile solo all'istanza del flusso di lavoro (memorizzazione nella cache a livello di istanza). Per impostazione predefinita, la memorizzazione nella cache è disabilitata per qualsiasi attività di invio nel flusso di lavoro che dispone di endpoint definiti nella configurazione.  
  
 Per ulteriori informazioni su come modificare la cache predefinita condivisione livelli e le impostazioni della cache per la channel factory e cache del canale, vedere [modifica dei livelli di condivisione della Cache per le attività di trasmissione](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).  
  
## <a name="example"></a>Esempio  
 In un servizio flusso di lavoro ospitato è possibile specificare le impostazioni della cache della factory e della cache del canale nel file di configurazione dell'applicazione. A tale scopo, aggiungere un comportamento del servizio contenente le impostazioni della cache della factory e del canale e aggiungere tale comportamento al servizio. Nell'esempio seguente viene illustrato il contenuto di un file di configurazione che contiene il **MyChannelCacheBehavior** comportamento del servizio con le impostazioni della cache factory personalizzata cache e canale. Questo comportamento del servizio viene aggiunto al servizio tramite il **behaviorConfiguarion** attributo.  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 [Modifica dei livelli di condivisione della cache per le attività Send](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)

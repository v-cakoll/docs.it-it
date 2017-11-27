---
title: '&lt;findCriteria&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b428d1a95ec6f1f493c831f66223f52e4723990c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltfindcriteriagt"></a>&lt;findCriteria&gt;
Elemento di configurazione che fornisce un set di criteri usati da un'applicazione client per la ricerca di un servizio di individuazione. I criteri possono essere raggruppati nei criteri di ricerca (specificando i servizi da cercare) e i criteri di terminazione (quanto tempo deve durare la ricerca).  
  
 \<System. ServiceModel >  
\<standardEndpoints >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|duration|Valore Timespan che specifica il tempo massimo di attesa per le risposte dai servizi in una rete. La durata predefinita è 20 secondi.|  
|maxResults|Integer che specifica il numero massimo di risposte da attendere dai servizi in una rete o su Internet. Se il numero massimo di risposte viene ricevuto prima della scadenza del valore specificato nell'attributo `duration`, l'operazione di ricerca termina.|  
|scopeMatchBy|URI che specifica l'algoritmo di corrispondenza da usare per trovare la corrispondenza tra l'ambito nel messaggio del Probe e quello dell'endpoint.<br /><br /> Sono supportate cinque regole di corrispondenza degli ambiti. Se non si specifica una regola di corrispondenza degli ambiti, verrà usato `ScopeMatchByPrefix`. Per altre informazioni in merito, vedere <xref:System.ServiceModel.Discovery.FindCriteria>.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<contractTypeNames >](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|Raccolta di elementi di configurazione contenenti i nomi dei tipi di contratto del servizio flusso di lavoro.|  
|\<estensioni > di \<findCriteria >|Raccolta di oggetti di elementi XML che forniscono estensioni.|  
|[\<gli ambiti >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Raccolta di oggetti contenenti URI assoluti usati durante un'operazione di ricerca per l'individuazione di uno o più servizi specifici.<br /><br /> Se il servizio specifico viene trovato, significa che è stata trovata una corrispondenza esatta tra l'URI del servizio e l'URI dell'ambito, talvolta con il supporto di regole di ambito che gestiscono i problemi di corrispondenza.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<standardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Contiene le impostazioni necessarie a un'applicazione per partecipare al processo di individuazione del servizio come client.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>

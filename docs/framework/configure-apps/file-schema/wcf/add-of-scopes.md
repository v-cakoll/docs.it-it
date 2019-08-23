---
title: <add> di <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: b190cb72e21d47bdc62aab2daba0f6eea1ee04ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926622"
---
# <a name="add-of-scopes"></a>\<aggiungere > degli \<ambiti >
Aggiunge URI di ambito personalizzato che è possibile usare per filtrare gli endpoint di servizio durante l'esecuzione di query.  
  
\<system.ServiceModel>  
\<comportamenti >  
\<endpointBehaviors>  
\<comportamento >  
\<endpointDiscovery>  
\<ambiti >  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|scope|URI contenente informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<ambiti >](scopes.md)|Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>

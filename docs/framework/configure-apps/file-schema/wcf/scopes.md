---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: eee6382c578648866045fd9b283454d9e0e76fcb
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275024"
---
# <a name="scopes"></a>\<gli ambiti >
Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.  
  
\<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<endpointDiscovery>  
\<gli ambiti >  
  
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
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|Aggiunge le informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<endpointDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|Specifica le varie impostazioni di individuazione per un endpoint, quali l'individuazione, gli ambiti e le eventuali estensioni personalizzate ai relativi metadati.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>

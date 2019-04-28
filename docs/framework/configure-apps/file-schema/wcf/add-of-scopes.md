---
title: <add> di <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: c29e47f688118e34fbdb4deb396c930d478f0582
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673602"
---
# <a name="add-of-scopes"></a>\<aggiungere > di \<ambiti >
Aggiunge URI di ambito personalizzato che è possibile usare per filtrare gli endpoint di servizio durante l'esecuzione di query.  
  
\<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<endpointDiscovery>  
\<gli ambiti >  
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
|ambito|URI contenente informazioni sull'ambito per l'endpoint che è possibile usare nei criteri di corrispondenza per la ricerca di servizi.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<gli ambiti >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Contiene una raccolta di elementi di configurazione che specificano URI di ambito personalizzati che è possibile usare per filtrare gli endpoint del servizio durante l'esecuzione di query.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>

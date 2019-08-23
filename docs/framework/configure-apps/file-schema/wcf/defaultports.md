---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925881"
---
# <a name="defaultports"></a>\<> defaultPorts
Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.  
  
\<system.ServiceModel>  
\<comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
\<useRequestHeadersForMetadataAddress>  
\<> defaultPorts  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<aggiungere > di \<defaultPorts >](add-of-defaultports.md)|Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|Elenco di porte predefinite.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>

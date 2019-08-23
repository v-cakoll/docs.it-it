---
title: <add> di <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: d2723dad14a63c4b05fdb70157f7eb21d193d3ab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926701"
---
# <a name="add-of-defaultports"></a>\<aggiungere > di \<defaultPorts >
Endpoint di comunicazione predefinito sul quale l'applicazione client è in ascolto.  
  
 \<system.ServiceModel>  
\<comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
\<useRequestHeadersForMetadataAddress>  
\<> defaultPorts  
\<add>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|port|Integer che specifica il numero della porta di comunicazione predefinita.|  
|scheme|Stringa che specifica il gruppo di impostazioni del protocollo associato a una porta di comunicazione.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|Raccolta di porte predefinite in cui sono elencati gli endpoint di comunicazione predefiniti sui quali l'applicazione client è in ascolto.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.DefaultPortElement>

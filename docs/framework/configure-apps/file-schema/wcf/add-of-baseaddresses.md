---
title: <add> di <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: a94c5144d907c26e6f5eef09b1a17b17eb6c9e0f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920225"
---
# <a name="add-of-baseaddresses"></a>\<aggiungere > di \<baseAddresses >
Rappresenta un elemento di configurazione che specifica indirizzi di base usati dall'host del servizio.  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
\<> host  
\<baseAddresses>  
\<baseAddress>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a>Type  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|`baseAddress`|Stringa che specifica un indirizzo di base usato dall'host del servizio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|Raccolta di elementi `baseAddress`.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [Hosting](../../../wcf/feature-details/hosting.md)

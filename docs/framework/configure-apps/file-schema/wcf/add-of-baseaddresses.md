---
title: '&lt;add&gt; di &lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: 31edf570a7374a4b4fe31760d35ec196ecfcb3c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553568"
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a>&lt;add&gt; di &lt;baseAddresses&gt;
Rappresenta un elemento di configurazione che specifica indirizzi di base usati dall'host del servizio.  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
\<host>  
\<baseAddresses>  
\<baseAddress>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`baseAddress`|Stringa che specifica un indirizzo di base usato dall'host del servizio.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<baseAddresses>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Raccolta di elementi `baseAddress`.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)

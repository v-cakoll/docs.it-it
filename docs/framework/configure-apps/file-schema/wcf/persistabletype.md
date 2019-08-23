---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: fcfd338e289b5151688724f0e84b6878707d32be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933829"
---
# <a name="persistabletype"></a>\<persistableType>
Specifica tutti i tipi persistenti.  
  
 \<system.ServiceModel>  
\<comContracts>  
\<comContract>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a>Type  
 `Type`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|id|Un attributo obbligatorio che contiene una stringa che specifica un identificatore univoco per un tipo persistente.|  
|name|Attributo facoltativo contenente una stringa che specifica il nome del tipo persistente.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuna  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|Raccolta di elementi `persistableType`.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [Integrazione con applicazioni COM+](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Procedura: Configurare le impostazioni del servizio COM+](../../../wcf/feature-details/how-to-configure-com-service-settings.md)

---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855078"
---
# <a name="persistabletype"></a>\<persistableType>
Specifica tutti i tipi persistenti.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comcontratti >** ](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> comContract**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> persistableTypes**](persistabletypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> persistableType**  
  
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
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|Raccolta di elementi `persistableType`.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [Integrazione con applicazioni COM+](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [Procedura: Configurare le impostazioni del servizio COM+](../../../wcf/feature-details/how-to-configure-com-service-settings.md)

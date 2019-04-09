---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 22ef3c3c6d23d6c68c27d6b5d1ed35b7c9910d48
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230798"
---
# <a name="parameter"></a>\<Parametro >
Specifica il parametro generico quando un tipo dichiarato è un tipo generico.  
  
 \<system.runtime.serialization>  
\<dataContractSerializer>  
\<declaredTypes > elemento  
\<aggiungere > (elemento) per \<declaredTypes >  
\<knownType > elemento  
\<parametro > elemento  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|indice|Quando il tipo dichiarato è un tipo generico, specifica il parametro generico che restituirà il tipo conosciuto.|  
|tipo|Stringa che descrive il tipo conosciuto usato per la serializzazione e la deserializzazione.|  
  
## <a name="index-attribute"></a>Attributo index  
  
|Value|Descrizione|  
|-----------|-----------------|  
|"0"|Primo parametro del tipo generico. Ad esempio, un elenco <xref:System.Collections.Generic.List%601> presenta un solo parametro. Se tale parametro viene usato come tipo dichiarato, impostare l'attributo index su "0".|  
|"1"|Secondo parametro di un tipo generico. Ad esempio, un dizionario <xref:System.Collections.Generic.Dictionary%602> presenta due parametri. Se il tipo conosciuto viene restituito dal secondo parametro, impostare l'attributo index su "1".|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<knownType>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Specifica un tipo conosciuto restituibile da un campo o da una proprietà del tipo dichiarato.|  
  
## <a name="remarks"></a>Note  
 Per altre informazioni sui tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Vedere le [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) per un esempio di utilizzo di questo elemento.  
  
 Questo elemento di configurazione non può avere contemporaneamente entrambi gli attributi. Se si impostano entrambi gli attributi, si verifica un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Tipi conosciuti di contratto dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)

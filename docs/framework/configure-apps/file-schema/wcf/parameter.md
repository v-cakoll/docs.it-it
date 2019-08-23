---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: c3f2179835ad1232e115cad0decdd3d41bbdc160
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932840"
---
# <a name="parameter"></a>\<> parametro
Specifica il parametro generico quando un tipo dichiarato è un tipo generico.  
  
 \<system.runtime.serialization>  
\<dataContractSerializer>  
\<Elemento > declaredTypes  
\<aggiungere > elemento per \<declaredTypes >  
\<Elemento > knownType  
\<Parameter > elemento  
  
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
|index|Quando il tipo dichiarato è un tipo generico, specifica il parametro generico che restituirà il tipo conosciuto.|  
|type|Stringa che descrive il tipo conosciuto usato per la serializzazione e la deserializzazione.|  
  
## <a name="index-attribute"></a>Attributo index  
  
|Value|DESCRIZIONE|  
|-----------|-----------------|  
|"0"|Primo parametro del tipo generico. Ad esempio, un elenco <xref:System.Collections.Generic.List%601> presenta un solo parametro. Se tale parametro viene usato come tipo dichiarato, impostare l'attributo index su "0".|  
|"1"|Secondo parametro di un tipo generico. Ad esempio, un dizionario <xref:System.Collections.Generic.Dictionary%602> presenta due parametri. Se il tipo conosciuto viene restituito dal secondo parametro, impostare l'attributo index su "1".|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|Specifica un tipo conosciuto restituibile da un campo o da una proprietà del tipo dichiarato.|  
  
## <a name="remarks"></a>Note  
 Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Per un esempio di utilizzo di questo elemento, vedere la [ \<> DataContractSerializer](datacontractserializer-element.md) .  
  
 Questo elemento di configurazione non può avere contemporaneamente entrambi gli attributi. Se si impostano entrambi gli attributi, si verifica un'eccezione <xref:System.Configuration.ConfigurationErrorsException>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Tipi noti di contratto di dati](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)

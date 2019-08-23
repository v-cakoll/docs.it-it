---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: a0794314cfcb87df00d66b6832356fb130787eba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928860"
---
# <a name="knowntype"></a>\<knownType>
Specifica un tipo da usare dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione. L'elemento specifica un "tipo conosciuto" restituito da un campo o da una proprietà di un "tipo dichiarato". Per ulteriori informazioni, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).  
  
 \<system.runtime.serialization>  
\<dataContractSerializer>  
\<Elemento > declaredTypes  
\<aggiungere > di \<declaredTypes >  
\<Elemento > knownType  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a>Type  
 `string`  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|type|Specifica il tipo (compreso lo spazio dei nomi), il nome dell'assembly, la versione, impostazioni cultura e token di chiave pubblica.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<> parametro](parameter.md)|Specifica un indice di parametro quando il tipo dichiarato è un tipo generico.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|Aggiunge un tipo dichiarato alla raccolta dei tipi dichiarati.|  
  
## <a name="remarks"></a>Note  
 Per ulteriori informazioni sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md) e <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Per un esempio di utilizzo di questo elemento, vedere la [ \<> DataContractSerializer](datacontractserializer-element.md) .  
  
## <a name="example"></a>Esempio  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Tipi noti di contratto di dati](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)

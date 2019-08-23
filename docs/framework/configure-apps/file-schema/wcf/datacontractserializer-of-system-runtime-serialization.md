---
title: <dataContractSerializer>di < System. Runtime. Serialization >
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: 380d9ba5b8407d78b5045fd34fcdf37c0818d6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919343"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a>\<> DataContractSerializer di \<System. Runtime. Serialization >
Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<system.runtime.serialization>  
\<dataContractSerializer>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|IgnoreExtensionDataObject|Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati. Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.|  
|maxItemsInObjectGraph|Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare. Questo attributo è pari a 65.536.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|Contiene i tipi noti usati dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.<br /><br /> Per ulteriori informazioni sui contratti dati e sui tipi noti, vedere [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Note  
 Per ulteriori informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer> e [tipi noti del contratto dati](../../../wcf/feature-details/data-contract-known-types.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [Tipi noti di contratto di dati](../../../wcf/feature-details/data-contract-known-types.md)

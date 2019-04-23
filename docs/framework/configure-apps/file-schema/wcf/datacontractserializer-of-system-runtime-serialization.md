---
title: <dataContractSerializer> of <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: c81fdb040f2e0d6c9a3728d8ed3b917443ecb42e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115362"
---
# <a name="datacontractserializer-of-systemruntimeserialization"></a>\<dataContractSerializer> of \<system.runtime.serialization>
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
|[\<declaredTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Contiene i tipi noti usati dal serializzatore <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserializzazione.<br /><br /> Per altre informazioni sui contratti dati e i tipi noti, vedere [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Note  
 Per altre informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer> e [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- [Tipi noti di contratto di dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)

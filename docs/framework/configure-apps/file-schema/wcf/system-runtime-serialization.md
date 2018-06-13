---
title: '&lt;Serialization&gt;'
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: 6ffd4057028adcd123086173a05164eb5d2622f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748500"
---
# <a name="ltsystemruntimeserializationgt"></a>&lt;Serialization&gt;
Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 system.runtime.serialization  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer">  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
             <parameter index="Integer"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti attributi, elementi figlio ed elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|Consente l'aggiunta di tipi noti da usare durante la deserializzazione.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[Elemento \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Elemento di livello superiore della configurazione.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Runtime.Serialization>  
 [Uso di contratti di dati](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [Tipi noti di contratto di dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)

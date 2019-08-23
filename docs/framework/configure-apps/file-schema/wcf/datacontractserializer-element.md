---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 7e440810fee1dddb7025d1385b1edb4838d98a39
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925917"
---
# <a name="datacontractserializer"></a>\<dataContractSerializer>
Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>. Questo elemento è presente in due gerarchie diverse e viene elencato sia nella sezione Gerarchia dello schema seguente sia nella sezione Osservazioni.  
  
 \<system.ServiceModel>  
\<comportamenti >  
\<serviceBehaviors>  
\<comportamento >  
\<dataContractSerializer>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|IgnoreExtensionDataObject|Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando vengono serializzati o deserializzati. Questo attributo è impostabile solo nell'elemento `<dataContractSerializer>` del serializzatore `<behavior>`.|  
|maxItemsInObjectGraph|Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare. Questo attributo è pari a 65.536.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|Raccolta di impostazioni per il comportamento di un servizio.|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|Rappresenta l'elemento radice della sezione dello spazio dei nomi <xref:System.Runtime.Serialization> e contiene elementi per l'impostazione delle opzioni del serializzatore <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Note  
 Come indicato nell'introduzione di questo argomento, questa è la seconda gerarchia in cui si verifica \<l'elemento X509Extension >.  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 Per altre informazioni sui tipi noti, vedere <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [Tipi noti di contratto di dati](../../../wcf/feature-details/data-contract-known-types.md)
- [Trasferimento e serializzazione dei dati](../../../wcf/feature-details/data-transfer-and-serialization.md)

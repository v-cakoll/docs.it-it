---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 933d49092c392fa293468d546e521bf7ed858376
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539844"
---
# <a name="datacontractserializer"></a>dataContractSerializer
Contiene dati di configurazione per <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<dataContractSerializer>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|IgnoreExtensionDataObject|Valore booleano che specifica se ignorare i dati forniti dall'endpoint quando serializzato o deserializzato.|  
|maxItemsInObjectGraph|Numero intero che specifica il numero massimo di elementi da serializzare o deserializzare.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Specifica un comportamento dell'endpoint.|  
  
## <a name="remarks"></a>Note  
 Per altre informazioni sui tipi noti, vedere la documentazione di <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
> [!CAUTION]
>  L'elemento di comportamento `<dataContractSerializer>` (se presente) deve sempre essere visualizzato prima dell'elemento di comportamento `<enableWebScript>` nel file di configurazione. In caso contrario, il comportamento risultante è indefinito.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [Tipi noti di contratto di dati](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [Trasferimento e serializzazione dei dati](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)

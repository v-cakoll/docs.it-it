---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: b6914a195ba0e1934f7a586f5f6bae703a4bb1f9
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675322"
---
# <a name="binarymessageencoding"></a>\<binaryMessageEncoding>
Definisce un codificatore di messaggi binario che codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario.  
  
 \<system.serviceModel>  
\<le associazioni >  
\<customBinding>  
\<binding>  
\<binaryMessageEncoding>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|maxReadPoolSize|Numero intero che definisce il numero di messaggi che possono essere letti contemporaneamente senza allocare nuovi lettori. Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore. Il valore predefinito è 64.|  
|maxSessionSize|Numero intero positivo che imposta la dimensione, in byte, del buffer usato per la codifica. Un buffer più grande aumenta la velocità di codifica a spese della dimensione del working set. Il valore predefinito è 2048.|  
|maxWritePoolSize|Numero intero che definisce il numero di messaggi che possono essere inviati contemporaneamente senza allocare nuovi writer. Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore. Il valore predefinito è 16.|  
|messageVersion|Specifica le versioni del messaggio SOAP e WS-Addressing usate o previste.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
 La codifica è il processo di trasformazione di un messaggio in una sequenza di byte. La decodifica è il processo inverso. Windows Communication Foundation (WCF) include tre tipi di codifica per i messaggi SOAP: Testo, binaria e MTOM (MTOM).  
  
 L'elemento `binaryMessageEncoding` specifica il formato binario .NET per XML e dispone delle opzioni che consentono di specificare la codifica dei caratteri e le versioni SOAP e WS-Addressing da usare. Il codificatore di messaggi binario codifica messaggi di Windows Communication Foundation (WCF) in transito in formato binario. Se da un lato questa codifica comporta una trasmissione molto veloce dei messaggi, dall'altro si perde l'interoperabilità basata sugli standard WS - *.  
  
## <a name="example"></a>Esempio  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [Codifica dei messaggi](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [Scelta di un codificatore di messaggi](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

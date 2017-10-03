---
title: '&lt;webMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
caps.latest.revision: 7
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 06920c0ebce33d7e55bc56ddb29843bba43de7a2
ms.contentlocale: it-it
ms.lasthandoff: 09/25/2017

---
# <a name="ltwebmessageencodinggt"></a>&lt;webMessageEncoding&gt;
Consente alle codifiche di messaggi XML di testo normale e JSON (JavaScript Object Notation) e al contenuto binario "non elaborato" di essere letti e scritti quando vengono usati in un'associazione [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
 \<System. ServiceModel >  
\<associazioni >  
\<customBinding >  
\<associazione >  
\<webMessageEncoding >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`maxReadPoolSize`|Numero di messaggi che è possibile leggere contemporaneamente senza allocare nuovi lettori. Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore. L'impostazione predefinita è 64 lettori per ogni codificatore interno (testo, JSON e "non elaborato").<br /><br /> Sebbene l'aumento di questo numero determini un maggiore consumo di memoria, in questo modo il codificatore sarà in grado di gestire picchi improvvisi di messaggi in arrivo usando i lettori del pool già creati anziché crearne di nuovi.|  
|`maxWritePoolSize`|Numero di messaggi che è possibile inviare contemporaneamente senza allocare nuovi writer. Dimensioni maggiori del pool rendono il sistema più tollerante ai picchi di attività al costo di un working set superiore. L'impostazione predefinita è 16 writer per ogni codificatore interno (testo, JSON e "non elaborato").<br /><br /> Sebbene l'aumento di questo numero determini un maggiore consumo di memoria, in questo modo il codificatore sarà in grado di gestire picchi improvvisi di messaggi in uscita usando i writer del pool già creati anziché crearne di nuovi.|  
|`writeEncoding`|Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione. I valori validi sono:<br /><br /> -UnicodeFffeTextEncoding: Codifica Unicode Big Endian.<br />-Utf16TextEncoding: Codifica Unicode.<br />-Utf8TextEncoding: codifica a 8 bit.<br /><br /> L'impostazione predefinita è Utf8TextEncoding. L'attributo è di tipo <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<associazione >](../../../../../docs/framework/misc/binding.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Note  
 La codifica è il processo di trasformazione di un messaggio in una sequenza di byte. La decodifica è il processo inverso. Questi processi richiedono la specifica di una codifica caratteri.  
  
 L'elemento `webMessageEncoding` delega a una serie di codificatori interni la gestione di codifiche XML di testo normale e JSON e dati binari non elaborati. Questa delega viene eseguita mediante un codificatore di messaggi composto.  
  
 Questo elemento di associazione e il relativo codificatore composto vengono usati per controllare la codifica in scenari che non usano la messaggistica SOAP usata dall'elemento `webHttpBinding`. Questi scenari includono POX (Plain Old XML), REST (Representational State Transfer), RSS (Really Simple Syndication ) e AJAX (Atom syndication and Asynchronous JavaScript and XML). Il codificatore di messaggi composto non supporta SOAP o WS-Addressing.  
  
 L'elemento di associazione può essere configurato con una codifica dei caratteri di scrittura mediante l'attributo `writeEncoding`. Il valore <xref:System.Text.Encoding> fornito specifica il comportamento in scrittura per le codifiche JSON e XML di testo. In lettura viene interpretata qualsiasi codifica di messaggi e codifica di testo valida.  
  
 Le proprietà `maxReadPoolSize` e `maxWritePoolSize` possono inoltre essere usate per impostare rispettivamente il numero massimo di lettori e il numero massimo di writer da allocare. Per impostazione predefinita vengono allocati 64 lettori e 16 writer.  
  
 Vincoli di complessità predefiniti vengono inoltre impostati utilizzando il [ \<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) elemento per la protezione da una classe di tipo denial of service (DOS) attacchi che tentano di utilizzare la complessità dei messaggi per bloccare l'elaborazione di endpoint risorse.  
  
## <a name="example"></a>Esempio  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>   
 [Codifica dei messaggi](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [Scelta di un codificatore di messaggi](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [Associazioni](../../../../../docs/framework/wcf/bindings.md)   
 [Estensione delle associazioni](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Associazioni personalizzate](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)


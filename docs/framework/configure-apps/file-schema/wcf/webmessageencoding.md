---
title: <webMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
ms.openlocfilehash: 4aa87acaf9080959ba8b53e3ec3216314dc745b6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732576"
---
# \<webMessageEncoding>
Consente alle codifiche di messaggi XML di testo normale e JSON (JavaScript Object Notation) e al contenuto binario "non elaborato" di essere letti e scritti quando vengono usati in un'associazione Windows Communication Foundation (WCF).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webMessageEncoding>**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<webMessageEncoding maxReadPoolSize="Integer"
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
|`writeEncoding`|Specifica la codifica del set di caratteri da usare per l'emissione dei messaggi dell'associazione. I valori validi sono:<br /><br /> -UnicodeFffeTextEncoding: codifica Unicode big endian.<br />-Utf16TextEncoding: codifica Unicode.<br />-Utf8TextEncoding: codifica a 8 bit.<br /><br /> L'impostazione predefinita è Utf8TextEncoding. L'attributo è di tipo <xref:System.Text.Encoding>.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definisce i vincoli sulla complessità dei messaggi SOAP che possono essere elaborati dagli endpoint configurati con questa associazione. L'elemento è di tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Definisce tutte le funzionalità di associazione dell'associazione personalizzata.|  
  
## <a name="remarks"></a>Commenti  
 La codifica è il processo di trasformazione di un messaggio in una sequenza di byte. La decodifica è il processo inverso. Questi processi richiedono la specifica di una codifica caratteri.  
  
 L'elemento `webMessageEncoding` delega a una serie di codificatori interni la gestione di codifiche XML di testo normale e JSON e dati binari non elaborati. Questa delega viene eseguita mediante un codificatore di messaggi composto.  
  
 Questo elemento di associazione e il relativo codificatore composto vengono usati per controllare la codifica in scenari che non usano la messaggistica SOAP usata dall'elemento `webHttpBinding`. Questi scenari includono POX (Plain Old XML), REST (Representational State Transfer), RSS (Really Simple Syndication ) e AJAX (Atom syndication and Asynchronous JavaScript and XML). Il codificatore di messaggi composto non supporta SOAP o WS-Addressing.  
  
 L'elemento di associazione può essere configurato con una codifica dei caratteri di scrittura mediante l'attributo `writeEncoding`. Il valore <xref:System.Text.Encoding> fornito specifica il comportamento in scrittura per le codifiche JSON e XML di testo. In lettura viene interpretata qualsiasi codifica di messaggi e codifica di testo valida.  
  
 Le proprietà `maxReadPoolSize` e `maxWritePoolSize` possono inoltre essere usate per impostare rispettivamente il numero massimo di lettori e il numero massimo di writer da allocare. Per impostazione predefinita vengono allocati 64 lettori e 16 writer.  
  
 I vincoli di complessità predefiniti vengono inoltre impostati utilizzando l' [\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100)) elemento per proteggersi da una classe di attacchi Denial of Service (DOS) che tentano di utilizzare la complessità dei messaggi per bloccare le risorse di elaborazione dell'endpoint.  
  
## <a name="example"></a>Esempio  
  
```xml  
<webMessageEncoding maxReadPoolSize="256"
                    maxWritePoolSize="128"
                    messageVersion="None"
                    textEncoding="utf-8" />
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [Codifica dei messaggi](message-encoding.md)
- [Scelta di un codificatore di messaggi](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [Binding](../../../wcf/bindings.md)
- [Estensione delle associazioni](../../../wcf/extending/extending-bindings.md)
- [Associazioni personalizzate](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)

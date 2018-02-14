---
title: Opzioni di output nella classe XslCompiledTransform
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91ce8cba-386c-411e-bb38-0891a0393c0a
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 84171c92a56a9970b5ffc16ce8f30c85d61cc678
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="output-options-on-the-xslcompiledtransform-class"></a>Opzioni di output nella classe XslCompiledTransform
In questo argomento vengono illustrate le opzioni disponibili per l'output di XSLT. È possibile specificare le opzioni di output nel foglio di stile oppure nel metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## <a name="xsloutput-element"></a>Elemento xsl:output  
 L'elemento `xsl:output` consente di specificare le opzioni per l'output. Il tipo di output specificato dal metodo <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> determina il comportamento delle opzioni `xsl:output`.  
  
 Nella tabella seguente viene descritto il comportamento di ciascun attributo disponibile nell'elemento `xsl:output` se il tipo di output è un flusso o un oggetto <xref:System.IO.TextWriter>.  
  
|Nome attributo|Comportamento|  
|--------------------|--------------|  
|metodo|Supportato.|  
|version|Ignorato. La versione è sempre 1.0 per XML e 4.0 per HTML.|  
|encoding|Ignorato se si invia l'output a un tipo <xref:System.IO.TextWriter>. Viene invece usata la proprietà <xref:System.IO.TextWriter.Encoding%2A?displayProperty=nameWithType>.|  
|omit-xml-declaration|Supportato.|  
|autonomi|Supportato.|  
|doctype-public|Supportato.|  
|doctype-system|Supportato.|  
|cdata-section-elements|Supportato.|  
|indent|Supportato.|  
|media-type|Supportato.|  
  
#### <a name="sending-output-to-an-xmlwriter"></a>Invio dell'output a XmlWriter  
 Se nel foglio di stile viene usato l'elemento `xsl:output` e il tipo di output è un oggetto <xref:System.Xml.XmlWriter>, quando si crea tale <xref:System.Xml.XmlWriter> oggetto è necessario usare la proprietà <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType>. La proprietà <xref:System.Xml.Xsl.XslCompiledTransform.OutputSettings%2A?displayProperty=nameWithType> restituisce un oggetto <xref:System.Xml.XmlWriterSettings> contenente informazioni derivate dall'elemento `xsl:output` di un foglio di stile compilato. Questo oggetto <xref:System.Xml.XmlWriterSettings> può essere passato al metodo <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> per creare un oggetto <xref:System.Xml.XmlWriter> con le impostazioni corrette.  
  
## <a name="output-types"></a>Tipi di output  
 Nell'elenco seguente vengono descritti i tipi di output disponibili nel comando <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
#### <a name="xmlwriter"></a>XmlWriter  
 La classe <xref:System.Xml.XmlWriter> consente di scrivere flussi o file XML. È possibile specificare le funzionalità da supportare nell'oggetto <xref:System.Xml.XmlWriter>, incluse le opzioni di output, tramite la classe <xref:System.Xml.XmlWriterSettings> class. La classe <xref:System.Xml.XmlWriter> rappresenta una parte integrante del framework <xref:System.Xml>. Usare questo tipo di output per eseguire la pipeline dei risultati di output in un altro processo XML.  
  
#### <a name="string"></a>Stringa  
 Usare questo tipo di output per specificare l'URI del file di output.  
  
#### <a name="stream"></a>Flusso  
 Un flusso è un'astrazione di una sequenza di byte, ad esempio un file, un dispositivo di input/output, una pipe di comunicazione tra processi o un socket TCP/IP. La classe <xref:System.IO.Stream> e le relative classi derivate forniscono una rappresentazione generica di questi diversi tipi di input e output, senza che il programmatore venga a contatto con i dettagli specifici del sistema operativo e con i dispositivi sottostanti.  
  
 Usare questo tipo di output per inviare dati a un tipo <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream> oppure per inviare un flusso di output (`Response.OutputStream`).  
  
#### <a name="textwriter"></a>TextWriter  
 Il tipo <xref:System.IO.TextWriter> consente di scrivere caratteri sequenziali. È implementato nelle classi <xref:System.IO.StringWriter> e <xref:System.IO.StreamWriter>, che consentono di scrivere rispettivamente stringhe o flussi. Usare questo tipo di output per inviare l'output a una stringa.  
  
## <a name="notes"></a>Note  
  
-   Quando si scrivono tag vuoti, viene scritto uno spazio tra l'ultimo carattere del nome dell'elemento e la barra rovesciata, ad esempio `<myElement />`. Questo consente ai browser meno recenti di visualizzare correttamente le pagine HTML generate.  
  
## <a name="see-also"></a>Vedere anche  
 [Trasformazioni XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)

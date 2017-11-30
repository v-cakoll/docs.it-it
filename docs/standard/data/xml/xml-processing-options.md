---
title: Opzioni di elaborazione XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 18f8f9c76a1842517340eaa3f74b4778f869403e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-options"></a>Opzioni di elaborazione XML
Per un elenco di tecnologie Microsoft usabili per l'elaborazione dei dati XML, vedere le tabelle riportate di seguito.  
  
## <a name="net-framework-options"></a>Opzioni di .NET Framework  
  
|**Opzione**|**Tipo di elaborazione**|**Descrizione**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) <br />(spazio dei nomi <xref:System.Xml.Linq>)|In memoria|-Basati sulla tecnologia di Integrated Query (LINQ).<br />-Offre l'esperienza di query è simile a SQL per gli oggetti, dati relazionali e dati XML.<br />-Fornisce intuitive per la funzionalità di creazione e la trasformazione di documenti.<br />-Utilizzare questa opzione se si scrive nuovo codice.|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|Basata sul flusso|: Fornisce un modo veloce, non in cache, di tipo forward-only per accedere ai dati XML.<br />-È possibile creare oggetti usando il <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> (metodo), nonché specificare il set di funzionalità da abilitare nell'oggetto tramite la <xref:System.Xml.XmlReaderSettings> classe.|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|Basata sul flusso|: Fornisce un modo veloce, non in cache, di tipo forward-only per generare i dati XML.<br />-È possibile creare oggetti usando il <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType> (metodo), nonché specificare il set di funzionalità da abilitare nell'oggetto tramite la <xref:System.Xml.XmlWriterSettings> classe.|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|In memoria|-Implementa il [W3C DOM Document Object Model () Level 1 Core](http://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) e [DOM Level 2 Core](http://www.w3.org/TR/DOM-Level-2-Core/) indicazioni.<br />-È possibile creare, inserire, rimuovere e modificare nodi usando metodi e proprietà basati sul modello DOM noto.<br />-Utilizzare questa opzione se si modifica il codice esistente che utilizza il DOM W3C.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|In memoria|-Offre diverse opzioni di modifica e funzionalità di navigazione usando un modello di cursore.<br />Documenti XML possono essere contenuti in un <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> oggetto.<br />-Fornisce prestazioni eccellenti per l'elaborazione di sola lettura di XML.<br />-Utilizzare questa opzione se si modifica il codice esistente con query XPath o trasformazioni XSLT.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|In memoria|-Fornisce opzioni per la trasformazione di dati XML tramite trasformazioni XSL.<br />-La [compilatore XSLT (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md) consente di cui si fa riferimento è precompilato trasformazioni nell'app.|  
  
## <a name="win32-and-com-based-options"></a>Opzioni basate su Win32 e COM  
  
|**Opzione**|**Descrizione**|  
|----------------|---------------------|  
|[XmlLite](http://go.microsoft.com/fwlink/?LinkId=93723)|-Un veloce, protetta, non-memorizzazione nella cache, il parser XML forward-only che consente di compilare ad alte prestazioni XML app.<br />-Funziona con qualsiasi linguaggio che è possibile utilizzare librerie a collegamento dinamico (DLL); è consigliabile usare C++.|  
|[MSXML](http://go.microsoft.com/fwlink/?LinkId=93722)|-Tecnologia basato su COM per l'elaborazione di XML che è incluso con il sistema operativo Windows.<br />-Fornisce un'implementazione nativa di DOM con supporto per XPath e XSLT.<br />-Contiene parser SAX2 basato su eventi.|  
  
## <a name="see-also"></a>Vedere anche  
 [Elaborazione di dati XML con il modello DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 [Elaborazione di dati XML con il modello di dati XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [Compilatore XSLT (xsltc.exe)](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)

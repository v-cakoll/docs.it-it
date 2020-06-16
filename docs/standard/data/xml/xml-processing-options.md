---
title: Opzioni di elaborazione XML
description: Esaminare le opzioni per l'elaborazione XML, tra cui LINQ to XML, XmlReader, XmlWriter, XmlDocument, XPathNavigator, XslCompiledTransform, XmlLite e MSXML.
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 33ced8ee-1745-4e71-8dee-ebe70ec067c7
ms.openlocfilehash: c41b3dd99264b9043c5914b84bbb76ac02b317ac
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767767"
---
# <a name="xml-processing-options"></a>Opzioni di elaborazione XML
Per un elenco di tecnologie Microsoft usabili per l'elaborazione dei dati XML, vedere le tabelle riportate di seguito.  
  
## <a name="net-framework-options"></a>Opzioni di .NET Framework  
  
|**Opzione**|**Tipo di elaborazione**|**Descrizione**|  
|----------------|-------------------------|---------------------|  
|[LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) <br/> [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) <br />(spazio dei nomi <xref:System.Xml.Linq>)|In memoria|- Basata sulla tecnologia LINQ (Language Integrated Query) di .NET Framework.<br />- Garantisce un utilizzo delle query simile a SQL per oggetti, dati relazionali e dati XML.<br />- Fornisce funzionalità intuitive per la creazione e la trasformazione di documenti.<br />- Usare questa opzione se si scrive del nuovo codice.|  
|<xref:System.Xml.XmlReader?displayProperty=nameWithType>|Basata sul flusso|- Fornisce un accesso rapido, non memorizzato nella cache, di tipo forward-only ai dati XML.<br />- È possibile creare oggetti usando il metodo <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType>, nonché specificare il set di funzionalità da abilitare nell'oggetto tramite la classe <xref:System.Xml.XmlReaderSettings>.|  
|<xref:System.Xml.XmlWriter?displayProperty=nameWithType>|Basata sul flusso|- Fornisce una generazione rapida, non memorizzata nella cache, di tipo forward-only dei dati XML.<br />- È possibile creare oggetti usando il metodo <xref:System.Xml.XmlWriter.Create%2A?displayProperty=nameWithType>, nonché specificare il set di funzionalità da abilitare nell'oggetto tramite la classe <xref:System.Xml.XmlWriterSettings>.|  
|<xref:System.Xml.XmlDocument?displayProperty=nameWithType>|In memoria|- Implementa le raccomandazioni [W3C Document Object Model (DOM) Level 1 Core](https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html) e [DOM Level 2 Core](https://www.w3.org/TR/DOM-Level-2-Core/).<br />- È possibile creare, inserire, rimuovere e modificare nodi usando metodi e proprietà basati sul modello DOM noto.<br />- Usare questa opzione se si modifica il codice esistente tramite cui viene usato DOM di W3C.|  
|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|In memoria|- Offre diverse opzioni di modifica e funzionalità di navigazione usando un modello di cursore.<br />- I documenti XML possono essere contenuti in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument>.<br />- Fornisce prestazioni eccellenti per l'elaborazione di sola lettura di XML.<br />- Usare questa opzione se si modifica il codice esistente con query XPath o trasformazioni XSLT.|  
|<xref:System.Xml.Xsl.XslCompiledTransform>|In memoria|- Fornisce opzioni per la trasformazione di dati XML tramite trasformazioni XSL.<br />- Tramite il [compilatore XSLT (xsltc.exe)](xslt-compiler-xsltc-exe.md) è possibile fare riferimento a trasformazioni precompilate nell'applicazione in uso.|  
  
## <a name="win32-and-com-based-options"></a>Opzioni basate su Win32 e COM  
  
|**Opzione**|**Descrizione**|  
|----------------|---------------------|  
|[XmlLite](https://docs.microsoft.com/previous-versions/windows/desktop/ms752872(v=vs.85))|- Parser XML rapido, sicuro, che non supporta la memorizzazione nella cache, di tipo forward-only con cui è possibile compilare applicazioni XML a elevate prestazioni.<br />- È compatibile con qualsiasi linguaggio che usa DLL. Se ne consiglia l'uso con C++.|  
|[MSXML](https://docs.microsoft.com/previous-versions/windows/desktop/ms763742(v=vs.85))|- Tecnologia basata su COM per l'elaborazione di codice XML inclusa nel sistema operativo Windows.<br />- Fornisce un'implementazione nativa di DOM con supporto per XPath e XSLT.<br />- Contiene il parser SAX2 basato su eventi.|  
  
## <a name="see-also"></a>Vedere anche

- [Elaborazione di dati XML con il modello DOM](process-xml-data-using-the-dom-model.md)
- [Elaborazione di dati XML con il modello di dati XPath](process-xml-data-using-the-xpath-data-model.md)
- [Compilatore XSLT (xsltc.exe)](xslt-compiler-xsltc-exe.md)

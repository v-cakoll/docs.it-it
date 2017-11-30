---
title: Elaborazione di dati XML in memoria
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec4ccbff095071b279e07cee6a1aab3ca830423f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="processing-xml-data-in-memory"></a>Elaborazione di dati XML in memoria
Microsoft .NET Framework include tre modelli per l'elaborazione dati XML: il <xref:System.Xml.XmlDocument> (classe), il <xref:System.Xml.XPath.XPathDocument> (classe), e [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).  
  
 La classe <xref:System.Xml.XmlDocument> consente l'implementazione delle raccomandazioni di base di livello 1 e 2 del modello DOM W3C. Il modello DOM è una rappresentazione in memoria (cache) dell'albero di un documento XML. Usando la classe <xref:System.Xml.XmlDocument> e le classi correlate è possibile costruire documenti XML, caricare e accedere ai dati, modificare i dati e salvare le modifiche.  
  
 La classe <xref:System.Xml.XPath.XPathDocument> è un archivio dati in memoria, di sola lettura, basato sul modello dati XPath. La classe <xref:System.Xml.XPath.XPathNavigator> offre diverse opzioni di modifica e funzionalità di navigazione usando un modello di cursore sui documenti XML contenuti nella classe <xref:System.Xml.XPath.XPathDocument> di sola lettura, nonché nella classe <xref:System.Xml.XmlDocument>.  
  
 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) è il nuovo modello di .NET Framework versione 3.5 per l'elaborazione dati XML. Si tratta di un modello in memoria che sfrutta [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d). LINQ estende la sintassi dei linguaggi C# e Visual Basic offrendo nuove funzionalità di query.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Elaborazione di dati XML con il modello DOM](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 Viene illustrato l'uso della classe <xref:System.Xml.XmlDocument> e delle classi correlate per l'elaborazione dei dati XML.  
  
 [Elaborazione di dati XML con il modello di dati XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 Viene illustrato l'uso delle classi <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> e <xref:System.Xml.XPath.XPathNavigator> e delle classi correlate per l'elaborazione dei dati XML.  
  
 [Elaborazione di dati XML utilizzando LINQ to XML](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 Viene fornita una breve panoramica di LINQ to XML e sono elencati i collegamenti alla relativa documentazione.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Documenti e dati XML](../../../../docs/standard/data/xml/index.md)

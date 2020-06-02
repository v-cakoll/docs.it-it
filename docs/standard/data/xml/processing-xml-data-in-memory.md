---
title: Elaborazione di dati XML in memoria
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
ms.openlocfilehash: 06863d162a9f9fbf67f41cb12ea4fbb1935b424d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291279"
---
# <a name="processing-xml-data-in-memory"></a>Elaborazione di dati XML in memoria
Microsoft .NET Framework include tre modelli per l'elaborazione dei dati XML: la classe <xref:System.Xml.XmlDocument>, la classe <xref:System.Xml.XPath.XPathDocument>, nonché [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) e [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
 La classe <xref:System.Xml.XmlDocument> consente l'implementazione delle raccomandazioni di base di livello 1 e 2 del modello DOM W3C. Il modello DOM è una rappresentazione in memoria (cache) dell'albero di un documento XML. Usando la classe <xref:System.Xml.XmlDocument> e le classi correlate è possibile costruire documenti XML, caricare e accedere ai dati, modificare i dati e salvare le modifiche.  
  
 La classe <xref:System.Xml.XPath.XPathDocument> è un archivio dati in memoria, di sola lettura, basato sul modello dati XPath. La classe <xref:System.Xml.XPath.XPathNavigator> offre diverse opzioni di modifica e funzionalità di navigazione usando un modello di cursore sui documenti XML contenuti nella classe <xref:System.Xml.XPath.XPathDocument> di sola lettura, nonché nella classe <xref:System.Xml.XmlDocument>.  
  
 [LINQ to XML](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) è un modello di elaborazione dei dati XML introdotto in .NET Framework versione 3.5. Si tratta di un modello in memoria che usa [LINQ (Language-Integrated Query)](../../../csharp/programming-guide/concepts/linq/index.md). LINQ estende la sintassi dei linguaggi C# e Visual Basic offrendo nuove funzionalità di query.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Elaborazione di dati XML con il modello DOM](process-xml-data-using-the-dom-model.md)  
 Viene illustrato l'uso della classe <xref:System.Xml.XmlDocument> e delle classi correlate per l'elaborazione dei dati XML.  
  
 [Elaborazione di dati XML con il modello di dati XPath](process-xml-data-using-the-xpath-data-model.md)  
 Viene illustrato l'uso delle classi <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> e <xref:System.Xml.XPath.XPathNavigator> e delle classi correlate per l'elaborazione dei dati XML.  
  
 [Elaborazione di dati XML utilizzando LINQ to XML](process-xml-data-using-linq-to-xml.md)  
 Viene fornita una breve panoramica di LINQ to XML e sono elencati i collegamenti alla relativa documentazione.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Documenti e dati XML](index.md)

---
title: Input di XPathDocument in XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: beefaffa0365efbb808fd15c1253027e4d5b09a1
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170910"
---
# <a name="xpathdocument-input-to-xsltransform"></a>Input di XPathDocument in XslTransform
Il tipo <xref:System.Xml.XPath.XPathDocument> è una cache di sola lettura per l'elaborazione di documenti con <xref:System.Xml.Xsl.XslTransform>. È strutturalmente simile al DOM XML, ma è altamente ottimizzata per l'elaborazione di trasformazioni XSLT (Extensible Stylesheet Language for Transformation) e del modello di dati XPath (XML Path Language) tramite le funzioni di ottimizzazione di XPath nel tipo <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
>  La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0. È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>. Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Nell'esempio di codice seguente viene creato un tipo <xref:System.Xml.XPath.XPathDocument> come input per una trasformazione.  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a>Vedere anche

- [Implementazione del processore XSLT da parte della classe XslTransform](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)

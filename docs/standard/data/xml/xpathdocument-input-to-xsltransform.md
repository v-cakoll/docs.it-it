---
title: Input di XPathDocument in XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
ms.openlocfilehash: 66cdbae8b52ca1b7ed46e8f040fcbf51c969dea2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84282974"
---
# <a name="xpathdocument-input-to-xsltransform"></a>Input di XPathDocument in XslTransform
Il tipo <xref:System.Xml.XPath.XPathDocument> è una cache di sola lettura per l'elaborazione di documenti con <xref:System.Xml.Xsl.XslTransform>. È strutturalmente simile al DOM XML, ma è altamente ottimizzata per l'elaborazione di trasformazioni XSLT (Extensible Stylesheet Language for Transformation) e del modello di dati XPath (XML Path Language) tramite le funzioni di ottimizzazione di XPath nel tipo <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
> La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0. È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>. Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](migrating-from-the-xsltransform-class.md).  
  
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

- [Implementazione del processore XSLT da parte della classe XslTransform](xsltransform-class-implements-the-xslt-processor.md)

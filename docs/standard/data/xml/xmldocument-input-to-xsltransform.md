---
title: Input di XmlDocument in XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
ms.openlocfilehash: c7819c3cb6b1430dcdb8a78c43f7138f64e691a8
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709842"
---
# <a name="xmldocument-input-to-xsltransform"></a><span data-ttu-id="ab897-102">Input di XmlDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="ab897-102">XmlDocument Input to XslTransform</span></span>
<span data-ttu-id="ab897-103">La classe <xref:System.Xml.XmlDocument> fornisce funzionalità di modifica per un documento XML.</span><span class="sxs-lookup"><span data-stu-id="ab897-103">The <xref:System.Xml.XmlDocument> class provides editing capabilities for an XML document.</span></span> <span data-ttu-id="ab897-104">Se è necessario modificare il codice XML prima di inviarlo al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>, caricare il codice XML in un <xref:System.Xml.XmlDocument>, modificarlo e inviarlo al <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="ab897-104">If the XML needs to be edited or modified before being sent to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, load the XML into an <xref:System.Xml.XmlDocument>, edit it, and send it in to the <xref:System.Xml.Xsl.XslTransform>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab897-105">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="ab897-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="ab897-106">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="ab897-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="ab897-107">Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="ab897-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="ab897-108"><xref:System.Xml.XmlDocument> implementa l'interfaccia <xref:System.Xml.XPath.IXPathNavigable>, quindi il documento può essere passato al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> dopo la modifica.</span><span class="sxs-lookup"><span data-stu-id="ab897-108">The <xref:System.Xml.XmlDocument> implements the <xref:System.Xml.XPath.IXPathNavigable> interface, so the document can be passed to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method after editing.</span></span>  
  
 <span data-ttu-id="ab897-109">Grazie alla funzionalità di modifica di <xref:System.Xml.XmlDocument>, usando la classe <xref:System.Xml.XmlDocument> come input per una trasformazione si ottengono prestazioni inferiori rispetto all'utilizzo di un <xref:System.Xml.XPath.XPathDocument> per le trasformazioni XSLT (Extensible Stylesheet Language for Transformations), in quanto <xref:System.Xml.XPath.XPathDocument> è ottimizzato per le query XPath (XML Path Language) per l'archiviazione interna.</span><span class="sxs-lookup"><span data-stu-id="ab897-109">Due to the editing capability of the <xref:System.Xml.XmlDocument>, using the <xref:System.Xml.XmlDocument> class as input to a transformation is slower than using an <xref:System.Xml.XPath.XPathDocument> for the Extensible Stylesheet Language for Transformations (XSLT) transformations, as the <xref:System.Xml.XPath.XPathDocument> is optimized for XML Path Language (XPath) queries due to the internal storage.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab897-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab897-110">Example</span></span>  
 <span data-ttu-id="ab897-111">Nell'esempio di codice seguente viene illustrato come fornire un <xref:System.Xml.XmlDocument> al metodo <xref:System.Xml.Xsl.XslTransform>, con l'output inviato a un <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ab897-111">The following code example shows how an <xref:System.Xml.XmlDocument> can be supplied to the <xref:System.Xml.Xsl.XslTransform>, with the output sent to an <xref:System.Xml.XmlReader>.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.Load("books.xml")  
Dim trans As XslTransform = new XslTransform()  
trans.Load("book.xsl")  
Dim rdr As XmlReader = trans.Transform(doc, Nothing, Nothing)  
while (rdr.Read())  
end while  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
XslTransform trans = new XslTransform();  
trans.Load("book.xsl");  
XmlReader rdr = trans.Transform(doc, null, null);  
while (rdr.Read()) {}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab897-112">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="ab897-112">See also</span></span>

- <xref:System.Xml.XmlDocument>
- [<span data-ttu-id="ab897-113">Trasformazioni XSLT con la classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="ab897-113">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="ab897-114">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="ab897-114">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="ab897-115">XPathNavigator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="ab897-115">XPathNavigator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)
- [<span data-ttu-id="ab897-116">XPathNodeIterator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="ab897-116">XPathNodeIterator in Transformations</span></span>](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="ab897-117">Input di XPathDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="ab897-117">XPathDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="ab897-118">Input di XmlDataDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="ab897-118">XmlDataDocument Input to XslTransform</span></span>](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)

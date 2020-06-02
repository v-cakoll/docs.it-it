---
title: Input di XmlDocument in XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
ms.openlocfilehash: e990c8ca3bb2a7145157fcedd06da4ea769c6ad3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290253"
---
# <a name="xmldocument-input-to-xsltransform"></a><span data-ttu-id="390a9-102">Input di XmlDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="390a9-102">XmlDocument Input to XslTransform</span></span>
<span data-ttu-id="390a9-103">La classe <xref:System.Xml.XmlDocument> fornisce funzionalità di modifica per un documento XML.</span><span class="sxs-lookup"><span data-stu-id="390a9-103">The <xref:System.Xml.XmlDocument> class provides editing capabilities for an XML document.</span></span> <span data-ttu-id="390a9-104">Se è necessario modificare il codice XML prima di inviarlo al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A>, caricare il codice XML in un <xref:System.Xml.XmlDocument>, modificarlo e inviarlo al <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="390a9-104">If the XML needs to be edited or modified before being sent to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, load the XML into an <xref:System.Xml.XmlDocument>, edit it, and send it in to the <xref:System.Xml.Xsl.XslTransform>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="390a9-105">La classe <xref:System.Xml.Xsl.XslTransform> è obsoleta in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="390a9-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="390a9-106">È possibile eseguire le trasformazioni XSLT (Extensible Stylesheet Language for Transformations) usando la classe <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="390a9-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="390a9-107">Per altre informazioni, vedere [Utilizzo della classe XslCompiledTransform](using-the-xslcompiledtransform-class.md) e [Migrazione dalla classe XslTransform](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="390a9-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="390a9-108"><xref:System.Xml.XmlDocument> implementa l'interfaccia <xref:System.Xml.XPath.IXPathNavigable>, quindi il documento può essere passato al metodo <xref:System.Xml.Xsl.XslTransform.Transform%2A> dopo la modifica.</span><span class="sxs-lookup"><span data-stu-id="390a9-108">The <xref:System.Xml.XmlDocument> implements the <xref:System.Xml.XPath.IXPathNavigable> interface, so the document can be passed to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method after editing.</span></span>  
  
 <span data-ttu-id="390a9-109">Grazie alla funzionalità di modifica di <xref:System.Xml.XmlDocument>, usando la classe <xref:System.Xml.XmlDocument> come input per una trasformazione si ottengono prestazioni inferiori rispetto all'utilizzo di un <xref:System.Xml.XPath.XPathDocument> per le trasformazioni XSLT (Extensible Stylesheet Language for Transformations), in quanto <xref:System.Xml.XPath.XPathDocument> è ottimizzato per le query XPath (XML Path Language) per l'archiviazione interna.</span><span class="sxs-lookup"><span data-stu-id="390a9-109">Due to the editing capability of the <xref:System.Xml.XmlDocument>, using the <xref:System.Xml.XmlDocument> class as input to a transformation is slower than using an <xref:System.Xml.XPath.XPathDocument> for the Extensible Stylesheet Language for Transformations (XSLT) transformations, as the <xref:System.Xml.XPath.XPathDocument> is optimized for XML Path Language (XPath) queries due to the internal storage.</span></span>  
  
## <a name="example"></a><span data-ttu-id="390a9-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="390a9-110">Example</span></span>  
 <span data-ttu-id="390a9-111">Nell'esempio di codice seguente viene illustrato come fornire un <xref:System.Xml.XmlDocument> al metodo <xref:System.Xml.Xsl.XslTransform>, con l'output inviato a un <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="390a9-111">The following code example shows how an <xref:System.Xml.XmlDocument> can be supplied to the <xref:System.Xml.Xsl.XslTransform>, with the output sent to an <xref:System.Xml.XmlReader>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="390a9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="390a9-112">See also</span></span>

- <xref:System.Xml.XmlDocument>
- [<span data-ttu-id="390a9-113">Trasformazioni XSLT con la classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="390a9-113">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="390a9-114">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="390a9-114">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="390a9-115">XPathNavigator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="390a9-115">XPathNavigator in Transformations</span></span>](xpathnavigator-in-transformations.md)
- [<span data-ttu-id="390a9-116">XPathNodeIterator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="390a9-116">XPathNodeIterator in Transformations</span></span>](xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="390a9-117">Input di XPathDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="390a9-117">XPathDocument Input to XslTransform</span></span>](xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="390a9-118">Input di XmlDataDocument in XslTransform</span><span class="sxs-lookup"><span data-stu-id="390a9-118">XmlDataDocument Input to XslTransform</span></span>](xmldatadocument-input-to-xsltransform.md)

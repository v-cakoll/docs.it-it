---
title: XPathNavigator nelle trasformazioni
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 118f97d1-7110-4d1b-b0bd-4143252c0bb0
ms.openlocfilehash: 240f9ca7a887a4a146437fdef46de776b299705a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709751"
---
# <a name="xpathnavigator-in-transformations"></a><span data-ttu-id="18a7b-102">XPathNavigator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="18a7b-102">XPathNavigator in Transformations</span></span>
<span data-ttu-id="18a7b-103">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce un accesso casuale di sola lettura ai dati ed è progettata per essere usata come input per XSLT (Extensible Stylesheet Language for Transformations).</span><span class="sxs-lookup"><span data-stu-id="18a7b-103">The <xref:System.Xml.XPath.XPathNavigator> class provides read-only random access to data and is designed for use as an input to Extensible Stylesheet Language for Transformations (XSLT).</span></span> <span data-ttu-id="18a7b-104">Viene implementata su <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument> e <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="18a7b-104">It is implemented on the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDataDocument>, and <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="18a7b-105"><xref:System.Xml.XPath.XPathNavigator> è basato sul modello di dati W3C (World Wide Web Consortium) secondo la descrizione fornita nella sezione 5 della raccomandazione XML Path Language (XPath) (informazioni in lingua inglese).</span><span class="sxs-lookup"><span data-stu-id="18a7b-105">The <xref:System.Xml.XPath.XPathNavigator> is based upon the World Wide Web Consortium (W3C) Data Model as described in section 5 of the XML Path Language (XPath) recommendation.</span></span>  
  
 <span data-ttu-id="18a7b-106"><xref:System.Xml.XPath.XPathNavigator> definisce un modello di cursore per qualsiasi archivio e fornisce query XPath rapide e di sola lettura per qualsiasi archivio dati.</span><span class="sxs-lookup"><span data-stu-id="18a7b-106">The <xref:System.Xml.XPath.XPathNavigator> defines a cursor model over any store and provides fast, read-only XPath queries over any data store.</span></span> <span data-ttu-id="18a7b-107"><xref:System.Xml.XPath.XPathNavigator> è inoltre la classe da usare per l'esecuzione di iterazioni sui frammenti di albero risultato.</span><span class="sxs-lookup"><span data-stu-id="18a7b-107">The <xref:System.Xml.XPath.XPathNavigator> is also the class to use for iterating over result tree fragments.</span></span>  
  
 <span data-ttu-id="18a7b-108">L'API consente di ottenere informazioni dal nodo corrente nell'archivio e di spostare i nodi collegati.</span><span class="sxs-lookup"><span data-stu-id="18a7b-108">The API enables you to get information from the current node in the store and move to connected nodes.</span></span> <span data-ttu-id="18a7b-109"><xref:System.Xml.XPath.XPathNavigator> è un modello di tipo cursore che esegue l'attraversamento di un archivio usando un set di metodi **Move**.</span><span class="sxs-lookup"><span data-stu-id="18a7b-109">The <xref:System.Xml.XPath.XPathNavigator> is a cursor style model that performs traversal over a store using a set of **Move** methods.</span></span> <span data-ttu-id="18a7b-110"><xref:System.Xml.XPath.XPathNavigator> viene sempre posizionato su un nodo.</span><span class="sxs-lookup"><span data-stu-id="18a7b-110">The <xref:System.Xml.XPath.XPathNavigator> is always positioned on a node.</span></span> <span data-ttu-id="18a7b-111">Qualsiasi metodo **Move** che abbia esito negativo lascia <xref:System.Xml.XPath.XPathNavigator> invariato.</span><span class="sxs-lookup"><span data-stu-id="18a7b-111">Any **Move** method that fails leaves the <xref:System.Xml.XPath.XPathNavigator> unchanged.</span></span>  
  
 <span data-ttu-id="18a7b-112"><xref:System.Xml.XPath.XPathNavigator> è la classe da usare per l'esecuzione di iterazioni sui frammenti di albero risultato.</span><span class="sxs-lookup"><span data-stu-id="18a7b-112">The <xref:System.Xml.XPath.XPathNavigator> is the class to use for iterating over result tree fragments.</span></span> <span data-ttu-id="18a7b-113">Nell'esempio di codice seguente viene illustrata la creazione di un frammento di albero risultato all'interno di un foglio di stile, chiamando la funzione con il parametro, `fragment`, che contiene l'XML</span><span class="sxs-lookup"><span data-stu-id="18a7b-113">The following code sample creates a result tree fragment within a style sheet by calling the function with the parameter, `fragment`, which contains XML.</span></span>  
  
## <a name="testxsl"></a><span data-ttu-id="18a7b-114">test.xsl</span><span class="sxs-lookup"><span data-stu-id="18a7b-114">test.xsl</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl ="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.adventure-works.com"  
                version="1.0">  
  
<xsl:variable name="fragment">  
    <authorlist>  
       <author>Joe</author>  
    </authorlist>  
</xsl:variable>  
  
<msxsl:script language="C#" implements-prefix="user">  
<![CDATA[  
   string NodeFragment(XPathNavigator nav)  
   {  
      if (nav.HasChildren)  
        return nav.Value;  
      else  
        return "";  
   }  
]]>  
</msxsl:script>  
  
<xsl:template match="/">  
     <xsl:value-of select="user:NodeFragment($fragment)"/>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a><span data-ttu-id="18a7b-115">test.xml</span><span class="sxs-lookup"><span data-stu-id="18a7b-115">test.xml</span></span>  
  
```xml  
<root>Some text</root>  
```  
  
 <span data-ttu-id="18a7b-116">Nell'esempio seguente vengono usati il foglio di stile **test.xsl** e i dati di input **test.xml**.</span><span class="sxs-lookup"><span data-stu-id="18a7b-116">The following code uses the **test.xsl** style sheet and **test.xml** input data.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
Public Class sample  
  
    Public Shared Sub Main()  
        Dim xslt As New XslTransform()  
        xslt.Load("test.xsl")  
  
        Dim xd As New XPathDocument("test.xml")  
  
        Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
        xslt.Transform(xd, Nothing, strmTemp, Nothing)  
    End Sub 'Main  
End Class 'sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Xsl;  
using System.Xml.XPath;  
using System.Text;  
  
public class sample  
{  
    public static void Main()  
    {  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, null, strmTemp, null);  
    }  
}  
```  
  
## <a name="output"></a><span data-ttu-id="18a7b-117">Output</span><span class="sxs-lookup"><span data-stu-id="18a7b-117">Output</span></span>  
 <span data-ttu-id="18a7b-118">Il risultato della trasformazione è riportato nel file **out.xml**:</span><span class="sxs-lookup"><span data-stu-id="18a7b-118">The result of the transformation is found in the file **out.xml**:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>Joe  
```  
  
## <a name="see-also"></a><span data-ttu-id="18a7b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18a7b-119">See also</span></span>

- [<span data-ttu-id="18a7b-120">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="18a7b-120">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)

---
title: XPathNodeIterator nelle trasformazioni
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2bc6ddc6-674a-4f75-b264-abc35e4e5857
ms.openlocfilehash: 63beeb3ca9d3f3cb6e6bde418e99ee2bd0a12e20
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709738"
---
# <a name="xpathnodeiterator-in-transformations"></a><span data-ttu-id="faa66-102">XPathNodeIterator nelle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="faa66-102">XPathNodeIterator in Transformations</span></span>
<span data-ttu-id="faa66-103">La classe <xref:System.Xml.XPath.XPathNodeIterator> fornisce i metodi per eseguire un'iterazione in un set di nodi creato come risultato di una query XPath (XML Path Language) o un frammento di albero risultato convertito in un set di nodi usando il metodo node-set.</span><span class="sxs-lookup"><span data-stu-id="faa66-103">The <xref:System.Xml.XPath.XPathNodeIterator> provides methods to iterate over a set of nodes created as the result of an XML Path Language (XPath) query or a result tree fragment converted to a node set by use of the node-set method.</span></span> <span data-ttu-id="faa66-104">La classe <xref:System.Xml.XPath.XPathNodeIterator> consente di eseguire un'iterazione tra i nodi all'interno di quel determinato set.</span><span class="sxs-lookup"><span data-stu-id="faa66-104">The <xref:System.Xml.XPath.XPathNodeIterator> enables you to iterate over the nodes within that node set.</span></span> <span data-ttu-id="faa66-105">Una volta recuperato il set di nodi, la classe <xref:System.Xml.XPath.XPathNodeIterator> fornisce al set di nodi selezionato un cursore forward-only di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="faa66-105">Once a node set is retrieved, the <xref:System.Xml.XPath.XPathNodeIterator> class provides a read-only, forward-only cursor to the selected set of nodes.</span></span> <span data-ttu-id="faa66-106">Il set di nodi viene creato in base all'ordine con cui è riportato nel documento, quindi la chiamata a questo metodo consente di spostarsi al nodo successivo nell'ordine del documento.</span><span class="sxs-lookup"><span data-stu-id="faa66-106">The node set is created in document order, so calling this method moves to the next node in document order.</span></span> <span data-ttu-id="faa66-107">L'oggetto <xref:System.Xml.XPath.XPathNodeIterator> non compila un albero con tutti i nodi del set,</span><span class="sxs-lookup"><span data-stu-id="faa66-107"><xref:System.Xml.XPath.XPathNodeIterator> does not build a node tree of all the nodes in the set.</span></span> <span data-ttu-id="faa66-108">bensì fornisce una finestra per i dati di ogni singolo nodo, esponendo il nodo sottostante a cui si riferisce quando il cursore viene spostato all'interno dell'albero.</span><span class="sxs-lookup"><span data-stu-id="faa66-108">Instead, it provides a single node window into the data, exposing the underlying node it points to as you move around in the tree.</span></span> <span data-ttu-id="faa66-109">I metodi e le proprietà disponibili nella classe <xref:System.Xml.XPath.XPathNodeIterator> consentono di ottenere informazioni dal nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="faa66-109">The methods and properties available from the <xref:System.Xml.XPath.XPathNodeIterator> class enable you to get information from the current node.</span></span> <span data-ttu-id="faa66-110">Per un elenco dei metodi e delle proprietà disponibili, vedere <xref:System.Windows.Forms.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="faa66-110">For a list of the available methods and properties, see <xref:System.Windows.Forms.ToolBar>.</span></span>  
  
 <span data-ttu-id="faa66-111">Poiché <xref:System.Xml.XPath.XPathNodeIterator> si sposta in un set di nodi creato da una query XPath e scorre solo in avanti, per spostarsi è necessario usare il metodo <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A>.</span><span class="sxs-lookup"><span data-stu-id="faa66-111">Since an <xref:System.Xml.XPath.XPathNodeIterator> moves over a set of nodes created from an XPath query and moves forward only, the way to move is by using the <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> method.</span></span> <span data-ttu-id="faa66-112">Il tipo restituito dal metodo è `Boolean`, con valore `true` se viene eseguito lo spostamento al nodo successivo selezionato e `false` se non vi sono altri nodi selezionati.</span><span class="sxs-lookup"><span data-stu-id="faa66-112">The return type of this method is `Boolean`, returning `true` if it moves to the next selected node, and `false` if there are no more selected nodes.</span></span> <span data-ttu-id="faa66-113">Se viene restituito `true`, nell'elenco seguente verranno illustrate le proprietà disponibili:</span><span class="sxs-lookup"><span data-stu-id="faa66-113">If it returns `true`, the following list shows the properties available:</span></span>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.Current%2A>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.CurrentPosition%2A>  
  
- <xref:System.Xml.XPath.XPathNodeIterator.Count%2A>  
  
 <span data-ttu-id="faa66-114">La prima volta che si visualizza un set di nodi, è necessario eseguire una chiamata al metodo <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> per posizionare il tipo <xref:System.Xml.XPath.XPathNodeIterator> sul primo nodo del set selezionato.</span><span class="sxs-lookup"><span data-stu-id="faa66-114">When you are looking at a node set for the first time, a call to <xref:System.Xml.XPath.XPathNodeIterator.MoveNext%2A> must be made to position the <xref:System.Xml.XPath.XPathNodeIterator> on the first node of the selected set.</span></span> <span data-ttu-id="faa66-115">In questo modo è possibile scrivere un ciclo while.</span><span class="sxs-lookup"><span data-stu-id="faa66-115">This allows a while loop to be written.</span></span>  
  
 <span data-ttu-id="faa66-116">Nell'esempio di codice seguente viene descritto come passare un tipo <xref:System.Xml.XPath.XPathNodeIterator> a un <xref:System.Xml.Xsl.XslTransform> come parametro nel tipo <xref:System.Xml.Xsl.XsltArgumentList>.</span><span class="sxs-lookup"><span data-stu-id="faa66-116">The following code example shows how to pass an <xref:System.Xml.XPath.XPathNodeIterator> to an <xref:System.Xml.Xsl.XslTransform> as a parameter in the <xref:System.Xml.Xsl.XsltArgumentList>.</span></span> <span data-ttu-id="faa66-117">L'input per il codice è **books.xml** e il foglio di stile è **text.xsl**.</span><span class="sxs-lookup"><span data-stu-id="faa66-117">The input to the code is **books.xml**, and the style sheet is **text.xsl**.</span></span> <span data-ttu-id="faa66-118">Il file **test.xml** è il tipo <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="faa66-118">The file **test.xml** is the <xref:System.Xml.XPath.XPathDocument>.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Xsl  
Imports System.Xml.XPath  
Imports System.Text  
  
Public Class sample  
  
   Public Shared Sub Main()  
      Dim Doc As New XPathDocument("books.xml")  
      Dim nav As XPathNavigator = Doc.CreateNavigator()  
      Dim Iterator As XPathNodeIterator = nav.Select("/bookstore/book")  
  
      Dim arg As New XsltArgumentList()  
      arg.AddParam("param1", "", Iterator)  
  
      Dim xslt As New XslTransform()  
      xslt.Load("test.xsl")  
  
      Dim xd As New XPathDocument("test.xml")  
  
      Dim strmTemp = New FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite)  
      xslt.Transform(xd, arg, strmTemp, Nothing)  
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
        XPathDocument Doc = new XPathDocument("books.xml");  
        XPathNavigator nav = Doc.CreateNavigator();  
        XPathNodeIterator Iterator = nav.Select("/bookstore/book");  
  
        XsltArgumentList arg = new XsltArgumentList();  
        arg.AddParam("param1", "", Iterator);  
  
        XslTransform xslt = new XslTransform();  
        xslt.Load("test.xsl");  
  
        XPathDocument xd = new XPathDocument("test.xml");  
  
        Stream strmTemp = new FileStream("out.xml", FileMode.Create, FileAccess.ReadWrite);  
        xslt.Transform(xd, arg, strmTemp, null);  
    }  
}  
```  
  
## <a name="booksxml"></a><span data-ttu-id="faa66-119">books.xml</span><span class="sxs-lookup"><span data-stu-id="faa66-119">books.xml</span></span>  
  
```xml  
<?xml version='1.0'?>  
<!-- This file represents a fragment of a book store inventory database. -->  
<bookstore specialty="novel">  
    <book style="autobiography">  
    <title>Seven Years in Trenton</title>  
        <author>  
            <first-name>Jay</first-name>  
            <last-name>Adams</last-name>  
            <award>Trenton Literary Review Honorable Mention</award>  
            <country>USA</country>  
        </author>  
        <price>12</price>  
    </book>  
    <book style="textbook">  
        <title>History of Trenton</title>  
        <author>  
            <first-name>Kim</first-name>  
            <last-name>Akers</last-name>  
            <publication>  
                Selected Short Stories of  
                <first-name>Scott</first-name>  
                <last-name>Bishop</last-name>  
                <country>US</country>  
            </publication>  
        </author>  
        <price>55</price>  
    </book>  
</bookstore>  
```  
  
## <a name="testxsl"></a><span data-ttu-id="faa66-120">test.xsl</span><span class="sxs-lookup"><span data-stu-id="faa66-120">test.xsl</span></span>  
  
```xml  
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl">  
  
<xsl:output method="xml" indent="yes"/>  
<xsl:param name="param1"/>  
  
<xsl:template match="/">  
    <out>  
        <xsl:for-each select="$param1/title">  
            <title><xsl:value-of select="."/></title>  
        </xsl:for-each>  
    </out>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="testxml"></a><span data-ttu-id="faa66-121">test.xml</span><span class="sxs-lookup"><span data-stu-id="faa66-121">test.xml</span></span>  
  
```xml  
<Title attr="Test">this is a test</Title>  
```  
  
## <a name="output-outxml"></a><span data-ttu-id="faa66-122">Output (out.xml)</span><span class="sxs-lookup"><span data-stu-id="faa66-122">Output (out.xml)</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<out>  
  <title>Seven Years in Trenton</title>  
  <title>History of Trenton</title>  
</out>  
```  
  
## <a name="see-also"></a><span data-ttu-id="faa66-123">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="faa66-123">See also</span></span>

- [<span data-ttu-id="faa66-124">Implementazione del processore XSLT da parte della classe XslTransform</span><span class="sxs-lookup"><span data-stu-id="faa66-124">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)

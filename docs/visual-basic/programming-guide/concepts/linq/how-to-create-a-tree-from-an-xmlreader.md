---
title: 'Procedura: Creare una struttura ad albero da un XmlReader (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
ms.openlocfilehash: d0826112821394ac6a81ba03e7803187aaec2796
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836467"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a><span data-ttu-id="18e12-102">Procedura: Creare una struttura ad albero da un XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18e12-102">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="18e12-103">In questo argomento viene illustrato come creare un albero XML direttamente da un oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="18e12-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="18e12-104">Per creare <xref:System.Xml.Linq.XElement> da <xref:System.Xml.XmlReader>, è necessario posizionare <xref:System.Xml.XmlReader> in un nodo di elemento.</span><span class="sxs-lookup"><span data-stu-id="18e12-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="18e12-105"><xref:System.Xml.XmlReader> ignorerà i commenti e le istruzioni di elaborazione, ma se <xref:System.Xml.XmlReader> è posizionato in un nodo di testo, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="18e12-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="18e12-106">Per evitare tali errori, posizionare <xref:System.Xml.XmlReader> in un elemento prima di creare l'albero XML da <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="18e12-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18e12-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="18e12-107">Example</span></span>  
 <span data-ttu-id="18e12-108">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="18e12-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="18e12-109">Nel codice seguente viene creato un oggetto `T:System.Xml.XmlReader`, quindi vengono letti i nodi fino a individuare il primo nodo di elemento.</span><span class="sxs-lookup"><span data-stu-id="18e12-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="18e12-110">Viene quindi caricato l'oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="18e12-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```vb  
Dim r As XmlReader = XmlReader.Create("books.xml")  
Do While r.NodeType <> XmlNodeType.Element  
    r.Read()  
Loop  
Dim e As XElement = XElement.Load(r)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="18e12-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="18e12-111">This example produces the following output:</span></span>  
  
```xml  
<Catalog>  
   <Book id="bk101">  
      <Author>Garghentini, Davide</Author>  
      <Title>XML Developer's Guide</Title>  
      <Genre>Computer</Genre>  
      <Price>44.95</Price>  
      <PublishDate>2000-10-01</PublishDate>  
      <Description>An in-depth look at creating applications   
      with XML.</Description>  
   </Book>  
   <Book id="bk102">  
      <Author>Garcia, Debra</Author>  
      <Title>Midnight Rain</Title>  
      <Genre>Fantasy</Genre>  
      <Price>5.95</Price>  
      <PublishDate>2000-12-16</PublishDate>  
      <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
   </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18e12-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18e12-112">See also</span></span>

- [<span data-ttu-id="18e12-113">Analisi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18e12-113">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)

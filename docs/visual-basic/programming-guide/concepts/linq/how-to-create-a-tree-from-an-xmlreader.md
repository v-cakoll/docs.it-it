---
title: 'Procedura: creare una struttura ad albero da XmlReader (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a60b5cb3557016bba7bae9be6e0b9c9a448c1284
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a><span data-ttu-id="567d3-102">Procedura: creare una struttura ad albero da XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="567d3-102">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>
<span data-ttu-id="567d3-103">In questo argomento viene illustrato come creare una struttura ad albero XML direttamente da un <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="567d3-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="567d3-104">Per creare un <xref:System.Xml.Linq.XElement>da un <xref:System.Xml.XmlReader>, è necessario posizionare il <xref:System.Xml.XmlReader>su un nodo elemento.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="567d3-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="567d3-105">Il <xref:System.Xml.XmlReader>ignorerà i commenti e istruzioni di elaborazione, ma se il <xref:System.Xml.XmlReader>è posizionato in un nodo di testo, verrà generato un errore.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="567d3-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="567d3-106">Per evitare tali errori, posizionare <xref:System.Xml.XmlReader>su un elemento prima di creare una struttura ad albero XML da <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="567d3-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="567d3-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="567d3-107">Example</span></span>  
 <span data-ttu-id="567d3-108">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="567d3-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="567d3-109">Nel codice seguente viene creato un oggetto `T:System.Xml.XmlReader`, quindi vengono letti i nodi fino a individuare il primo nodo di elemento.</span><span class="sxs-lookup"><span data-stu-id="567d3-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="567d3-110">Viene quindi caricato il <xref:System.Xml.Linq.XElement>oggetto.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="567d3-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```vb  
Dim r As XmlReader = XmlReader.Create("books.xml")  
Do While r.NodeType <> XmlNodeType.Element  
    r.Read()  
Loop  
Dim e As XElement = XElement.Load(r)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="567d3-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="567d3-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="567d3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="567d3-112">See Also</span></span>  
 [<span data-ttu-id="567d3-113">Analisi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="567d3-113">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)

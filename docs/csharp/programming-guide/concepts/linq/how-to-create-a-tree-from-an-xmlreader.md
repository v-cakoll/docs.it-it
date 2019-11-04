---
title: 'Procedura: Creare una struttura ad albero da un XmlReader (C#)'
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: a0cff596e0a6d50aefab3645a99beec3277d05ec
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418317"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a><span data-ttu-id="f1d70-102">Procedura: Creare una struttura ad albero da un XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="f1d70-102">How to: Create a Tree from an XmlReader (C#)</span></span>
<span data-ttu-id="f1d70-103">In questo argomento viene illustrato come creare un albero XML direttamente da un oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f1d70-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="f1d70-104">Per creare <xref:System.Xml.Linq.XElement> da <xref:System.Xml.XmlReader>, è necessario posizionare <xref:System.Xml.XmlReader> in un nodo di elemento.</span><span class="sxs-lookup"><span data-stu-id="f1d70-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="f1d70-105"><xref:System.Xml.XmlReader> ignorerà i commenti e le istruzioni di elaborazione, ma se <xref:System.Xml.XmlReader> è posizionato in un nodo di testo, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="f1d70-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="f1d70-106">Per evitare tali errori, posizionare <xref:System.Xml.XmlReader> in un elemento prima di creare l'albero XML da <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f1d70-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1d70-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="f1d70-107">Example</span></span>  
 <span data-ttu-id="f1d70-108">Questo esempio usa il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f1d70-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f1d70-109">Nel codice seguente viene creato un oggetto `T:System.Xml.XmlReader`, quindi vengono letti i nodi fino a individuare il primo nodo di elemento.</span><span class="sxs-lookup"><span data-stu-id="f1d70-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="f1d70-110">Viene quindi caricato l'oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="f1d70-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="f1d70-111">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f1d70-111">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1d70-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1d70-112">See also</span></span>

- [<span data-ttu-id="f1d70-113">Analisi di codice XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f1d70-113">Parsing XML (C#)</span></span>](how-to-parse-a-string.md)

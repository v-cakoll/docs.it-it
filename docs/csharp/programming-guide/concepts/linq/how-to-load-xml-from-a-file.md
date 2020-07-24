---
title: Come caricare XML da un file (C#)
description: Informazioni su come caricare XML da un URI usando il metodo XElement. Load in C#. In questo esempio viene caricato il file XML e l'albero XML viene stampato nella console.
ms.date: 07/20/2015
ms.assetid: 3ed38487-8028-4209-9872-c8dce0ed4dfe
ms.openlocfilehash: 29de914139d1e9abcda2097addca9219d44d2696
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104958"
---
# <a name="how-to-load-xml-from-a-file-c"></a><span data-ttu-id="42c29-104">Come caricare XML da un file (C#)</span><span class="sxs-lookup"><span data-stu-id="42c29-104">How to load XML from a file (C#)</span></span>
<span data-ttu-id="42c29-105">In questo argomento viene illustrato come caricare XML da un URI tramite il metodo <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="42c29-105">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42c29-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="42c29-106">Example</span></span>  
 <span data-ttu-id="42c29-107">Nell'esempio seguente viene illustrato come caricare un documento XML da un file.</span><span class="sxs-lookup"><span data-stu-id="42c29-107">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="42c29-108">Viene caricato il file books.xml e viene restituito l'albero XML alla console.</span><span class="sxs-lookup"><span data-stu-id="42c29-108">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="42c29-109">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="42c29-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XElement booksFromFile = XElement.Load(@"books.xml");  
Console.WriteLine(booksFromFile);  
```  
  
 <span data-ttu-id="42c29-110">Questo codice genera l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="42c29-110">This code produces the following output:</span></span>  
  
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
  
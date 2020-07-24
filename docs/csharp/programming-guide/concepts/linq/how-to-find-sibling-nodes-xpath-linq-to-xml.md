---
title: Come trovare nodi di pari livello (XPath-LINQ to XML) (C#)
description: In questo esempio di C# viene confrontato XPath con LINQ to XML per trovare tutti gli elementi di pari livello di un nodo con un nome specifico.
ms.date: 07/20/2015
ms.assetid: e2c73d10-a8ca-4e11-b5aa-d055de285874
ms.openlocfilehash: 2936fc4ad088580a9644f79f1797e679fe877e00
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105220"
---
# <a name="how-to-find-sibling-nodes-xpath-linq-to-xml-c"></a>Come trovare nodi di pari livello (XPath-LINQ to XML) (C#)
Può essere necessario trovare tutti i gli elementi di pari livello di un nodo che hanno un nome specifico. La raccolta risultante può includere il nodo di contesto, se anche quest'ultimo ha il nome specifico.  
  
 L'espressione XPath è:  
  
 `../Book`  
  
## <a name="example"></a>Esempio  
 In questo esempio viene dapprima ricercato un elemento `Book` e quindi tutti gli elementi di pari livello denominati `Book`. La raccolta risultante include il nodo di contesto.  
  
 Nell'esempio viene usato il documento XML seguente: [File XML di esempio: libri (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =
    books  
    .Root  
    .Elements("Book")  
    .Skip(1)  
    .First();  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    book  
    .Parent  
    .Elements("Book");  
  
// XPath expression  
IEnumerable<XElement> list2 = book.XPathSelectElements("../Book");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```output  
Results are identical  
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
```  

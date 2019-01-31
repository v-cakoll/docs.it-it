---
title: 'Procedura: Creare una struttura ad albero da un XmlReader (C#)'
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: fb65c7b74bf3bd006fd4f545e4587efe9a392131
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496182"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a>Procedura: Creare una struttura ad albero da un XmlReader (C#)
In questo argomento viene illustrato come creare un albero XML direttamente da un oggetto <xref:System.Xml.XmlReader>. Per creare <xref:System.Xml.Linq.XElement> da <xref:System.Xml.XmlReader>, è necessario posizionare <xref:System.Xml.XmlReader> in un nodo di elemento. <xref:System.Xml.XmlReader> ignorerà i commenti e le istruzioni di elaborazione, ma se <xref:System.Xml.XmlReader> è posizionato in un nodo di testo, verrà generato un errore. Per evitare tali errori, posizionare <xref:System.Xml.XmlReader> in un elemento prima di creare l'albero XML da <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio viene utilizzato il seguente documento XML:  [File XML di esempio: libri (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
 Nel codice seguente viene creato un oggetto `T:System.Xml.XmlReader`, quindi vengono letti i nodi fino a individuare il primo nodo di elemento. Viene quindi caricato l'oggetto <xref:System.Xml.Linq.XElement>.  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 Questo esempio produce il seguente output:  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Analisi di codice XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

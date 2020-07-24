---
title: Come eseguire query LINQ to XML usando XPath (C#)
description: È possibile usare i metodi di estensione in C# per eseguire query in un albero XML tramite XPath. In generale, non è consigliabile usare XPath con LINQ to XML.
ms.date: 07/20/2015
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: fff45a93380b5af85aa640fc690783cc95e6298b
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104350"
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a>Come eseguire query LINQ to XML usando XPath (C#)
In questo argomento vengono presentati i metodi di estensione che consentono di eseguire una query su un albero XML usando XPath. Per informazioni dettagliate sull'utilizzo di questi metodi di estensione, vedere <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
 A meno che non esista un motivo molto specifico per eseguire query tramite XPATH, ad esempio l'uso esteso di codice legacy, è preferibile non usare XPATH con LINQ to XML. Le query XPath non vengono eseguite con le stesse prestazioni delle query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata un piccolo albero XML e viene usato <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> per selezionare un set di elementi.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
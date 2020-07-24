---
title: Come recuperare un singolo attributo (LINQ to XML) (C#)
description: Informazioni su come usare LINQ to XML recuperare un singolo attributo di un elemento in C#, in base al nome dell'attributo.
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: 4efcae5324ad5a2e4664e68e35e15ec2053daece
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103430"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a>Come recuperare un singolo attributo (LINQ to XML) (C#)
In questo argomento viene illustrato come recuperare un singolo attributo di un elemento, dato il relativo nome. Questa procedura è utile per la scrittura di espressioni di query in cui si desidera trovare un elemento con un attributo specifico.  
  
 Il metodo <xref:System.Xml.Linq.XElement.Attribute%2A> della classe <xref:System.Xml.Linq.XElement> restituisce l'attributo <xref:System.Xml.Linq.XAttribute> con il nome specificato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato il metodo <xref:System.Xml.Linq.XElement.Attribute%2A>:  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 In questo esempio vengono individuati tutti i discendenti dell'albero denominato `Phone` e quindi l'attributo denominato `type`.  
  
 Questo codice genera l'output seguente:  
  
```output  
home  
work  
```  
  
## <a name="example"></a>Esempio  
 Se si desidera recuperare il valore dell'attributo, è possibile eseguirne il cast, come nel caso degli oggetti <xref:System.Xml.Linq.XElement>. L'esempio seguente illustra questa operazione.  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 Questo codice genera l'output seguente:  
  
```output  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce operatori di cast espliciti per la classe <xref:System.Xml.Linq.XAttribute> in `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` e `GUID?`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato lo stesso codice per un attributo all'interno di uno spazio dei nomi. Per altre informazioni, vedere [Panoramica degli spazi dei nomi (LINQ to XML)](namespaces-overview-linq-to-xml.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement cust = new XElement(aw + "PhoneNumbers",  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "home"),  
        "555-555-5555"),  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants(aw + "Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute(aw + "type"));  
```  
  
 Questo codice genera l'output seguente:  
  
```output  
home  
work  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (C#)](./linq-to-xml-axes-overview.md)

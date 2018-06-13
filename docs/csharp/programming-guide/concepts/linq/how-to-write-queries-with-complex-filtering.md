---
title: 'Procedura: Scrivere query con filtri complessi (C#)'
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 72c34f8ef8bebb3584e00cf040cfcdc35dfc3701
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324811"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a>Procedura: Scrivere query con filtri complessi (C#)
A volte si desidera scrivere query LINQ to XML con filtri complessi. Può ad esempio essere necessario trovare tutti gli elementi che hanno un elemento figlio con un determinato nome e valore. In questo argomento viene illustrato come scrivere una query di esempio con filtri complessi.  
  
## <a name="example"></a>Esempio  
 Nell'esempio viene illustrato come trovare tutti gli elementi `PurchaseOrder` che includono un elemento figlio `Address` con un attributo `Type` uguale a "Shipping" e un elemento figlio `State` uguale a "NY". Viene usata una query annidata nella clausola `Where` e l'operatore `Any` restituisce `true` se la raccolta contiene elementi. Per informazioni sull'uso della sintassi delle query basate su metodo, vedere [Sintassi di query e sintassi di metodi in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
 Per altre informazioni sull'operatore `Any`, vedere [Operazioni del quantificatore (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md).  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where   
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 L'output del codice è il seguente:  
  
```  
99505  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi. Per altre informazioni, vedere [Utilizzo degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto in uno spazio dei nomi](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 L'output del codice è il seguente:  
  
```  
99505  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [Query di base (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [Operazioni di proiezione (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)  
 [Operazioni del quantificatore (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)

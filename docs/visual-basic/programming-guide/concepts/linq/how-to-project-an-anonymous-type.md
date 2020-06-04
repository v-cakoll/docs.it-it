---
title: 'Procedura: Proiettare un tipo anonimo'
ms.date: 07/20/2015
ms.assetid: 30b42987-0e0e-4b2b-adb1-5255ddfbcd7b
ms.openlocfilehash: 459602eb7ede0bd055e00d3c7620cb95ec5408ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396480"
---
# <a name="how-to-project-an-anonymous-type-visual-basic"></a>Procedura: proiettare un tipo anonimo (Visual Basic)
In alcuni casi può necessario proiettare una query in un nuovo tipo, anche se è noto che questo tipo verrà usato solo per un breve periodo di tempo. La creazione di un nuovo tipo solo per usarlo nella proiezione implica molto lavoro supplementare. Un approccio più efficiente in questo caso consiste nella proiezione in un tipo anonimo. I tipi anonimi consentono di definire una classe, quindi dichiarare e inizializzare un oggetto di tale classe, senza assegnare un nome alla classe.  
  
 I tipi anonimi sono l'implementazione C# del concetto matematico di *tupla*. Il termine matematico tupla deriva dalla sequenza singolo, doppio, triplo, quadruplo, quintuplo, n-plo. Fa riferimento a una sequenza finita di oggetti, ognuno di un tipo specifico, denominata a volte elenco di coppie nome/valore. Ad esempio, il contenuto di un indirizzo nel documento XML [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) potrebbe essere espresso come segue:  
  
```  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 Quando si crea un'istanza di un tipo anonimo, è utile considerare questa operazione come la creazione di una tupla di ordine n. Se si scrive una query che crea una tupla nella clausola `Select`, la query restituisce un oggetto `IEnumerable` della tupla.  
  
## <a name="example"></a>Esempio  
 In questo esempio la clausola `Select` proietta un tipo anonimo. Viene quindi usato `Dim` per creare l'oggetto `IEnumerable`. All'interno del ciclo `For Each` la variabile di iterazione diventa un'istanza del tipo anonimo creata nell'espressione di query.  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
```vb  
Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
Dim custList = _  
    From el In custOrd.<Customers>.<Customer> _  
    Select New With { _  
        .CustomerID = el.@<CustomerID>, _  
        .CompanyName = el.<CompanyName>.Value, _  
        .ContactName = el.<ContactName>.Value _  
    }  
For Each cust In custList  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName)  
Next  
```  
  
 L'output del codice è il seguente:  
  
```console  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a>Vedere anche

- [Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)](projections-and-transformations-linq-to-xml.md)

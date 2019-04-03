---
title: 'Procedura: Proiettare un tipo anonimo (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 30b42987-0e0e-4b2b-adb1-5255ddfbcd7b
ms.openlocfilehash: cc8e59ac1037fc173cb44d8c8ff344374c5766ae
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834569"
---
# <a name="how-to-project-an-anonymous-type-visual-basic"></a><span data-ttu-id="8fe5a-102">Procedura: Proiettare un tipo anonimo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fe5a-102">How to: Project an Anonymous Type (Visual Basic)</span></span>
<span data-ttu-id="8fe5a-103">In alcuni casi può necessario proiettare una query in un nuovo tipo, anche se è noto che questo tipo verrà usato solo per un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-103">In some cases you might want to project a query to a new type, even though you know you will only use this type for a short while.</span></span> <span data-ttu-id="8fe5a-104">La creazione di un nuovo tipo solo per usarlo nella proiezione implica molto lavoro supplementare.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-104">It is a lot of extra work to create a new type just to use in the projection.</span></span> <span data-ttu-id="8fe5a-105">Un approccio più efficiente in questo caso consiste nella proiezione in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-105">A more efficient approach in this case is to project to an anonymous type.</span></span> <span data-ttu-id="8fe5a-106">I tipi anonimi consentono di definire una classe, quindi dichiarare e inizializzare un oggetto di tale classe, senza assegnare un nome alla classe.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-106">Anonymous types allow you to define a class, then declare and initialize an object of that class, without giving the class a name.</span></span>  
  
 <span data-ttu-id="8fe5a-107">I tipi anonimi sono l'implementazione C# del concetto matematico di *tupla*.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-107">Anonymous types are the C# implementation of the mathematical concept of a *tuple*.</span></span> <span data-ttu-id="8fe5a-108">Il termine matematico tupla deriva dalla sequenza singolo, doppio, triplo, quadruplo, quintuplo, n-plo.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-108">The mathematical term tuple originated from the sequence single, double, triple, quadruple, quintuple, n-tuple.</span></span> <span data-ttu-id="8fe5a-109">Fa riferimento a una sequenza finita di oggetti, ognuno di un tipo specifico,</span><span class="sxs-lookup"><span data-stu-id="8fe5a-109">It refers to a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="8fe5a-110">denominata a volte elenco di coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-110">Sometimes this is called a list of name/value pairs.</span></span> <span data-ttu-id="8fe5a-111">Ad esempio, il contenuto di un indirizzo nel documento XML [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) potrebbe essere espresso come segue:</span><span class="sxs-lookup"><span data-stu-id="8fe5a-111">For example, the contents of an address in the [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) XML document could be expressed as follows:</span></span>  
  
```  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 <span data-ttu-id="8fe5a-112">Quando si crea un'istanza di un tipo anonimo, è utile considerare questa operazione come la creazione di una tupla di ordine n.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-112">When you create an instance of an anonymous type, it is convenient to think of it as creating a tuple of order n.</span></span> <span data-ttu-id="8fe5a-113">Se si scrive una query che crea una tupla nella clausola `Select`, la query restituisce un oggetto `IEnumerable` della tupla.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-113">If you write a query that creates a tuple in the `Select` clause, the query returns an `IEnumerable` of the tuple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fe5a-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="8fe5a-114">Example</span></span>  
 <span data-ttu-id="8fe5a-115">In questo esempio la clausola `Select` proietta un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-115">In this example, the `Select` clause projects an anonymous type.</span></span> <span data-ttu-id="8fe5a-116">Viene quindi usato `Dim` per creare l'oggetto `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-116">The example then uses `Dim` to create the `IEnumerable` object.</span></span> <span data-ttu-id="8fe5a-117">All'interno del ciclo `For Each` la variabile di iterazione diventa un'istanza del tipo anonimo creata nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="8fe5a-117">Within the `For Each` loop, the iteration variable becomes an instance of the anonymous type created in the query expression.</span></span>  
  
 <span data-ttu-id="8fe5a-118">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8fe5a-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="8fe5a-119">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8fe5a-119">This code produces the following output:</span></span>  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="8fe5a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fe5a-120">See also</span></span>

- [<span data-ttu-id="8fe5a-121">Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8fe5a-121">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

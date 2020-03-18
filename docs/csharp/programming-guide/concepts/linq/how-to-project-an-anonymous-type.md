---
title: Come proiettare un tipo anonimo (C
ms.date: 07/20/2015
ms.assetid: 5cb9be13-5ac4-4373-a034-b3520a5b2dec
ms.openlocfilehash: 7797c8bfb12943af1ce7f975b170bf002aa7d6fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345726"
---
# <a name="how-to-project-an-anonymous-type-c"></a><span data-ttu-id="ff71d-102">Come proiettare un tipo anonimo (C</span><span class="sxs-lookup"><span data-stu-id="ff71d-102">How to project an anonymous type (C#)</span></span>
<span data-ttu-id="ff71d-103">In alcuni casi può necessario proiettare una query in un nuovo tipo, anche se è noto che questo tipo verrà usato solo per un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="ff71d-103">In some cases you might want to project a query to a new type, even though you know you will only use this type for a short while.</span></span> <span data-ttu-id="ff71d-104">La creazione di un nuovo tipo solo per usarlo nella proiezione implica molto lavoro supplementare.</span><span class="sxs-lookup"><span data-stu-id="ff71d-104">It is a lot of extra work to create a new type just to use in the projection.</span></span> <span data-ttu-id="ff71d-105">Un approccio più efficiente in questo caso consiste nella proiezione in un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="ff71d-105">A more efficient approach in this case is to project to an anonymous type.</span></span> <span data-ttu-id="ff71d-106">I tipi anonimi consentono di definire una classe, quindi dichiarare e inizializzare un oggetto di tale classe, senza assegnare un nome alla classe.</span><span class="sxs-lookup"><span data-stu-id="ff71d-106">Anonymous types allow you to define a class, then declare and initialize an object of that class, without giving the class a name.</span></span>  
  
 <span data-ttu-id="ff71d-107">I tipi anonimi sono l'implementazione C# del concetto matematico di *tupla*.</span><span class="sxs-lookup"><span data-stu-id="ff71d-107">Anonymous types are the C# implementation of the mathematical concept of a *tuple*.</span></span> <span data-ttu-id="ff71d-108">Il termine matematico tupla deriva dalla sequenza singolo, doppio, triplo, quadruplo, quintuplo, n-plo.</span><span class="sxs-lookup"><span data-stu-id="ff71d-108">The mathematical term tuple originated from the sequence single, double, triple, quadruple, quintuple, n-tuple.</span></span> <span data-ttu-id="ff71d-109">Fa riferimento a una sequenza finita di oggetti, ognuno di un tipo specifico,</span><span class="sxs-lookup"><span data-stu-id="ff71d-109">It refers to a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="ff71d-110">denominata a volte elenco di coppie nome/valore.</span><span class="sxs-lookup"><span data-stu-id="ff71d-110">Sometimes this is called a list of name/value pairs.</span></span> <span data-ttu-id="ff71d-111">Ad esempio, il contenuto di un indirizzo nel documento XML [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) potrebbe essere espresso come segue:</span><span class="sxs-lookup"><span data-stu-id="ff71d-111">For example, the contents of an address in the [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) XML document could be expressed as follows:</span></span>  
  
```text  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 <span data-ttu-id="ff71d-112">Quando si crea un'istanza di un tipo anonimo, è utile considerare questa operazione come la creazione di una tupla di ordine n.</span><span class="sxs-lookup"><span data-stu-id="ff71d-112">When you create an instance of an anonymous type, it is convenient to think of it as creating a tuple of order n.</span></span> <span data-ttu-id="ff71d-113">Se si scrive una query che crea una tupla nella clausola `select`, la query restituisce un oggetto `IEnumerable` della tupla.</span><span class="sxs-lookup"><span data-stu-id="ff71d-113">If you write a query that creates a tuple in the `select` clause, the query returns an `IEnumerable` of the tuple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff71d-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff71d-114">Example</span></span>  
 <span data-ttu-id="ff71d-115">In questo esempio la clausola `select` proietta un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="ff71d-115">In this example, the `select` clause projects an anonymous type.</span></span> <span data-ttu-id="ff71d-116">Viene quindi usato `var` per creare l'oggetto `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="ff71d-116">The example then uses `var` to create the `IEnumerable` object.</span></span> <span data-ttu-id="ff71d-117">All'interno del ciclo `foreach` la variabile di iterazione diventa un'istanza del tipo anonimo creata nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="ff71d-117">Within the `foreach` loop, the iteration variable becomes an instance of the anonymous type created in the query expression.</span></span>  
  
 <span data-ttu-id="ff71d-118">Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="ff71d-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
var custList =  
    from el in custOrd.Element("Customers").Elements("Customer")  
    select new {  
        CustomerID = (string)el.Attribute("CustomerID"),  
        CompanyName = (string)el.Element("CompanyName"),  
        ContactName = (string)el.Element("ContactName")  
    };  
foreach (var cust in custList)  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName);  
```  
  
 <span data-ttu-id="ff71d-119">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ff71d-119">This code produces the following output:</span></span>  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
---
title: Prestazioni delle query concatenate (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
ms.openlocfilehash: e099d4d725a0603df61f5e308ce9897feec0af29
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54677317"
---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a><span data-ttu-id="b2f57-102">Prestazioni delle query concatenate (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b2f57-102">Performance of Chained Queries (LINQ to XML) (C#)</span></span>
<span data-ttu-id="b2f57-103">Uno dei più importanti vantaggi di LINQ (e di LINQ to XML) consiste nel fatto che le query concatenate possono offrire le stesse prestazioni di una singola query di dimensioni maggiori e più complessa.</span><span class="sxs-lookup"><span data-stu-id="b2f57-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>  
  
 <span data-ttu-id="b2f57-104">Una query concatenata è una query che usa un'altra query come origine.</span><span class="sxs-lookup"><span data-stu-id="b2f57-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="b2f57-105">Nel semplice codice seguente, ad esempio, `query2` è l'origine di `query1`:</span><span class="sxs-lookup"><span data-stu-id="b2f57-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    new XElement("Child", 3),  
    new XElement("Child", 4)  
);  
  
var query1 = from x in root.Elements("Child")  
             where (int)x >= 3  
             select x;  
  
var query2 = from e in query1  
             where (int)e % 2 == 0  
             select e;  
  
foreach (var i in query2)  
    Console.WriteLine("{0}", (int)i);  
```  
  
 <span data-ttu-id="b2f57-106">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="b2f57-106">This example produces the following output:</span></span>  
  
```  
4  
```  
  
 <span data-ttu-id="b2f57-107">Questa query concatenata offre lo stesso profilo di prestazioni dell'iterazione in un elenco collegato.</span><span class="sxs-lookup"><span data-stu-id="b2f57-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>  
  
-   <span data-ttu-id="b2f57-108">L'asse <xref:System.Xml.Linq.XContainer.Elements%2A> offre essenzialmente le stesse prestazioni dell'iterazione in un elenco collegato.</span><span class="sxs-lookup"><span data-stu-id="b2f57-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="b2f57-109"><xref:System.Xml.Linq.XContainer.Elements%2A> viene implementato come iteratore con esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="b2f57-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="b2f57-110">Questo significa che esegue alcune operazioni in aggiunta all'iterazione nell'elenco collegato, ad esempio l'allocazione dell'oggetto iteratore e la registrazione dello stato di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b2f57-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="b2f57-111">Queste operazioni possono essere divise in due categorie: le operazioni eseguite al momento della configurazione dell'iteratore e quelle eseguite durante ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="b2f57-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="b2f57-112">Le operazioni di configurazione implicano una quantità di lavoro piccola e fissa, mentre quelle eseguite durante ogni iterazione sono proporzionali al numero di elementi nella raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="b2f57-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>  
  
-   <span data-ttu-id="b2f57-113">In `query1` la clausola `where` comporta la chiamata al metodo <xref:System.Linq.Enumerable.Where%2A> da parte della query.</span><span class="sxs-lookup"><span data-stu-id="b2f57-113">In `query1`, the `where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="b2f57-114">Questo metodo è implementato anche come iteratore.</span><span class="sxs-lookup"><span data-stu-id="b2f57-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="b2f57-115">Le operazioni di configurazione consistono nella creazione di un'istanza del delegato che fa riferimento all'espressione lambda, nonché nelle normali operazioni di configurazione per un iteratore.</span><span class="sxs-lookup"><span data-stu-id="b2f57-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="b2f57-116">A ogni iterazione, il delegato viene chiamato per eseguire il predicato.</span><span class="sxs-lookup"><span data-stu-id="b2f57-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="b2f57-117">Le operazioni di configurazione e quelle eseguite durante ogni iterazione sono simili a quelle eseguite durante l'iterazione nell'asse.</span><span class="sxs-lookup"><span data-stu-id="b2f57-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>  
  
-   <span data-ttu-id="b2f57-118">In `query1` la clausola select comporta la chiamata al metodo <xref:System.Linq.Enumerable.Select%2A> da parte della query.</span><span class="sxs-lookup"><span data-stu-id="b2f57-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="b2f57-119">Questo metodo ha lo stesso profilo di prestazioni del metodo <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2f57-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>  
  
-   <span data-ttu-id="b2f57-120">In `query2` sia la clausola `where` che la clausola `select` hanno lo stesso profilo di prestazioni, come in `query1`.</span><span class="sxs-lookup"><span data-stu-id="b2f57-120">In `query2`, both the `where` clause and the `select` clause have the same performance profile as in `query1`.</span></span>  
  
 <span data-ttu-id="b2f57-121">L'iterazione in `query2` è pertanto direttamente proporzionale al numero di elementi nell'origine della prima query, in altre parole un tempo lineare.</span><span class="sxs-lookup"><span data-stu-id="b2f57-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span> <span data-ttu-id="b2f57-122">In un esempio di Visual Basic corrispondente il profilo di prestazioni sarebbe lo stesso.</span><span class="sxs-lookup"><span data-stu-id="b2f57-122">A corresponding Visual Basic example would have the same performance profile.</span></span>  
  
 <span data-ttu-id="b2f57-123">Per altre informazioni sugli iteratori, vedere [yield](../../../../csharp/language-reference/keywords/yield.md).</span><span class="sxs-lookup"><span data-stu-id="b2f57-123">For more information on iterators, see [yield](../../../../csharp/language-reference/keywords/yield.md).</span></span>  
  
 <span data-ttu-id="b2f57-124">Per un'esercitazione più dettagliata sul concatenamento di query, vedere [Esercitazione: Concatenamento di query](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span><span class="sxs-lookup"><span data-stu-id="b2f57-124">For a more detailed tutorial on chaining queries together, see [Tutorial: Chaining Queries Together](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f57-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2f57-125">See also</span></span>

- [<span data-ttu-id="b2f57-126">Prestazioni (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b2f57-126">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)

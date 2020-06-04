---
title: Prestazioni delle query concatenate (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
ms.openlocfilehash: 6b87f2744f663ebd45dceb036dcaac71b80765fc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396389"
---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="6d913-102">Prestazioni delle query concatenate (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d913-102">Performance of Chained Queries (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="6d913-103">Uno dei più importanti vantaggi di LINQ (e di LINQ to XML) consiste nel fatto che le query concatenate possono offrire le stesse prestazioni di una singola query di dimensioni maggiori e più complessa.</span><span class="sxs-lookup"><span data-stu-id="6d913-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>

<span data-ttu-id="6d913-104">Una query concatenata è una query che usa un'altra query come origine.</span><span class="sxs-lookup"><span data-stu-id="6d913-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="6d913-105">Nel semplice codice seguente, ad esempio, `query2` è l'origine di `query1`:</span><span class="sxs-lookup"><span data-stu-id="6d913-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>

```vb
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))

Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x

Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e

For Each i As var In query2
    Console.WriteLine("{0}", CInt(i))
Next
```

<span data-ttu-id="6d913-106">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="6d913-106">This example produces the following output:</span></span>

```console
4
```

<span data-ttu-id="6d913-107">Questa query concatenata offre lo stesso profilo di prestazioni dell'iterazione in un elenco collegato.</span><span class="sxs-lookup"><span data-stu-id="6d913-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>

- <span data-ttu-id="6d913-108">L'asse <xref:System.Xml.Linq.XContainer.Elements%2A> offre essenzialmente le stesse prestazioni dell'iterazione in un elenco collegato.</span><span class="sxs-lookup"><span data-stu-id="6d913-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="6d913-109"><xref:System.Xml.Linq.XContainer.Elements%2A> viene implementato come iteratore con esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="6d913-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="6d913-110">Questo significa che esegue alcune operazioni in aggiunta all'iterazione nell'elenco collegato, ad esempio l'allocazione dell'oggetto iteratore e la registrazione dello stato di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6d913-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="6d913-111">Queste operazioni possono essere divise in due categorie: le operazioni eseguite al momento della configurazione dell'iteratore e quelle eseguite durante ogni iterazione.</span><span class="sxs-lookup"><span data-stu-id="6d913-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="6d913-112">Le operazioni di configurazione implicano una quantità di lavoro piccola e fissa, mentre quelle eseguite durante ogni iterazione sono proporzionali al numero di elementi nella raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="6d913-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>

- <span data-ttu-id="6d913-113">In `query1` la clausola `Where` comporta la chiamata al metodo <xref:System.Linq.Enumerable.Where%2A> da parte della query.</span><span class="sxs-lookup"><span data-stu-id="6d913-113">In `query1`, the `Where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="6d913-114">Questo metodo è implementato anche come iteratore.</span><span class="sxs-lookup"><span data-stu-id="6d913-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="6d913-115">Le operazioni di configurazione consistono nella creazione di un'istanza del delegato che fa riferimento all'espressione lambda, nonché nelle normali operazioni di configurazione per un iteratore.</span><span class="sxs-lookup"><span data-stu-id="6d913-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="6d913-116">A ogni iterazione, il delegato viene chiamato per eseguire il predicato.</span><span class="sxs-lookup"><span data-stu-id="6d913-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="6d913-117">Le operazioni di configurazione e quelle eseguite durante ogni iterazione sono simili a quelle eseguite durante l'iterazione nell'asse.</span><span class="sxs-lookup"><span data-stu-id="6d913-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>

- <span data-ttu-id="6d913-118">In `query1` la clausola select comporta la chiamata al metodo <xref:System.Linq.Enumerable.Select%2A> da parte della query.</span><span class="sxs-lookup"><span data-stu-id="6d913-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="6d913-119">Questo metodo ha lo stesso profilo di prestazioni del metodo <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="6d913-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>

- <span data-ttu-id="6d913-120">In `query2` sia la clausola `Where` che la clausola `Select` hanno lo stesso profilo di prestazioni, come in `query1`.</span><span class="sxs-lookup"><span data-stu-id="6d913-120">In `query2`, both the `Where` clause and the `Select` clause have the same performance profile as in `query1`.</span></span>

 <span data-ttu-id="6d913-121">L'iterazione in `query2` è pertanto direttamente proporzionale al numero di elementi nell'origine della prima query, in altre parole un tempo lineare.</span><span class="sxs-lookup"><span data-stu-id="6d913-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d913-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d913-122">See also</span></span>

- [<span data-ttu-id="6d913-123">Prestazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d913-123">Performance (LINQ to XML) (Visual Basic)</span></span>](performance-linq-to-xml.md)

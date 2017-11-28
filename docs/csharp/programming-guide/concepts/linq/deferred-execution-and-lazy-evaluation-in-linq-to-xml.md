---
title: Esecuzione posticipata e valutazione lazy in LINQ to XML (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 847d8f830c26f54521664accc4bf569f822f255a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-c"></a><span data-ttu-id="af535-102">Esecuzione posticipata e valutazione lazy in LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="af535-102">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>
<span data-ttu-id="af535-103">Operazioni di query e su asse vengono spesso implementate in modo da usare l'esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="af535-103">Query and axis operations are often implemented to use deferred execution.</span></span> <span data-ttu-id="af535-104">In questo argomento vengono illustrati requisiti e vantaggi dell'esecuzione posticipata e vengono fornite alcune considerazioni sull'implementazione.</span><span class="sxs-lookup"><span data-stu-id="af535-104">This topic explains the requirements and advantages of deferred execution, and some implementation considerations.</span></span>  
  
## <a name="deferred-execution"></a><span data-ttu-id="af535-105">Esecuzione posticipata</span><span class="sxs-lookup"><span data-stu-id="af535-105">Deferred Execution</span></span>  
 <span data-ttu-id="af535-106">Per esecuzione posticipata si intende che la valutazione di un'espressione viene ritardata finché il relativo valore *realizzato* non risulta effettivamente necessario.</span><span class="sxs-lookup"><span data-stu-id="af535-106">Deferred execution means that the evaluation of an expression is delayed until its *realized* value is actually required.</span></span> <span data-ttu-id="af535-107">L'esecuzione posticipata può contribuire a migliorare notevolmente le prestazioni quando è necessario modificare grandi raccolte di dati, in particolare in programmi che contengono una serie di modifiche o query concatenate.</span><span class="sxs-lookup"><span data-stu-id="af535-107">Deferred execution can greatly improve performance when you have to manipulate large data collections, especially in programs that contain a series of chained queries or manipulations.</span></span> <span data-ttu-id="af535-108">Nel migliore dei casi l'esecuzione posticipata consente di eseguire un'unica iterazione nella raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="af535-108">In the best case, deferred execution enables only a single iteration through the source collection.</span></span>  
  
 <span data-ttu-id="af535-109">Le tecnologie LINQ usano notevolmente l'esecuzione posticipata sia nei membri di classi <xref:System.Linq?displayProperty=nameWithType> principali che nei metodi di estensione dei diversi spazi dei nomi LINQ, ad esempio <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af535-109">The LINQ technologies make extensive use of deferred execution in both the members of core <xref:System.Linq?displayProperty=nameWithType> classes and in the extension methods in the various LINQ namespaces, such as <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="af535-110">L'esecuzione posticipata è supportata direttamente nel linguaggio C# usando la parola chiave [yield](../../../../csharp/language-reference/keywords/yield.md) (sotto forma di istruzione `yield-return`) quando viene usata all'interno di un blocco iteratore.</span><span class="sxs-lookup"><span data-stu-id="af535-110">Deferred execution is supported directly in the C# language by the [yield](../../../../csharp/language-reference/keywords/yield.md) keyword (in the form of the `yield-return` statement) when used within an iterator block.</span></span> <span data-ttu-id="af535-111">Tale iteratore deve restituire una raccolta di tipo <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> (o un tipo derivato).</span><span class="sxs-lookup"><span data-stu-id="af535-111">Such an iterator must return a collection of type <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> (or a derived type).</span></span>  
  
## <a name="eager-vs-lazy-evaluation"></a><span data-ttu-id="af535-112">Valutazione eager e valutazione lazy</span><span class="sxs-lookup"><span data-stu-id="af535-112">Eager vs. Lazy Evaluation</span></span>  
 <span data-ttu-id="af535-113">Quando si scrive un metodo che implementa l'esecuzione posticipata, è inoltre necessario decidere se implementare il metodo tramite la valutazione lazy o la valutazione eager.</span><span class="sxs-lookup"><span data-stu-id="af535-113">When you write a method that implements deferred execution, you also have to decide whether to implement the method using lazy evaluation or eager evaluation.</span></span>  
  
-   <span data-ttu-id="af535-114">Nella *valutazione lazy* durante ogni chiamata all'iteratore viene elaborato un unico elemento della raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="af535-114">In *lazy evaluation*, a single element of the source collection is processed during each call to the iterator.</span></span> <span data-ttu-id="af535-115">Si tratta della modalità di implementazione tipica degli iteratori.</span><span class="sxs-lookup"><span data-stu-id="af535-115">This is the typical way in which iterators are implemented.</span></span>  
  
-   <span data-ttu-id="af535-116">Nella *valutazione eager* in seguito alla prima chiamata all'iteratore verrà elaborata l'intera raccolta.</span><span class="sxs-lookup"><span data-stu-id="af535-116">In *eager evaluation*, the first call to the iterator will result in the entire collection being processed.</span></span> <span data-ttu-id="af535-117">Potrebbe inoltre essere necessaria una copia temporanea della raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="af535-117">A temporary copy of the source collection might also be required.</span></span> <span data-ttu-id="af535-118">Ad esempio, il metodo <xref:System.Linq.Enumerable.OrderBy%2A> deve ordinare l'intera raccolta prima di restituire il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="af535-118">For example, the <xref:System.Linq.Enumerable.OrderBy%2A> method has to sort the entire collection before it returns the first element.</span></span>  
  
 <span data-ttu-id="af535-119">La valutazione lazy offre in genere prestazioni migliori perché implica una distribuzione uniforme dell'overhead di elaborazione in tutte le fasi della valutazione della raccolta e riduce al minimo l'uso di dati temporanei.</span><span class="sxs-lookup"><span data-stu-id="af535-119">Lazy evaluation usually yields better performance because it distributes overhead processing evenly throughout the evaluation of the collection and minimizes the use of temporary data.</span></span> <span data-ttu-id="af535-120">Per alcune operazioni è naturalmente inevitabile dover materializzare i risultati intermedi.</span><span class="sxs-lookup"><span data-stu-id="af535-120">Of course, for some operations, there is no other option than to materialize intermediate results.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="af535-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="af535-121">Next Steps</span></span>  
 <span data-ttu-id="af535-122">Nel successivo argomento dell'esercitazione verrà illustrata l'esecuzione posticipata:</span><span class="sxs-lookup"><span data-stu-id="af535-122">The next topic in this tutorial illustrates deferred execution:</span></span>  
  
-   [<span data-ttu-id="af535-123">Esempio di esecuzione posticipata (C#)</span><span class="sxs-lookup"><span data-stu-id="af535-123">Deferred Execution Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="af535-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af535-124">See Also</span></span>  
 [<span data-ttu-id="af535-125">Esercitazione: Concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="af535-125">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)  
 [<span data-ttu-id="af535-126">Concetti e terminologia (trasformazione funzionale) (C#)</span><span class="sxs-lookup"><span data-stu-id="af535-126">Concepts and Terminology (Functional Transformation) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)  
 [<span data-ttu-id="af535-127">Operazioni di aggregazione (C#)</span><span class="sxs-lookup"><span data-stu-id="af535-127">Aggregation Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md)  
 [<span data-ttu-id="af535-128">yield</span><span class="sxs-lookup"><span data-stu-id="af535-128">yield</span></span>](../../../../csharp/language-reference/keywords/yield.md)

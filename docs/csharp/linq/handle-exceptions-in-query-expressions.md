---
title: Gestire le eccezioni nelle espressioni di query
description: Come gestire le eccezioni nelle espressioni di query.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9ce4a4ca62bb476b2414ec8b93d5633faca53b59
ms.contentlocale: it-it
ms.lasthandoff: 08/11/2017

---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="cafcf-104">Gestire le eccezioni nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="cafcf-104">Handle exceptions in query expressions</span></span>

<span data-ttu-id="cafcf-105">Nel contesto di un'espressione di query è possibile chiamare qualsiasi metodo.</span><span class="sxs-lookup"><span data-stu-id="cafcf-105">It is possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="cafcf-106">È tuttavia consigliabile non chiamare in un'espressione di query i metodi che possono creare un effetto collaterale, ad esempio la modifica del contenuto dell'origine dati o la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cafcf-106">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="cafcf-107">In questo esempio viene illustrato come evitare di generare eccezioni quando si chiamano i metodi in un'espressione di query senza violare le linee guida generali di .NET Framework sulla gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="cafcf-107">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET Framework guidelines on exception handling.</span></span> <span data-ttu-id="cafcf-108">Tali linee guida stabiliscono che è accettabile intercettare un'eccezione specifica quando è evidente il motivo per cui verrà generata in un contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="cafcf-108">Those guidelines state that it is acceptable to catch a specific exception when you understand why it will be thrown in a given context.</span></span> <span data-ttu-id="cafcf-109">Per altre informazioni, vedere [Suggerimenti per le eccezioni](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="cafcf-109">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>  
  
 <span data-ttu-id="cafcf-110">Nell'esempio finale viene illustrato come gestire quei casi in cui è necessario generare un'eccezione durante l'esecuzione di una query.</span><span class="sxs-lookup"><span data-stu-id="cafcf-110">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cafcf-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="cafcf-111">Example</span></span>  

 <span data-ttu-id="cafcf-112">Nell'esempio seguente viene illustrato come spostare codice di gestione dell'eccezione al di fuori di un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="cafcf-112">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="cafcf-113">Questa operazione è possibile solo quando il metodo non dipende da variabili locali per la query.</span><span class="sxs-lookup"><span data-stu-id="cafcf-113">This is only possible when the method does not depend on any variables local to the query.</span></span>  
  
 <span data-ttu-id="cafcf-114">[!code-cs[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cafcf-114">[!code-cs[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cafcf-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="cafcf-115">Example</span></span> 

 <span data-ttu-id="cafcf-116">In alcuni casi la migliore risposta a un'eccezione generata all'interno di una query potrebbe essere l'arresto immediato dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="cafcf-116">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="cafcf-117">Nell'esempio seguente viene illustrato come gestire le eccezioni che potrebbero essere generate all'interno del corpo di una query.</span><span class="sxs-lookup"><span data-stu-id="cafcf-117">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="cafcf-118">Si supponga che `SomeMethodThatMightThrow` possa potenzialmente generare un'eccezione che richiede l'arresto dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="cafcf-118">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>  
  
 <span data-ttu-id="cafcf-119">Si noti che il blocco `try` racchiude il ciclo `foreach` e non la query stessa,</span><span class="sxs-lookup"><span data-stu-id="cafcf-119">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="cafcf-120">in quanto il ciclo `foreach` è il punto in corrispondenza del quale la query viene effettivamente eseguita.</span><span class="sxs-lookup"><span data-stu-id="cafcf-120">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="cafcf-121">Per altre informazioni, vedere [Introduzione alle query LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="cafcf-121">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="cafcf-122">[!code-cs[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="cafcf-122">[!code-cs[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="cafcf-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cafcf-123">See Also</span></span>  
 [<span data-ttu-id="cafcf-124">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="cafcf-124">LINQ query expressions</span></span>](index.md)


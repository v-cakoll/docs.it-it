---
title: Gestire le eccezioni nelle espressioni di query
description: Come gestire le eccezioni nelle espressioni di query.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 376bd461bfeb51653471fd374a2215aa15872976
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="af803-104">Gestire le eccezioni nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="af803-104">Handle exceptions in query expressions</span></span>

<span data-ttu-id="af803-105">Nel contesto di un'espressione di query è possibile chiamare qualsiasi metodo.</span><span class="sxs-lookup"><span data-stu-id="af803-105">It is possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="af803-106">È tuttavia consigliabile non chiamare in un'espressione di query i metodi che possono creare un effetto collaterale, ad esempio la modifica del contenuto dell'origine dati o la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="af803-106">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="af803-107">In questo esempio viene illustrato come evitare di generare eccezioni quando si chiamano i metodi in un'espressione di query senza violare le linee guida generali di .NET Framework sulla gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="af803-107">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET Framework guidelines on exception handling.</span></span> <span data-ttu-id="af803-108">Tali linee guida stabiliscono che è accettabile intercettare un'eccezione specifica quando è evidente il motivo per cui verrà generata in un contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="af803-108">Those guidelines state that it is acceptable to catch a specific exception when you understand why it will be thrown in a given context.</span></span> <span data-ttu-id="af803-109">Per altre informazioni, vedere [Suggerimenti per le eccezioni](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="af803-109">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>  
  
 <span data-ttu-id="af803-110">Nell'esempio finale viene illustrato come gestire quei casi in cui è necessario generare un'eccezione durante l'esecuzione di una query.</span><span class="sxs-lookup"><span data-stu-id="af803-110">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af803-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="af803-111">Example</span></span>  

 <span data-ttu-id="af803-112">Nell'esempio seguente viene illustrato come spostare codice di gestione dell'eccezione al di fuori di un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="af803-112">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="af803-113">Questa operazione è possibile solo quando il metodo non dipende da variabili locali per la query.</span><span class="sxs-lookup"><span data-stu-id="af803-113">This is only possible when the method does not depend on any variables local to the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="af803-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="af803-114">Example</span></span> 

 <span data-ttu-id="af803-115">In alcuni casi la migliore risposta a un'eccezione generata all'interno di una query potrebbe essere l'arresto immediato dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="af803-115">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="af803-116">Nell'esempio seguente viene illustrato come gestire le eccezioni che potrebbero essere generate all'interno del corpo di una query.</span><span class="sxs-lookup"><span data-stu-id="af803-116">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="af803-117">Si supponga che `SomeMethodThatMightThrow` possa potenzialmente generare un'eccezione che richiede l'arresto dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="af803-117">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>  
  
 <span data-ttu-id="af803-118">Si noti che il blocco `try` racchiude il ciclo `foreach` e non la query stessa,</span><span class="sxs-lookup"><span data-stu-id="af803-118">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="af803-119">in quanto il ciclo `foreach` è il punto in corrispondenza del quale la query viene effettivamente eseguita.</span><span class="sxs-lookup"><span data-stu-id="af803-119">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="af803-120">Per altre informazioni, vedere [Introduzione alle query LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="af803-120">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!code-csharp[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]  
  

## <a name="see-also"></a><span data-ttu-id="af803-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af803-121">See Also</span></span>  
 [<span data-ttu-id="af803-122">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="af803-122">LINQ query expressions</span></span>](index.md)

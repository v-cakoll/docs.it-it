---
title: Gestire le eccezioni nelle espressioni di query (LINQ in C#)
description: Informazioni su come gestire le eccezioni nelle espressioni di query LINQ in C#.
ms.date: 12/01/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: f900669412026e69598d3939c51ff8208b51b7ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688501"
---
# <a name="handle-exceptions-in-query-expressions"></a><span data-ttu-id="dc3d5-103">Gestire le eccezioni nelle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="dc3d5-103">Handle exceptions in query expressions</span></span>

<span data-ttu-id="dc3d5-104">Nel contesto di un'espressione di query è possibile chiamare qualsiasi metodo.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-104">It's possible to call any method in the context of a query expression.</span></span> <span data-ttu-id="dc3d5-105">È tuttavia consigliabile non chiamare in un'espressione di query i metodi che possono creare un effetto collaterale, ad esempio la modifica del contenuto dell'origine dati o la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-105">However, we recommend that you avoid calling any method in a query expression that can create a side effect such as modifying the contents of the data source or throwing an exception.</span></span> <span data-ttu-id="dc3d5-106">Questo esempio illustra come evitare di generare eccezioni quando si chiamano i metodi in un'espressione di query senza violare le linee guida generali di .NET sulla gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-106">This example shows how to avoid raising exceptions when you call methods in a query expression without violating the general .NET guidelines on exception handling.</span></span> <span data-ttu-id="dc3d5-107">Tali linee guida stabiliscono che è accettabile intercettare un'eccezione specifica quando è evidente il motivo per cui viene generata in un contesto specificato.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-107">Those guidelines state that it's acceptable to catch a specific exception when you understand why it's thrown in a given context.</span></span> <span data-ttu-id="dc3d5-108">Per altre informazioni, vedere [Suggerimenti per le eccezioni](../../standard/exceptions/best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="dc3d5-108">For more information, see [Best Practices for Exceptions](../../standard/exceptions/best-practices-for-exceptions.md).</span></span>

<span data-ttu-id="dc3d5-109">Nell'esempio finale viene illustrato come gestire quei casi in cui è necessario generare un'eccezione durante l'esecuzione di una query.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-109">The final example shows how to handle those cases when you must throw an exception during execution of a query.</span></span>

## <a name="example"></a><span data-ttu-id="dc3d5-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc3d5-110">Example</span></span>

<span data-ttu-id="dc3d5-111">Nell'esempio seguente viene illustrato come spostare codice di gestione dell'eccezione al di fuori di un'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-111">The following example shows how to move exception handling code outside a query expression.</span></span> <span data-ttu-id="dc3d5-112">Questa operazione è possibile solo quando il metodo non dipende da variabili locali per la query.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-112">This is only possible when the method does not depend on any variables local to the query.</span></span>

[!code-csharp[csProgGuideLINQ#10](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]

## <a name="example"></a><span data-ttu-id="dc3d5-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="dc3d5-113">Example</span></span>

<span data-ttu-id="dc3d5-114">In alcuni casi la migliore risposta a un'eccezione generata all'interno di una query potrebbe essere l'arresto immediato dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-114">In some cases, the best response to an exception that is thrown from within a query might be to stop the query execution immediately.</span></span> <span data-ttu-id="dc3d5-115">Nell'esempio seguente viene illustrato come gestire le eccezioni che potrebbero essere generate all'interno del corpo di una query.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-115">The following example shows how to handle exceptions that might be thrown from inside a query body.</span></span> <span data-ttu-id="dc3d5-116">Si supponga che `SomeMethodThatMightThrow` possa potenzialmente generare un'eccezione che richiede l'arresto dell'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-116">Assume that `SomeMethodThatMightThrow` can potentially cause an exception that requires the query execution to stop.</span></span>

<span data-ttu-id="dc3d5-117">Si noti che il blocco `try` racchiude il ciclo `foreach` e non la query stessa,</span><span class="sxs-lookup"><span data-stu-id="dc3d5-117">Note that the `try` block encloses the `foreach` loop, and not the query itself.</span></span> <span data-ttu-id="dc3d5-118">in quanto il ciclo `foreach` è il punto in corrispondenza del quale la query viene effettivamente eseguita.</span><span class="sxs-lookup"><span data-stu-id="dc3d5-118">This is because the `foreach` loop is the point at which the query is actually executed.</span></span> <span data-ttu-id="dc3d5-119">Per altre informazioni, vedere [Introduzione alle query LINQ](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="dc3d5-119">For more information, see [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

[!code-csharp[csProgGuideLINQ#12](~/samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]

## <a name="see-also"></a><span data-ttu-id="dc3d5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc3d5-120">See also</span></span>

- [<span data-ttu-id="dc3d5-121">Language Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="dc3d5-121">Language Integrated Query (LINQ)</span></span>](index.md)

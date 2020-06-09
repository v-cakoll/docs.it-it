---
title: 'Procedura: Usare Parallel.Invoke per eseguire operazioni parallele'
description: Vedere come usare il metodo Parallel. Invoke nella Task Parallel Library (TPL), che esegue operazioni parallele su un'origine dati condivisa in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: 084ade48b1406d23a11eb311739525f35ac973df
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596345"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="aa49e-103">Procedura: Usare Parallel.Invoke per eseguire operazioni parallele</span><span class="sxs-lookup"><span data-stu-id="aa49e-103">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>

<span data-ttu-id="aa49e-104">Questo esempio mostra come parallelizzare le operazioni usando <xref:System.Threading.Tasks.Parallel.Invoke%2A> in Task Parallel Library.</span><span class="sxs-lookup"><span data-stu-id="aa49e-104">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="aa49e-105">Vengono eseguite tre operazioni in un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="aa49e-105">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="aa49e-106">Le operazioni possono essere eseguite in parallelo in modo semplice, perché nessuna modifica l'origine.</span><span class="sxs-lookup"><span data-stu-id="aa49e-106">The operations can be executed in parallel in a straightforward manner, because none of them modifies the source.</span></span>

> [!NOTE]
> <span data-ttu-id="aa49e-107">Questa documentazione usa espressioni lambda per definire delegati in TPL.</span><span class="sxs-lookup"><span data-stu-id="aa49e-107">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="aa49e-108">Se non si ha familiarità con le espressioni lambda in C# o Visual Basic, vedere [espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="aa49e-108">If you aren't familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="aa49e-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa49e-109">Example</span></span>

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

<span data-ttu-id="aa49e-110">Con <xref:System.Threading.Tasks.Parallel.Invoke%2A> , è sufficiente esprimere le azioni che si desidera eseguire simultaneamente e il runtime gestisce tutti i dettagli di pianificazione dei thread, inclusa la scalabilità automatica al numero di core nel computer host.</span><span class="sxs-lookup"><span data-stu-id="aa49e-110">With <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>

<span data-ttu-id="aa49e-111">Questo esempio parallelizza le operazioni, ma non i dati.</span><span class="sxs-lookup"><span data-stu-id="aa49e-111">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="aa49e-112">Come approccio alternativo, è possibile parallelizzare le query LINQ usando PLINQ ed eseguire le query in sequenza.</span><span class="sxs-lookup"><span data-stu-id="aa49e-112">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="aa49e-113">In alternativa, è possibile parallelizzare i dati usando PLINQ.</span><span class="sxs-lookup"><span data-stu-id="aa49e-113">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="aa49e-114">Un'altra possibilità consiste nel parallelizzare sia le query che le attività.</span><span class="sxs-lookup"><span data-stu-id="aa49e-114">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="aa49e-115">Anche se il sovraccarico risultante potrebbe compromettere le prestazioni nei computer host con un numero relativamente basso di processori, la scalabilità è migliore nei computer con molti processori.</span><span class="sxs-lookup"><span data-stu-id="aa49e-115">Although the resulting overhead might degrade performance on host computers with relatively few processors, it scales better on computers with many processors.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="aa49e-116">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="aa49e-116">Compile the Code</span></span>

<span data-ttu-id="aa49e-117">Copiare e incollare l'esempio completo in un progetto di Microsoft Visual Studio e premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="aa49e-117">Copy and paste the entire example into a Microsoft Visual Studio project and press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa49e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa49e-118">See also</span></span>

- [<span data-ttu-id="aa49e-119">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="aa49e-119">Parallel Programming</span></span>](index.md)
- [<span data-ttu-id="aa49e-120">Procedura: Annullare un'attività e i relativi figli</span><span class="sxs-lookup"><span data-stu-id="aa49e-120">How to: Cancel a Task and Its Children</span></span>](how-to-cancel-a-task-and-its-children.md)
- [<span data-ttu-id="aa49e-121">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="aa49e-121">Parallel LINQ (PLINQ)</span></span>](introduction-to-plinq.md)

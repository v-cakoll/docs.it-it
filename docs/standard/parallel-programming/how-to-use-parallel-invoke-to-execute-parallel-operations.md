---
title: 'Procedura: utilizzare Parallel.Invoke per eseguire operazioni in parallelo'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- task parallelism in .NET
- parallel programming, task parallelism
ms.assetid: 6b3ecd79-dec9-4ce1-abf4-62e5392a59c6
ms.openlocfilehash: f61bbf10bbeef736f66710f50e621c3619355a1d
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635794"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a><span data-ttu-id="09fe2-102">Procedura: utilizzare Parallel.Invoke per eseguire operazioni in parallelo</span><span class="sxs-lookup"><span data-stu-id="09fe2-102">How to: Use Parallel.Invoke to Execute Parallel Operations</span></span>

<span data-ttu-id="09fe2-103">Questo esempio mostra come parallelizzare le operazioni usando <xref:System.Threading.Tasks.Parallel.Invoke%2A> in Task Parallel Library.</span><span class="sxs-lookup"><span data-stu-id="09fe2-103">This example shows how to parallelize operations by using <xref:System.Threading.Tasks.Parallel.Invoke%2A> in the Task Parallel Library.</span></span> <span data-ttu-id="09fe2-104">Vengono eseguite tre operazioni in un'origine dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="09fe2-104">Three operations are performed on a shared data source.</span></span> <span data-ttu-id="09fe2-105">Le operazioni possono essere eseguite in parallelo in modo semplice, perché nessuna di esse modifica l'origine.</span><span class="sxs-lookup"><span data-stu-id="09fe2-105">The operations can be executed in parallel in a straightforward manner, because none of them modifies the source.</span></span>

> [!NOTE]
> <span data-ttu-id="09fe2-106">Questa documentazione usa espressioni lambda per definire delegati in TPL.</span><span class="sxs-lookup"><span data-stu-id="09fe2-106">This documentation uses lambda expressions to define delegates in TPL.</span></span> <span data-ttu-id="09fe2-107">Se non si ha familiarità con le espressioni lambda in Visual Basic o in Visual Basic, vedere [Espressioni lambda in PLINQ e TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="09fe2-107">If you aren't familiar with lambda expressions in C# or Visual Basic, see [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="09fe2-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="09fe2-108">Example</span></span>

[!code-csharp[TPL_Parallel#06](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/parallelinvoke.cs#06)]
[!code-vb[TPL_Parallel#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/parallelinvoke.vb#06)]

<span data-ttu-id="09fe2-109">Con <xref:System.Threading.Tasks.Parallel.Invoke%2A>, è sufficiente esprimere le azioni che si desidera eseguire contemporaneamente e il runtime gestisce tutti i dettagli di pianificazione dei thread, incluso il ridimensionamento automatico in base al numero di core nel computer host.</span><span class="sxs-lookup"><span data-stu-id="09fe2-109">With <xref:System.Threading.Tasks.Parallel.Invoke%2A>, you simply express which actions you want to run concurrently, and the runtime handles all thread scheduling details, including scaling automatically to the number of cores on the host computer.</span></span>

<span data-ttu-id="09fe2-110">Questo esempio parallelizza le operazioni, ma non i dati.</span><span class="sxs-lookup"><span data-stu-id="09fe2-110">This example parallelizes the operations, not the data.</span></span> <span data-ttu-id="09fe2-111">Come approccio alternativo, è possibile parallelizzare le query LINQ usando PLINQ ed eseguire le query in sequenza.</span><span class="sxs-lookup"><span data-stu-id="09fe2-111">As an alternate approach, you can parallelize the LINQ queries by using PLINQ and run the queries sequentially.</span></span> <span data-ttu-id="09fe2-112">In alternativa, è possibile parallelizzare i dati usando PLINQ.</span><span class="sxs-lookup"><span data-stu-id="09fe2-112">Alternatively, you could parallelize the data by using PLINQ.</span></span> <span data-ttu-id="09fe2-113">Un'altra possibilità consiste nel parallelizzare sia le query che le attività.</span><span class="sxs-lookup"><span data-stu-id="09fe2-113">Another option is to parallelize both the queries and the tasks.</span></span> <span data-ttu-id="09fe2-114">Anche se l'overhead risultante potrebbe ridurre le prestazioni nei computer host con relativamente pochi processori, è scalabile meglio su computer con molti processori.</span><span class="sxs-lookup"><span data-stu-id="09fe2-114">Although the resulting overhead might degrade performance on host computers with relatively few processors, it scales better on computers with many processors.</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="09fe2-115">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="09fe2-115">Compile the Code</span></span>

<span data-ttu-id="09fe2-116">Copiare e incollare l'esempio completo in un progetto di Microsoft Visual Studio e premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="09fe2-116">Copy and paste the entire example into a Microsoft Visual Studio project and press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="09fe2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09fe2-117">See also</span></span>

- [<span data-ttu-id="09fe2-118">Programmazione parallela</span><span class="sxs-lookup"><span data-stu-id="09fe2-118">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="09fe2-119">Procedura: annullare un'attività e i relativi figli</span><span class="sxs-lookup"><span data-stu-id="09fe2-119">How to: Cancel a Task and Its Children</span></span>](../../../docs/standard/parallel-programming/how-to-cancel-a-task-and-its-children.md)
- [<span data-ttu-id="09fe2-120">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="09fe2-120">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/introduction-to-plinq.md)

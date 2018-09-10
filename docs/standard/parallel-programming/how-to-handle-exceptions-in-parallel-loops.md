---
title: 'Procedura: gestire le eccezioni nei cicli paralleli'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddf311ad2b79e615f5c3097686035e7bbfbc49c9
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185139"
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="d42a4-102">Procedura: gestire le eccezioni nei cicli paralleli</span><span class="sxs-lookup"><span data-stu-id="d42a4-102">How to: Handle Exceptions in Parallel Loops</span></span>
<span data-ttu-id="d42a4-103">Gli overload dei metodi <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> non presentano alcun meccanismo speciale per gestire le eccezioni eventualmente generate.</span><span class="sxs-lookup"><span data-stu-id="d42a4-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="d42a4-104">Sotto questo aspetto assomigliano ai cicli `for` e `foreach` (`For` e `For Each`in Visual Basic) normali; un'eccezione non gestita fa sì che il ciclo termini immediatamente.</span><span class="sxs-lookup"><span data-stu-id="d42a4-104">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate immediately.</span></span>  
  
 <span data-ttu-id="d42a4-105">Quando si aggiunge una logica personalizzata di gestione delle eccezioni nei cicli paralleli, gestire il caso della generazione simultanea di eccezioni simili in più thread e il caso in cui un'eccezione generata in un determinato thread comporta la generazione di un'altra eccezione in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="d42a4-105">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="d42a4-106">Per gestire entrambi questi casi è possibile eseguire il wrapping di tutte le eccezioni del ciclo in un oggetto <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d42a4-106">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d42a4-107">L'esempio seguente mostra uno degli approcci possibili.</span><span class="sxs-lookup"><span data-stu-id="d42a4-107">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d42a4-108">Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente".</span><span class="sxs-lookup"><span data-stu-id="d42a4-108">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="d42a4-109">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="d42a4-109">This error is benign.</span></span> <span data-ttu-id="d42a4-110">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d42a4-110">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="d42a4-111">Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.</span><span class="sxs-lookup"><span data-stu-id="d42a4-111">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d42a4-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="d42a4-112">Example</span></span>  
 <span data-ttu-id="d42a4-113">In questo esempio vengono rilevate tutte le eccezioni e quindi ne viene eseguito il wrapping in un oggetto <xref:System.AggregateException?displayProperty=nameWithType> che viene generato.</span><span class="sxs-lookup"><span data-stu-id="d42a4-113">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="d42a4-114">Il chiamante può decidere quali eccezioni gestire.</span><span class="sxs-lookup"><span data-stu-id="d42a4-114">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="d42a4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d42a4-115">See also</span></span>

- [<span data-ttu-id="d42a4-116">Parallelismo dei dati</span><span class="sxs-lookup"><span data-stu-id="d42a4-116">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
- [<span data-ttu-id="d42a4-117">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="d42a4-117">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)

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
ms.openlocfilehash: 5d108937e6ab2483cd1633d4b398c1e250f5c098
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77453013"
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a><span data-ttu-id="3f77f-102">Procedura: gestire le eccezioni nei cicli paralleli</span><span class="sxs-lookup"><span data-stu-id="3f77f-102">How to: Handle Exceptions in Parallel Loops</span></span>
<span data-ttu-id="3f77f-103">Gli overload dei metodi <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> non presentano alcun meccanismo speciale per gestire le eccezioni eventualmente generate.</span><span class="sxs-lookup"><span data-stu-id="3f77f-103">The <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> and <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> overloads do not have any special mechanism to handle exceptions that might be thrown.</span></span> <span data-ttu-id="3f77f-104">A questo proposito, `for` `foreach` assomigliano`For` ai cicli e regolari ( e `For Each` in Visual Basic); un'eccezione non gestita fa sì che il ciclo termini non appena tutte le iterazioni attualmente in esecuzione terminano.</span><span class="sxs-lookup"><span data-stu-id="3f77f-104">In this respect, they resemble regular `for` and `foreach` loops (`For` and `For Each` in Visual Basic); an unhandled exception causes the loop to terminate as soon as all currently running iterations finish.</span></span>
  
 <span data-ttu-id="3f77f-105">Quando si aggiunge una logica personalizzata di gestione delle eccezioni nei cicli paralleli, gestire il caso della generazione simultanea di eccezioni simili in più thread e il caso in cui un'eccezione generata in un determinato thread comporta la generazione di un'altra eccezione in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="3f77f-105">When you add your own exception-handling logic to parallel loops, handle the case in which similar exceptions might be thrown on multiple threads concurrently, and the case in which an exception thrown on one thread causes another exception to be thrown on another thread.</span></span> <span data-ttu-id="3f77f-106">Per gestire entrambi questi casi è possibile eseguire il wrapping di tutte le eccezioni del ciclo in un oggetto <xref:System.AggregateException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3f77f-106">You can handle both cases by wrapping all exceptions from the loop in a <xref:System.AggregateException?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3f77f-107">L'esempio seguente mostra uno degli approcci possibili.</span><span class="sxs-lookup"><span data-stu-id="3f77f-107">The following example shows one possible approach.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f77f-108">Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente".</span><span class="sxs-lookup"><span data-stu-id="3f77f-108">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="3f77f-109">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="3f77f-109">This error is benign.</span></span> <span data-ttu-id="3f77f-110">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3f77f-110">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the example below.</span></span> <span data-ttu-id="3f77f-111">Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.</span><span class="sxs-lookup"><span data-stu-id="3f77f-111">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f77f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f77f-112">Example</span></span>  
 <span data-ttu-id="3f77f-113">In questo esempio vengono rilevate tutte le eccezioni e quindi ne viene eseguito il wrapping in un oggetto <xref:System.AggregateException?displayProperty=nameWithType> che viene generato.</span><span class="sxs-lookup"><span data-stu-id="3f77f-113">In this example, all exceptions are caught and then wrapped in an <xref:System.AggregateException?displayProperty=nameWithType> which is thrown.</span></span> <span data-ttu-id="3f77f-114">Il chiamante può decidere quali eccezioni gestire.</span><span class="sxs-lookup"><span data-stu-id="3f77f-114">The caller can decide which exceptions to handle.</span></span>  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="3f77f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f77f-115">See also</span></span>

- [<span data-ttu-id="3f77f-116">Parallelismo dei dati</span><span class="sxs-lookup"><span data-stu-id="3f77f-116">Data Parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="3f77f-117">Espressioni lambda in PLINQ e TPL</span><span class="sxs-lookup"><span data-stu-id="3f77f-117">Lambda Expressions in PLINQ and TPL</span></span>](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)

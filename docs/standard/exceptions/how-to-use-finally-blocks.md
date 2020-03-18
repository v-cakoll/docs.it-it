---
title: 'Procedura: utilizzare blocchi Finally'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
ms.openlocfilehash: 44fbb53437c4c8f19a424227a167e2e268b77057
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708832"
---
# <a name="how-to-use-finally-blocks"></a><span data-ttu-id="8deaf-102">Come usare i blocchi finally</span><span class="sxs-lookup"><span data-stu-id="8deaf-102">How to use finally blocks</span></span>

<span data-ttu-id="8deaf-103">Quando si verifica un'eccezione, l'esecuzione viene arrestata e il controllo viene assegnato al gestore di eccezioni appropriato.</span><span class="sxs-lookup"><span data-stu-id="8deaf-103">When an exception occurs, execution stops and control is given to the appropriate exception handler.</span></span> <span data-ttu-id="8deaf-104">Spesso questo significa che le righe di codice che si prevede di eseguire vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="8deaf-104">This often means that lines of code you expect to be executed are bypassed.</span></span> <span data-ttu-id="8deaf-105">La pulizia di alcune risorse, ad esempio la chiusura di un file, deve essere eseguita anche se viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8deaf-105">Some resource cleanup, such as closing a file, needs to be done even if an exception is thrown.</span></span> <span data-ttu-id="8deaf-106">A tale scopo è possibile usare un blocco `finally`.</span><span class="sxs-lookup"><span data-stu-id="8deaf-106">To do this, you can use a `finally` block.</span></span> <span data-ttu-id="8deaf-107">Un blocco `finally` viene sempre eseguito, indipendentemente dalla generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="8deaf-107">A `finally` block always executes, regardless of whether an exception is thrown.</span></span>

<span data-ttu-id="8deaf-108">L'esempio di codice seguente usa un blocco `try`/`catch` per rilevare <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="8deaf-108">The following code example uses a `try`/`catch` block to catch an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="8deaf-109">Il metodo `Main` crea due matrici e tenta di copiarle una sull'altra.</span><span class="sxs-lookup"><span data-stu-id="8deaf-109">The `Main` method creates two arrays and attempts to copy one to the other.</span></span> <span data-ttu-id="8deaf-110">L'azione genera un'eccezione <xref:System.ArgumentOutOfRangeException> e l'errore viene scritto nella console.</span><span class="sxs-lookup"><span data-stu-id="8deaf-110">The action generates an <xref:System.ArgumentOutOfRangeException> and the error is written to the console.</span></span> <span data-ttu-id="8deaf-111">Il blocco `finally` viene eseguito indipendentemente dal risultato dell'azione di copia.</span><span class="sxs-lookup"><span data-stu-id="8deaf-111">The `finally` block executes regardless of the outcome of the copy action.</span></span>

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="8deaf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8deaf-112">See also</span></span>

- [<span data-ttu-id="8deaf-113">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="8deaf-113">Exceptions</span></span>](index.md)

---
title: "Procedura: implementare un form che utilizza un'operazione in background"
description: Informazioni su come implementare un Windows Form che usa un'operazione in background in modo che un'operazione possa continuare a essere eseguita mentre un'altra operazione continua.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- components [Windows Forms], asynchronous
- forms [Windows Forms], background operations
- background threads
- threading [Windows Forms], background operations
- background operations
ms.assetid: 9f483f93-1613-4be1-a021-b4934e9c78f3
ms.openlocfilehash: 23bf4bc02fbf998d92dfce6d84e4e337cbefe7d9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174523"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="5e3c0-103">Procedura: implementare un form che utilizza un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="5e3c0-103">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="5e3c0-104">Nell'esempio di codice riportato di seguito viene creato un form che calcola numeri di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-104">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="5e3c0-105">Il calcolo viene eseguito su un thread separato da quello dell'interfaccia utente, in modo che la risposta dell'interfaccia utente non venga ritardata dall'esecuzione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-105">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="5e3c0-106">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-106">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="5e3c0-107">Vedere anche [Procedura dettagliata: implementazione di un modulo che usa un'operazione in background](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="5e3c0-107">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e3c0-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="5e3c0-108">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5e3c0-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="5e3c0-109">Compiling the Code</span></span>  
 <span data-ttu-id="5e3c0-110">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e3c0-110">This example requires:</span></span>  
  
- <span data-ttu-id="5e3c0-111">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-111">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="5e3c0-112">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="5e3c0-112">Robust Programming</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="5e3c0-113">L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-113">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="5e3c0-114">Vedere [Procedure consigliate per l'uso del threading gestito](../../../standard/threading/managed-threading-best-practices.md) prima di implementare soluzioni che usano il multithreading.</span><span class="sxs-lookup"><span data-stu-id="5e3c0-114">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3c0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e3c0-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="5e3c0-116">Cenni preliminari sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="5e3c0-116">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="5e3c0-117">Procedure consigliate per il threading gestito</span><span class="sxs-lookup"><span data-stu-id="5e3c0-117">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)

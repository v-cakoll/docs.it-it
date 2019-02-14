---
title: "Procedura: Implementare un Form che usa un'operazione in Background"
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
ms.openlocfilehash: 9ace37b1c79ff2e5cd06fce08557dc6cdf2fcc11
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261307"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="384c2-102">Procedura: Implementare un Form che usa un'operazione in Background</span><span class="sxs-lookup"><span data-stu-id="384c2-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="384c2-103">Nell'esempio di codice riportato di seguito viene creato un form che calcola numeri di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="384c2-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="384c2-104">Il calcolo viene eseguito su un thread separato da quello dell'interfaccia utente, in modo che la risposta dell'interfaccia utente non venga ritardata dall'esecuzione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="384c2-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="384c2-105">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="384c2-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="384c2-106">Vedere anche [procedura dettagliata: Implementazione di un Form che usa un'operazione in Background](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span><span class="sxs-lookup"><span data-stu-id="384c2-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="384c2-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="384c2-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="384c2-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="384c2-108">Compiling the Code</span></span>  
 <span data-ttu-id="384c2-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="384c2-109">This example requires:</span></span>  
  
-   <span data-ttu-id="384c2-110">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="384c2-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="384c2-111">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="384c2-111">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="384c2-112">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="384c2-112">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="384c2-113">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="384c2-113">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="384c2-114">L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi.</span><span class="sxs-lookup"><span data-stu-id="384c2-114">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="384c2-115">Vedere [Procedure consigliate per l'uso del threading gestito](../../../../docs/standard/threading/managed-threading-best-practices.md) prima di implementare soluzioni che usano il multithreading.</span><span class="sxs-lookup"><span data-stu-id="384c2-115">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384c2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="384c2-116">See also</span></span>
- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="384c2-117">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="384c2-117">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="384c2-118">Suggerimenti per l'utilizzo del threading gestito</span><span class="sxs-lookup"><span data-stu-id="384c2-118">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)

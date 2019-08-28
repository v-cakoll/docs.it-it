---
title: "Procedura: Implementare un modulo che usa un'operazione in background"
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
ms.openlocfilehash: e06b18558f6b3fa3cef47613bbaef16fb7c740f0
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046197"
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="9b779-102">Procedura: Implementare un modulo che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="9b779-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="9b779-103">Nell'esempio di codice riportato di seguito viene creato un form che calcola numeri di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="9b779-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="9b779-104">Il calcolo viene eseguito su un thread separato da quello dell'interfaccia utente, in modo che la risposta dell'interfaccia utente non venga ritardata dall'esecuzione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="9b779-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="9b779-105">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="9b779-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="9b779-106">Vedere [anche procedura dettagliata: Implementazione di un form che utilizza un'operazione](walkthrough-implementing-a-form-that-uses-a-background-operation.md)in background.</span><span class="sxs-lookup"><span data-stu-id="9b779-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](walkthrough-implementing-a-form-that-uses-a-background-operation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b779-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b779-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b779-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9b779-108">Compiling the Code</span></span>  
 <span data-ttu-id="9b779-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b779-109">This example requires:</span></span>  
  
- <span data-ttu-id="9b779-110">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9b779-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9b779-111">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="9b779-111">Robust Programming</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="9b779-112">L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi.</span><span class="sxs-lookup"><span data-stu-id="9b779-112">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="9b779-113">Vedere [Procedure consigliate per l'uso del threading gestito](../../../standard/threading/managed-threading-best-practices.md) prima di implementare soluzioni che usano il multithreading.</span><span class="sxs-lookup"><span data-stu-id="9b779-113">Consult the [Managed Threading Best Practices](../../../standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b779-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b779-114">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="9b779-115">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="9b779-115">Event-based Asynchronous Pattern Overview</span></span>](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
- [<span data-ttu-id="9b779-116">Suggerimenti per l'utilizzo del threading gestito</span><span class="sxs-lookup"><span data-stu-id="9b779-116">Managed Threading Best Practices</span></span>](../../../standard/threading/managed-threading-best-practices.md)

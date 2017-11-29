---
title: 'Procedura: implementare un form che utilizza un''operazione in background'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a519f1611e419ec439a70ec86f457049582c4ceb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-form-that-uses-a-background-operation"></a><span data-ttu-id="eeeda-102">Procedura: implementare un form che utilizza un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="eeeda-102">How to: Implement a Form That Uses a Background Operation</span></span>
<span data-ttu-id="eeeda-103">Nell'esempio di codice riportato di seguito viene creato un form che calcola numeri di Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="eeeda-103">The following example program creates a form that calculates Fibonacci numbers.</span></span> <span data-ttu-id="eeeda-104">Il calcolo viene eseguito su un thread separato da quello dell'interfaccia utente, in modo che la risposta dell'interfaccia utente non venga ritardata dall'esecuzione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="eeeda-104">The calculation runs on a thread that is separate from the user interface thread, so the user interface continues to run without delays as the calculation proceeds.</span></span>  
  
 <span data-ttu-id="eeeda-105">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="eeeda-105">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="eeeda-106">Vedere anche [Procedura dettagliata: implementazione di un modulo che usa un'operazione in background](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="eeeda-106">Also see [Walkthrough: Implementing a Form That Uses a Background Operation](http://msdn.microsoft.com/library/b2zk6580\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eeeda-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="eeeda-107">Example</span></span>  
 [!code-cpp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#1)]
 [!code-csharp[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eeeda-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="eeeda-108">Compiling the Code</span></span>  
 <span data-ttu-id="eeeda-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="eeeda-109">This example requires:</span></span>  
  
-   <span data-ttu-id="eeeda-110">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="eeeda-110">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="eeeda-111">Per informazioni sulla compilazione di questo esempio dalla riga di comando per [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], vedere [Compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilazione dalla riga di comando con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="eeeda-111">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="eeeda-112">È anche possibile compilare questo esempio in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="eeeda-112">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="eeeda-113">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo tramite Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="eeeda-113">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="eeeda-114">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="eeeda-114">Robust Programming</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="eeeda-115">L'uso di qualsiasi tipo di multithreading determina la potenziale esposizione a bug seri e complessi.</span><span class="sxs-lookup"><span data-stu-id="eeeda-115">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="eeeda-116">Vedere [Procedure consigliate per l'uso del threading gestito](../../../../docs/standard/threading/managed-threading-best-practices.md) prima di implementare soluzioni che usano il multithreading.</span><span class="sxs-lookup"><span data-stu-id="eeeda-116">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeeda-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eeeda-117">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="eeeda-118">Panoramica sul modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="eeeda-118">Event-based Asynchronous Pattern Overview</span></span>](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 [<span data-ttu-id="eeeda-119">Suggerimenti per l'utilizzo del threading gestito</span><span class="sxs-lookup"><span data-stu-id="eeeda-119">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)

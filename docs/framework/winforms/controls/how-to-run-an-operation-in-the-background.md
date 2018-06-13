---
title: "Procedura: eseguire un'operazione in background"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 5b56e2aa-dc05-444f-930c-2d7b23f9ad5b
ms.openlocfilehash: 7a2ce452a1e55d0b01245c4eb7f43056031b9e2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533913"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="43e53-102">Procedura: eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="43e53-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="43e53-103">Se l'esecuzione di un'operazione richiede molto tempo e si vogliono evitare ritardi nella risposta dell'interfaccia utente, è possibile usare la classe <xref:System.ComponentModel.BackgroundWorker> per eseguire l'operazione in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="43e53-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="43e53-104">L'esempio di codice seguente illustra come eseguire in background un'operazione che richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="43e53-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="43e53-105">Nel form sono presenti i pulsanti **Avvia** e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="43e53-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="43e53-106">Fare clic sul pulsante **Avvia** per eseguire un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="43e53-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="43e53-107">Fare clic sul pulsante **Annulla** per interrompere l'esecuzione dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="43e53-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="43e53-108">Il risultato di ciascuna operazione viene visualizzato in una finestra di messaggio <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="43e53-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="43e53-109">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="43e53-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="43e53-110">Vedere anche [Procedura dettagliata: Esecuzione di un'operazione in background](http://msdn.microsoft.com/library/ms233672\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="43e53-110">Also see [Walkthrough: Running an Operation in the Background](http://msdn.microsoft.com/library/ms233672\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43e53-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="43e53-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="43e53-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="43e53-112">Compiling the Code</span></span>  
 <span data-ttu-id="43e53-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="43e53-113">This example requires:</span></span>  
  
-   <span data-ttu-id="43e53-114">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="43e53-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="43e53-115">Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="43e53-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="43e53-116">È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="43e53-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="43e53-117">Vedere anche [Procedura: Compilare ed eseguire un esempio di codice Windows Form completo con Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="43e53-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43e53-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43e53-118">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.DoWorkEventArgs>  
 [<span data-ttu-id="43e53-119">Procedura: Implementare un form che esegue un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="43e53-119">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="43e53-120">BackgroundWorker (componente)</span><span class="sxs-lookup"><span data-stu-id="43e53-120">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)

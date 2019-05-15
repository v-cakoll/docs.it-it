---
title: "Procedura: Eseguire un'operazione in background"
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
ms.openlocfilehash: 77f75a7eb1d7cc536df7110ef55727fbdf789f23
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591608"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="f57b5-102">Procedura: Eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="f57b5-102">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="f57b5-103">Se l'esecuzione di un'operazione richiede molto tempo e si vogliono evitare ritardi nella risposta dell'interfaccia utente, è possibile usare la classe <xref:System.ComponentModel.BackgroundWorker> per eseguire l'operazione in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="f57b5-103">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="f57b5-104">L'esempio di codice seguente illustra come eseguire in background un'operazione che richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="f57b5-104">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="f57b5-105">Nel form sono presenti i pulsanti **Avvia** e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="f57b5-105">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="f57b5-106">Fare clic sul pulsante **Avvia** per eseguire un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="f57b5-106">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="f57b5-107">Fare clic sul pulsante **Annulla** per interrompere l'esecuzione dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="f57b5-107">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="f57b5-108">Il risultato di ciascuna operazione viene visualizzato in una finestra di messaggio <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="f57b5-108">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="f57b5-109">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="f57b5-109">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="f57b5-110">Vedere anche [procedura dettagliata: Esecuzione di un'operazione in Background](walkthrough-running-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="f57b5-110">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f57b5-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="f57b5-111">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f57b5-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f57b5-112">Compiling the Code</span></span>  
 <span data-ttu-id="f57b5-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f57b5-113">This example requires:</span></span>  
  
- <span data-ttu-id="f57b5-114">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="f57b5-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f57b5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f57b5-115">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="f57b5-116">Procedura: Implementare un modulo che usa un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="f57b5-116">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="f57b5-117">BackgroundWorker (componente)</span><span class="sxs-lookup"><span data-stu-id="f57b5-117">BackgroundWorker Component</span></span>](backgroundworker-component.md)

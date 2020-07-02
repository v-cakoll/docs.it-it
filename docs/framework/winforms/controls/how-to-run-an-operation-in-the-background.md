---
title: "Procedura: eseguire un'operazione in background"
description: Informazioni su come usare la classe BackgroundWorker per eseguire un'operazione di Windows Forms dispendiosa in termini di tempo in background.
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
ms.openlocfilehash: 6b2a97f5acf1e906dfe141aee62e99a4e50dca9f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621574"
---
# <a name="how-to-run-an-operation-in-the-background"></a><span data-ttu-id="85548-103">Procedura: eseguire un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="85548-103">How to: Run an Operation in the Background</span></span>
<span data-ttu-id="85548-104">Se l'esecuzione di un'operazione richiede molto tempo e si vogliono evitare ritardi nella risposta dell'interfaccia utente, è possibile usare la classe <xref:System.ComponentModel.BackgroundWorker> per eseguire l'operazione in un altro thread.</span><span class="sxs-lookup"><span data-stu-id="85548-104">If you have an operation that will take a long time to complete, and you do not want to cause delays in your user interface, you can use the <xref:System.ComponentModel.BackgroundWorker> class to run the operation on another thread.</span></span>  
  
 <span data-ttu-id="85548-105">L'esempio di codice seguente illustra come eseguire in background un'operazione che richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="85548-105">The following code example shows how to run a time-consuming operation in the background.</span></span> <span data-ttu-id="85548-106">Nel form sono presenti i pulsanti **Avvia** e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="85548-106">The form has **Start** and **Cancel** buttons.</span></span> <span data-ttu-id="85548-107">Fare clic sul pulsante **Avvia** per eseguire un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="85548-107">Click the **Start** button to run an asynchronous operation.</span></span> <span data-ttu-id="85548-108">Fare clic sul pulsante **Annulla** per interrompere l'esecuzione dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="85548-108">Click the **Cancel** button to stop a running asynchronous operation.</span></span> <span data-ttu-id="85548-109">Il risultato di ciascuna operazione viene visualizzato in una finestra di messaggio <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="85548-109">The outcome of each operation is displayed in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="85548-110">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="85548-110">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="85548-111">Vedere anche [Procedura dettagliata: Esecuzione di un'operazione in background](walkthrough-running-an-operation-in-the-background.md).</span><span class="sxs-lookup"><span data-stu-id="85548-111">Also see [Walkthrough: Running an Operation in the Background](walkthrough-running-an-operation-in-the-background.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85548-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="85548-112">Example</span></span>  
 [!code-csharp[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.BackgroundWorker.Example#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="85548-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="85548-113">Compiling the Code</span></span>  
 <span data-ttu-id="85548-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="85548-114">This example requires:</span></span>  
  
- <span data-ttu-id="85548-115">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="85548-115">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85548-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85548-116">See also</span></span>

- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [<span data-ttu-id="85548-117">Procedura: implementare un form che utilizza un'operazione in background</span><span class="sxs-lookup"><span data-stu-id="85548-117">How to: Implement a Form That Uses a Background Operation</span></span>](how-to-implement-a-form-that-uses-a-background-operation.md)
- [<span data-ttu-id="85548-118">Componente BackgroundWorker</span><span class="sxs-lookup"><span data-stu-id="85548-118">BackgroundWorker Component</span></span>](backgroundworker-component.md)

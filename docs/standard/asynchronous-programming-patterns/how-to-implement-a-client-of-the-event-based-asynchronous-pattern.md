---
title: 'Procedura: implementare un client del modello asincrono basato su eventi'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b70d4ba205d39ad8fcbc7c7f6fa1f5b34a36c98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-client-of-the-event-based-asynchronous-pattern"></a><span data-ttu-id="f4eed-102">Procedura: implementare un client del modello asincrono basato su eventi</span><span class="sxs-lookup"><span data-stu-id="f4eed-102">How to: Implement a Client of the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="f4eed-103">Esempio di codice seguente viene illustrato come utilizzare un componente che rispetti il [Panoramica del modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4eed-103">The following code example demonstrates how to use a component that adheres to the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span> <span data-ttu-id="f4eed-104">Il form per questo esempio Usa il `PrimeNumberCalculator` componente descritto in [procedura: implementare un componente che supporta il modello asincrono basato su eventi](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span><span class="sxs-lookup"><span data-stu-id="f4eed-104">The form for this example uses the `PrimeNumberCalculator` component described in [How to: Implement a Component That Supports the Event-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).</span></span>  
  
 <span data-ttu-id="f4eed-105">Quando si esegue un progetto che utilizza questo esempio, si verrà visualizzato un form "Calcolatrice di numeri primi" con una griglia e due pulsanti: **Avvia nuova attività** e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="f4eed-105">When you run a project that uses this example, you will see a "Prime Number Calculator" form with a grid and two buttons: **Start New Task** and **Cancel**.</span></span> <span data-ttu-id="f4eed-106">È possibile scegliere di **Avvia nuova attività** più volte in successione e per ogni clic, un'operazione asincrona inizierà a un calcolo per determinare se un numero di test in modo casuale generato è primo.</span><span class="sxs-lookup"><span data-stu-id="f4eed-106">You can click the **Start New Task** button several times in succession, and for each click, an asynchronous operation will begin a computation to determine if a randomly generated test number is prime.</span></span> <span data-ttu-id="f4eed-107">Il modulo verrà visualizzato periodicamente lo stato di avanzamento e risultati incrementali.</span><span class="sxs-lookup"><span data-stu-id="f4eed-107">The form will periodically display progress and incremental results.</span></span> <span data-ttu-id="f4eed-108">Ogni operazione viene assegnato un ID attività univoco.</span><span class="sxs-lookup"><span data-stu-id="f4eed-108">Each operation is assigned a unique task ID.</span></span> <span data-ttu-id="f4eed-109">Il risultato del calcolo viene visualizzato nel **risultato** colonna; se il numero di test non è primo, contrassegnato come **composito,** e viene visualizzato il relativo primo divisore.</span><span class="sxs-lookup"><span data-stu-id="f4eed-109">The result of the computation is displayed in the **Result** column; if the test number is not prime, it is labeled as **Composite,** and its first divisor is displayed.</span></span>  
  
 <span data-ttu-id="f4eed-110">Qualsiasi operazione in sospeso possono essere annullato con la **Annulla** pulsante.</span><span class="sxs-lookup"><span data-stu-id="f4eed-110">Any pending operation can be canceled with the **Cancel** button.</span></span> <span data-ttu-id="f4eed-111">Può essere più selezioni.</span><span class="sxs-lookup"><span data-stu-id="f4eed-111">Multiple selections can be made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4eed-112">Non è la maggior parte dei numeri primi.</span><span class="sxs-lookup"><span data-stu-id="f4eed-112">Most numbers will not be prime.</span></span> <span data-ttu-id="f4eed-113">Se non è stato possibile trovare un numero primo dopo diverse operazioni completate, avviare semplicemente più attività e alla fine si troveranno alcuni numeri primi.</span><span class="sxs-lookup"><span data-stu-id="f4eed-113">If you have not found a prime number after several completed operations, simply start more tasks, and eventually you will find some prime numbers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4eed-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4eed-114">Example</span></span>  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="f4eed-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4eed-115">See Also</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>

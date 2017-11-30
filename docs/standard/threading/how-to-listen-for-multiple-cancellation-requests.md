---
title: "Procedura: Ascolto di più richieste di annullamento"
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
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 36cf338a15ad3f7d234f902c50a2dbb1b2e95847
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a><span data-ttu-id="35613-102">Procedura: Ascolto di più richieste di annullamento</span><span class="sxs-lookup"><span data-stu-id="35613-102">How to: Listen for Multiple Cancellation Requests</span></span>
<span data-ttu-id="35613-103">In questo esempio viene illustrato come contemporaneamente in attesa di due token di annullamento in modo che se uno dei token lo richiede, è possibile annullare un'operazione.</span><span class="sxs-lookup"><span data-stu-id="35613-103">This example shows how to listen to two cancellation tokens simultaneously so that you can cancel an operation if either token requests it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35613-104">Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente".</span><span class="sxs-lookup"><span data-stu-id="35613-104">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="35613-105">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="35613-105">This error is benign.</span></span> <span data-ttu-id="35613-106">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="35613-106">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="35613-107">Per impedire l'interruzione per il primo errore di Visual Studio, deselezionare semplicemente la casella di controllo "Just My Code" **strumenti, opzioni, debug, generale**.</span><span class="sxs-lookup"><span data-stu-id="35613-107">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35613-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="35613-108">Example</span></span>  
 <span data-ttu-id="35613-109">Nell'esempio seguente, il <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> metodo viene utilizzato per unire due token in un token.</span><span class="sxs-lookup"><span data-stu-id="35613-109">In the following example, the <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> method is used to join two tokens into one token.</span></span> <span data-ttu-id="35613-110">In questo modo il token deve essere passato ai metodi che accettano l'annullamento di un solo token come argomento.</span><span class="sxs-lookup"><span data-stu-id="35613-110">This enables the token to be passed to methods that take just one cancellation token as an argument.</span></span> <span data-ttu-id="35613-111">Nell'esempio viene illustrato uno scenario comune in cui un metodo è necessario osservare sia un token passato dall'esterno della classe e un token generato all'interno della classe.</span><span class="sxs-lookup"><span data-stu-id="35613-111">The example demonstrates a common scenario in which a method must observe both a token passed in from outside the class, and a token generated inside the class.</span></span>  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 <span data-ttu-id="35613-112">Quando il token collegato genera un <xref:System.OperationCanceledException>, il token passato all'eccezione è il token collegato, non uno dei token del predecessore.</span><span class="sxs-lookup"><span data-stu-id="35613-112">When the linked token throws an <xref:System.OperationCanceledException>, the token that is passed to the exception is the linked token, not either of the predecessor tokens.</span></span> <span data-ttu-id="35613-113">Per determinare quale dei token è stata annullata, controllare lo stato dei token del predecessore direttamente.</span><span class="sxs-lookup"><span data-stu-id="35613-113">To determine which of the tokens was canceled, check the status of the predecessor tokens directly.</span></span>  
  
 <span data-ttu-id="35613-114">In questo esempio, <xref:System.AggregateException> non deve essere mai generata, ma venga intercettato qui perché in scenari reali eccezione <xref:System.OperationCanceledException> generati da un delegato di attività viene eseguito il wrapping un <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="35613-114">In this example, <xref:System.AggregateException> should never be thrown, but it is caught here because in real-world scenarios any other exceptions besides <xref:System.OperationCanceledException> that are thrown from the task delegate are wrapped in a <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35613-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35613-115">See Also</span></span>  
 [<span data-ttu-id="35613-116">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="35613-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)

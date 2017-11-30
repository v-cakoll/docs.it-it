---
title: 'Procedura: registrare i callback per le richieste di annullamento'
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
helpviewer_keywords: cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 85b15ed610d80958ac9d7e3762ac8ea7b781b8d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-register-callbacks-for-cancellation-requests"></a><span data-ttu-id="3db22-102">Procedura: registrare i callback per le richieste di annullamento</span><span class="sxs-lookup"><span data-stu-id="3db22-102">How to: Register Callbacks for Cancellation Requests</span></span>
<span data-ttu-id="3db22-103">Nell'esempio seguente viene illustrato come registrare un delegato che verrà richiamato quando un <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> proprietà diventa true a causa di una chiamata a <xref:System.Threading.CancellationTokenSource.Cancel%2A> per l'oggetto che ha creato il token.</span><span class="sxs-lookup"><span data-stu-id="3db22-103">The following example shows how to register a delegate that will be invoked when a <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property becomes true due to a call to <xref:System.Threading.CancellationTokenSource.Cancel%2A> on the object that created the token.</span></span> <span data-ttu-id="3db22-104">Usare questa tecnica per annullare le operazioni asincrone che non supportano in modo nativo il framework di annullamento unificato e per sbloccare i metodi che potrebbero essere in attesa del completamento di un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="3db22-104">Use this technique for cancelling asynchronous operations that do not natively support the unified cancellation framework, and for unblocking methods that might be waiting for an asynchronous operation to finish.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3db22-105">Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente".</span><span class="sxs-lookup"><span data-stu-id="3db22-105">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="3db22-106">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="3db22-106">This error is benign.</span></span> <span data-ttu-id="3db22-107">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3db22-107">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="3db22-108">Per impedire l'interruzione per il primo errore di Visual Studio, deselezionare semplicemente la casella di controllo "Just My Code" **strumenti, opzioni, debug, generale**.</span><span class="sxs-lookup"><span data-stu-id="3db22-108">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3db22-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="3db22-109">Example</span></span>  
 <span data-ttu-id="3db22-110">Nell'esempio seguente, il metodo <xref:System.Net.WebClient.CancelAsync%2A> viene registrato come metodo da richiamare quando viene richiesto l'annullamento tramite il token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="3db22-110">In the following example, the <xref:System.Net.WebClient.CancelAsync%2A> method is registered as the method to be invoked when cancellation is requested through the cancellation token.</span></span>  
  
 [!code-csharp[Conceptual.Cancellation.Callback#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs#1)]
 [!code-vb[Conceptual.Cancellation.Callback#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb#1)]  
  
 <span data-ttu-id="3db22-111">Se l'annullamento è già stato richiesto quando il callback viene registrato, è tuttavia garantito che il callback verrà chiamato.</span><span class="sxs-lookup"><span data-stu-id="3db22-111">If cancellation has already been requested when the callback is registered, the callback is still guaranteed to be called.</span></span> <span data-ttu-id="3db22-112">In questo caso particolare, il metodo <xref:System.Net.WebClient.CancelAsync%2A> non eseguirà alcuna operazione se nessuna operazione asincrona è in corso, quindi la chiamata al metodo è sempre sicura.</span><span class="sxs-lookup"><span data-stu-id="3db22-112">In this particular case, the <xref:System.Net.WebClient.CancelAsync%2A> method will do nothing if no asynchronous operation is in progress, so it is always safe to call the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db22-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3db22-113">See Also</span></span>  
 [<span data-ttu-id="3db22-114">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="3db22-114">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)

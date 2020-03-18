---
title: 'Procedura: registrare i callback per le richieste di annullamento'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, how to register callbacks
ms.assetid: 8838dd75-18ed-4b8b-b322-cd4531faac64
ms.openlocfilehash: 87ba1ab9ac095c733a53f766d00ebb7530a8d9c4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137992"
---
# <a name="how-to-register-callbacks-for-cancellation-requests"></a><span data-ttu-id="962d0-102">Procedura: registrare i callback per le richieste di annullamento</span><span class="sxs-lookup"><span data-stu-id="962d0-102">How to: Register Callbacks for Cancellation Requests</span></span>
<span data-ttu-id="962d0-103">L'esempio seguente mostra come registrare un delegato che verrà richiamato quando una proprietà <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> diventa true in seguito a una chiamata a <xref:System.Threading.CancellationTokenSource.Cancel%2A> sull'oggetto che ha creato il token.</span><span class="sxs-lookup"><span data-stu-id="962d0-103">The following example shows how to register a delegate that will be invoked when a <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property becomes true due to a call to <xref:System.Threading.CancellationTokenSource.Cancel%2A> on the object that created the token.</span></span> <span data-ttu-id="962d0-104">Usare questa tecnica per annullare le operazioni asincrone che non supportano in modo nativo il framework di annullamento unificato e per sbloccare i metodi che potrebbero essere in attesa del completamento di un'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="962d0-104">Use this technique for cancelling asynchronous operations that do not natively support the unified cancellation framework, and for unblocking methods that might be waiting for an asynchronous operation to finish.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="962d0-105">Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente".</span><span class="sxs-lookup"><span data-stu-id="962d0-105">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="962d0-106">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="962d0-106">This error is benign.</span></span> <span data-ttu-id="962d0-107">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="962d0-107">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="962d0-108">Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.</span><span class="sxs-lookup"><span data-stu-id="962d0-108">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="962d0-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="962d0-109">Example</span></span>  
 <span data-ttu-id="962d0-110">Nell'esempio seguente, il metodo <xref:System.Net.WebClient.CancelAsync%2A> viene registrato come metodo da richiamare quando viene richiesto l'annullamento tramite il token di annullamento.</span><span class="sxs-lookup"><span data-stu-id="962d0-110">In the following example, the <xref:System.Net.WebClient.CancelAsync%2A> method is registered as the method to be invoked when cancellation is requested through the cancellation token.</span></span>  
  
 [!code-csharp[Conceptual.Cancellation.Callback#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.cancellation.callback/cs/howtoexample1.cs#1)]
 [!code-vb[Conceptual.Cancellation.Callback#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.cancellation.callback/vb/howtoexample1.vb#1)]  
  
 <span data-ttu-id="962d0-111">Se l'annullamento è già stato richiesto quando il callback viene registrato, è tuttavia garantito che il callback verrà chiamato.</span><span class="sxs-lookup"><span data-stu-id="962d0-111">If cancellation has already been requested when the callback is registered, the callback is still guaranteed to be called.</span></span> <span data-ttu-id="962d0-112">In questo caso particolare, il metodo <xref:System.Net.WebClient.CancelAsync%2A> non eseguirà alcuna operazione se nessuna operazione asincrona è in corso, quindi la chiamata al metodo è sempre sicura.</span><span class="sxs-lookup"><span data-stu-id="962d0-112">In this particular case, the <xref:System.Net.WebClient.CancelAsync%2A> method will do nothing if no asynchronous operation is in progress, so it is always safe to call the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="962d0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="962d0-113">See also</span></span>

- [<span data-ttu-id="962d0-114">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="962d0-114">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)

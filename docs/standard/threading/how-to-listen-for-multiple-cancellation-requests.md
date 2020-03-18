---
title: 'Procedura: Ascolto di più richieste di annullamento'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation tokens, joining
- LinkedTokenSource, how to
ms.assetid: 6f4f3804-2ed7-41b4-a97a-6e32b93f6e05
ms.openlocfilehash: e35472040b6ee1263ebc4c4968fa1822045a2064
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138016"
---
# <a name="how-to-listen-for-multiple-cancellation-requests"></a><span data-ttu-id="a2cc9-102">Procedura: Ascolto di più richieste di annullamento</span><span class="sxs-lookup"><span data-stu-id="a2cc9-102">How to: Listen for Multiple Cancellation Requests</span></span>
<span data-ttu-id="a2cc9-103">Questo esempio illustra come essere in ascolto di due token di annullamento contemporaneamente, in modo da annullare un'operazione se uno dei due token lo richiede.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-103">This example shows how to listen to two cancellation tokens simultaneously so that you can cancel an operation if either token requests it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2cc9-104">Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente".</span><span class="sxs-lookup"><span data-stu-id="a2cc9-104">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="a2cc9-105">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-105">This error is benign.</span></span> <span data-ttu-id="a2cc9-106">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-106">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="a2cc9-107">Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-107">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2cc9-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2cc9-108">Example</span></span>  
 <span data-ttu-id="a2cc9-109">Nell'esempio seguente il metodo <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> viene usato per unire due token in un token.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-109">In the following example, the <xref:System.Threading.CancellationTokenSource.CreateLinkedTokenSource%2A> method is used to join two tokens into one token.</span></span> <span data-ttu-id="a2cc9-110">In questo modo, il token può essere passato ai metodi che accettano un solo token di annullamento come argomento.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-110">This enables the token to be passed to methods that take just one cancellation token as an argument.</span></span> <span data-ttu-id="a2cc9-111">L'esempio illustra uno scenario comune in cui un metodo deve rilevare sia un token passato dall'esterno della classe che un token generato all'interno della classe.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-111">The example demonstrates a common scenario in which a method must observe both a token passed in from outside the class, and a token generated inside the class.</span></span>  
  
 [!code-csharp[Cancellation#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex13.cs#13)]
 [!code-vb[Cancellation#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex13.vb#13)]  
  
 <span data-ttu-id="a2cc9-112">Quando il token collegato genera un'eccezione <xref:System.OperationCanceledException>, il token passato all'eccezione è il token collegato, non uno dei token predecessori.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-112">When the linked token throws an <xref:System.OperationCanceledException>, the token that is passed to the exception is the linked token, not either of the predecessor tokens.</span></span> <span data-ttu-id="a2cc9-113">Per determinare quale token è stato annullato, controllare direttamente lo stato dei token predecessori.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-113">To determine which of the tokens was canceled, check the status of the predecessor tokens directly.</span></span>  
  
 <span data-ttu-id="a2cc9-114">In questo esempio l'eccezione <xref:System.AggregateException> non deve essere mai generata, ma qui viene intercettata perché in scenari reali per le eccezioni diverse da <xref:System.OperationCanceledException> generate da un delegato dell'attività viene eseguito il wrapping in un oggetto <xref:System.AggregateException>.</span><span class="sxs-lookup"><span data-stu-id="a2cc9-114">In this example, <xref:System.AggregateException> should never be thrown, but it is caught here because in real-world scenarios any other exceptions besides <xref:System.OperationCanceledException> that are thrown from the task delegate are wrapped in a <xref:System.AggregateException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2cc9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2cc9-115">See also</span></span>

- [<span data-ttu-id="a2cc9-116">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="a2cc9-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)

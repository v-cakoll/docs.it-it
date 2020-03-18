---
title: 'Procedura: mettersi in ascolto di richieste di annullamento con handle di attesa'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
ms.openlocfilehash: 43ca52359a48d3ac5a27933fcc8ce56c07159cac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73137985"
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="33a29-102">Procedura: mettersi in ascolto di richieste di annullamento con handle di attesa</span><span class="sxs-lookup"><span data-stu-id="33a29-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="33a29-103">Se un metodo è bloccato mentre è in attesa che un evento venga segnalato, non può controllare il valore del token di annullamento e rispondere in modo tempestivo.</span><span class="sxs-lookup"><span data-stu-id="33a29-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="33a29-104">Il primo esempio illustra come risolvere questo problema quando si usano eventi come <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> che non supportano in modo nativo il framework di annullamento unificato.</span><span class="sxs-lookup"><span data-stu-id="33a29-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="33a29-105">Il secondo esempio illustra un approccio più semplice che usa <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, che supporta l'annullamento unificato.</span><span class="sxs-lookup"><span data-stu-id="33a29-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33a29-106">Quando "Just My Code" è abilitato, Visual Studio in alcuni casi si interromperà in corrispondenza della riga che genera l'eccezione e visualizzerà un messaggio di errore simile a "Eccezione non gestita dal codice utente".</span><span class="sxs-lookup"><span data-stu-id="33a29-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="33a29-107">Questo errore non è grave.</span><span class="sxs-lookup"><span data-stu-id="33a29-107">This error is benign.</span></span> <span data-ttu-id="33a29-108">È possibile premere F5 per continuare e osservare il comportamento di gestione delle eccezioni illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="33a29-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="33a29-109">Per impedire l'interruzione di Visual Studio al primo errore, deselezionare semplicemente la casella di controllo "Just My Code" in **Strumenti, Opzioni, Debug, Generale**.</span><span class="sxs-lookup"><span data-stu-id="33a29-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33a29-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="33a29-110">Example</span></span>  
 <span data-ttu-id="33a29-111">L'esempio seguente usa un oggetto <xref:System.Threading.ManualResetEvent> per illustrare come sbloccare gli handle di attesa che non supportano l'annullamento unificato.</span><span class="sxs-lookup"><span data-stu-id="33a29-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="33a29-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="33a29-112">Example</span></span>  
 <span data-ttu-id="33a29-113">L'esempio seguente usa un oggetto <xref:System.Threading.ManualResetEventSlim> per illustrare come sbloccare le primitive di coordinamento che supportano l'annullamento unificato.</span><span class="sxs-lookup"><span data-stu-id="33a29-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="33a29-114">Lo stesso approccio può essere usato con altre primitive di coordinamento leggere, ad esempio <xref:System.Threading.Semaphore>`Slim` e <xref:System.Threading.CountdownEvent>.</span><span class="sxs-lookup"><span data-stu-id="33a29-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="33a29-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33a29-115">See also</span></span>

- [<span data-ttu-id="33a29-116">Annullamento in thread gestiti</span><span class="sxs-lookup"><span data-stu-id="33a29-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)

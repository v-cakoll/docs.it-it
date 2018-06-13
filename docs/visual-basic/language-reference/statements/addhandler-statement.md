---
title: Istruzione AddHandler
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: db8131dc82aed40e725c9375efef274fb6917d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603652"
---
# <a name="addhandler-statement"></a><span data-ttu-id="6bda1-102">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="6bda1-102">AddHandler Statement</span></span>
<span data-ttu-id="6bda1-103">Associa un evento al gestore eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6bda1-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bda1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bda1-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="6bda1-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6bda1-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="6bda1-106">Il nome dell'evento da gestire.</span><span class="sxs-lookup"><span data-stu-id="6bda1-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="6bda1-107">Il nome di una routine che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="6bda1-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bda1-108">Note</span><span class="sxs-lookup"><span data-stu-id="6bda1-108">Remarks</span></span>  
 <span data-ttu-id="6bda1-109">Il `AddHandler` e `RemoveHandler` istruzioni consentono di avviare e arrestare la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="6bda1-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="6bda1-110">La firma del `eventhandler` routine deve corrispondere alla firma dell'evento `event`.</span><span class="sxs-lookup"><span data-stu-id="6bda1-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="6bda1-111">La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="6bda1-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="6bda1-112">L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6bda1-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="6bda1-113">Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento.</span><span class="sxs-lookup"><span data-stu-id="6bda1-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="6bda1-114">Per ulteriori informazioni, vedere [gestisce](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="6bda1-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bda1-115">Per gli eventi personalizzati, il `AddHandler` istruzione richiama l'evento `AddHandler` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="6bda1-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="6bda1-116">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6bda1-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6bda1-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="6bda1-117">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6bda1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bda1-118">See Also</span></span>  
 [<span data-ttu-id="6bda1-119">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="6bda1-119">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [<span data-ttu-id="6bda1-120">Handles</span><span class="sxs-lookup"><span data-stu-id="6bda1-120">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="6bda1-121">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="6bda1-121">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="6bda1-122">Eventi</span><span class="sxs-lookup"><span data-stu-id="6bda1-122">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)

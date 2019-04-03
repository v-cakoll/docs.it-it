---
title: Istruzione AddHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 1e8d8f512f163d82f074a5ad53fbb38a10904dfa
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827081"
---
# <a name="addhandler-statement"></a><span data-ttu-id="c67b1-102">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="c67b1-102">AddHandler Statement</span></span>
<span data-ttu-id="c67b1-103">Associa un evento a un gestore eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c67b1-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c67b1-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="c67b1-105">Parti</span><span class="sxs-lookup"><span data-stu-id="c67b1-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="c67b1-106">event</span><span class="sxs-lookup"><span data-stu-id="c67b1-106">event</span></span>|<span data-ttu-id="c67b1-107">Il nome dell'evento da gestire.</span><span class="sxs-lookup"><span data-stu-id="c67b1-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="c67b1-108">Il nome di una routine che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="c67b1-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="c67b1-109">Note</span><span class="sxs-lookup"><span data-stu-id="c67b1-109">Remarks</span></span>  
 <span data-ttu-id="c67b1-110">Il `AddHandler` e `RemoveHandler` istruzioni consentono di avviare e arrestare la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="c67b1-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="c67b1-111">La firma del `eventhandler` routine deve corrispondere alla firma dell'evento `event`.</span><span class="sxs-lookup"><span data-stu-id="c67b1-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="c67b1-112">La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="c67b1-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="c67b1-113">L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c67b1-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="c67b1-114">Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento.</span><span class="sxs-lookup"><span data-stu-id="c67b1-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="c67b1-115">Per altre informazioni, vedere [gestisce](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="c67b1-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c67b1-116">Per gli eventi personalizzati, il `AddHandler` istruzione richiama l'evento `AddHandler` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="c67b1-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="c67b1-117">Per altre informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c67b1-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c67b1-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="c67b1-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="c67b1-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c67b1-119">See also</span></span>

- [<span data-ttu-id="c67b1-120">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="c67b1-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="c67b1-121">Handles</span><span class="sxs-lookup"><span data-stu-id="c67b1-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="c67b1-122">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="c67b1-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="c67b1-123">Eventi</span><span class="sxs-lookup"><span data-stu-id="c67b1-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)

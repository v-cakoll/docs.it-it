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
ms.openlocfilehash: c110116af75d4fb39c016b8d6afcdb707fa6599b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350183"
---
# <a name="addhandler-statement"></a><span data-ttu-id="fa13b-102">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="fa13b-102">AddHandler Statement</span></span>
<span data-ttu-id="fa13b-103">Associates an event with an event handler at run time.</span><span class="sxs-lookup"><span data-stu-id="fa13b-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa13b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa13b-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="fa13b-105">Parti</span><span class="sxs-lookup"><span data-stu-id="fa13b-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="fa13b-106">event</span><span class="sxs-lookup"><span data-stu-id="fa13b-106">event</span></span>|<span data-ttu-id="fa13b-107">The name of the event to handle.</span><span class="sxs-lookup"><span data-stu-id="fa13b-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="fa13b-108">The name of a procedure that handles the event.</span><span class="sxs-lookup"><span data-stu-id="fa13b-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="fa13b-109">Note</span><span class="sxs-lookup"><span data-stu-id="fa13b-109">Remarks</span></span>  
 <span data-ttu-id="fa13b-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span><span class="sxs-lookup"><span data-stu-id="fa13b-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="fa13b-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span><span class="sxs-lookup"><span data-stu-id="fa13b-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="fa13b-112">La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="fa13b-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="fa13b-113">L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fa13b-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="fa13b-114">Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento.</span><span class="sxs-lookup"><span data-stu-id="fa13b-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="fa13b-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="fa13b-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa13b-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span><span class="sxs-lookup"><span data-stu-id="fa13b-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="fa13b-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fa13b-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa13b-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa13b-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="fa13b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa13b-119">See also</span></span>

- [<span data-ttu-id="fa13b-120">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="fa13b-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="fa13b-121">Handles</span><span class="sxs-lookup"><span data-stu-id="fa13b-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="fa13b-122">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="fa13b-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="fa13b-123">Eventi</span><span class="sxs-lookup"><span data-stu-id="fa13b-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)

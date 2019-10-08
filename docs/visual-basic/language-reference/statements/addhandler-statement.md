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
ms.openlocfilehash: 95277f532488b0cf56114e5ee94dc3528e3a2e02
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004534"
---
# <a name="addhandler-statement"></a><span data-ttu-id="692de-102">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="692de-102">AddHandler Statement</span></span>
<span data-ttu-id="692de-103">Associa un evento a un gestore eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="692de-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="692de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="692de-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="692de-105">Parti</span><span class="sxs-lookup"><span data-stu-id="692de-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="692de-106">event</span><span class="sxs-lookup"><span data-stu-id="692de-106">event</span></span>|<span data-ttu-id="692de-107">Nome dell'evento da gestire.</span><span class="sxs-lookup"><span data-stu-id="692de-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="692de-108">Nome di una routine che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="692de-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="692de-109">Note</span><span class="sxs-lookup"><span data-stu-id="692de-109">Remarks</span></span>  
 <span data-ttu-id="692de-110">Le istruzioni `AddHandler` e `RemoveHandler` consentono di avviare e arrestare la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="692de-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="692de-111">La firma della procedura `eventhandler` deve corrispondere alla firma dell'evento `event`.</span><span class="sxs-lookup"><span data-stu-id="692de-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="692de-112">La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="692de-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="692de-113">L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="692de-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="692de-114">Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento.</span><span class="sxs-lookup"><span data-stu-id="692de-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="692de-115">Per ulteriori informazioni, vedere [handle](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="692de-115">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="692de-116">Per gli eventi personalizzati, l'istruzione `AddHandler` richiama la funzione di accesso `AddHandler` dell'evento.</span><span class="sxs-lookup"><span data-stu-id="692de-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="692de-117">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="692de-117">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="692de-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="692de-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="692de-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="692de-119">See also</span></span>

- [<span data-ttu-id="692de-120">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="692de-120">RemoveHandler Statement</span></span>](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [<span data-ttu-id="692de-121">Handles</span><span class="sxs-lookup"><span data-stu-id="692de-121">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="692de-122">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="692de-122">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="692de-123">Eventi</span><span class="sxs-lookup"><span data-stu-id="692de-123">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)

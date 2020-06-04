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
ms.openlocfilehash: de995a13b34678410e2af74b59f2d0c467982b75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408484"
---
# <a name="addhandler-statement"></a><span data-ttu-id="4967d-102">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="4967d-102">AddHandler Statement</span></span>
<span data-ttu-id="4967d-103">Associa un evento a un gestore eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4967d-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4967d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4967d-104">Syntax</span></span>  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="4967d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="4967d-105">Parts</span></span>  
|||
|---|---|
|<span data-ttu-id="4967d-106">event</span><span class="sxs-lookup"><span data-stu-id="4967d-106">event</span></span>|<span data-ttu-id="4967d-107">Nome dell'evento da gestire.</span><span class="sxs-lookup"><span data-stu-id="4967d-107">The name of the event to handle.</span></span>|  
|`eventhandler`|<span data-ttu-id="4967d-108">Nome di una routine che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="4967d-108">The name of a procedure that handles the event.</span></span>|
|||
  
## <a name="remarks"></a><span data-ttu-id="4967d-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="4967d-109">Remarks</span></span>  
 <span data-ttu-id="4967d-110">Le `AddHandler` `RemoveHandler` istruzioni e consentono di avviare e arrestare la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="4967d-110">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="4967d-111">La firma della `eventhandler` stored procedure deve corrispondere alla firma dell'evento `event` .</span><span class="sxs-lookup"><span data-stu-id="4967d-111">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="4967d-112">La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="4967d-112">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="4967d-113">L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4967d-113">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="4967d-114">Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento.</span><span class="sxs-lookup"><span data-stu-id="4967d-114">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="4967d-115">Per ulteriori informazioni, vedere [handle](handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4967d-115">For more information, see [Handles](handles-clause.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4967d-116">Per gli eventi personalizzati, l' `AddHandler` istruzione richiama la funzione di `AddHandler` accesso dell'evento.</span><span class="sxs-lookup"><span data-stu-id="4967d-116">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="4967d-117">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4967d-117">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4967d-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="4967d-118">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="4967d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4967d-119">See also</span></span>

- [<span data-ttu-id="4967d-120">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="4967d-120">RemoveHandler Statement</span></span>](removehandler-statement.md)
- [<span data-ttu-id="4967d-121">Selettori</span><span class="sxs-lookup"><span data-stu-id="4967d-121">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="4967d-122">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="4967d-122">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="4967d-123">Events</span><span class="sxs-lookup"><span data-stu-id="4967d-123">Events</span></span>](../../programming-guide/language-features/events/index.md)

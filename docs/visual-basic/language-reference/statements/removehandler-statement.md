---
title: Istruzione RemoveHandler
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 0d982768707948bd6c616445509e16a462b86f2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597988"
---
# <a name="removehandler-statement"></a><span data-ttu-id="57ae3-102">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="57ae3-102">RemoveHandler Statement</span></span>
<span data-ttu-id="57ae3-103">Rimuove l'associazione tra un evento e un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="57ae3-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57ae3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57ae3-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="57ae3-105">Parti</span><span class="sxs-lookup"><span data-stu-id="57ae3-105">Parts</span></span>  
  
|<span data-ttu-id="57ae3-106">Termine</span><span class="sxs-lookup"><span data-stu-id="57ae3-106">Term</span></span>|<span data-ttu-id="57ae3-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="57ae3-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="57ae3-108">Il nome dell'evento gestito.</span><span class="sxs-lookup"><span data-stu-id="57ae3-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="57ae3-109">Il nome della routine che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="57ae3-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57ae3-110">Note</span><span class="sxs-lookup"><span data-stu-id="57ae3-110">Remarks</span></span>  
 <span data-ttu-id="57ae3-111">Il `AddHandler` e `RemoveHandler` istruzioni consentono di avviare e arrestare la gestione degli eventi per un evento specifico in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="57ae3-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57ae3-112">Per gli eventi personalizzati, il `RemoveHandler` istruzione richiama l'evento `RemoveHandler` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="57ae3-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="57ae3-113">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="57ae3-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57ae3-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="57ae3-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="57ae3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57ae3-115">See Also</span></span>  
 [<span data-ttu-id="57ae3-116">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="57ae3-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [<span data-ttu-id="57ae3-117">Handles</span><span class="sxs-lookup"><span data-stu-id="57ae3-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="57ae3-118">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="57ae3-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="57ae3-119">Eventi</span><span class="sxs-lookup"><span data-stu-id="57ae3-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)

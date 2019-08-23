---
title: Istruzione RemoveHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 3a839a7d05d05066f6c0f774a683c8fc83c19643
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957729"
---
# <a name="removehandler-statement"></a><span data-ttu-id="f68f0-102">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="f68f0-102">RemoveHandler Statement</span></span>
<span data-ttu-id="f68f0-103">Rimuove l'associazione tra un evento e un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f68f0-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f68f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f68f0-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="f68f0-105">Parti</span><span class="sxs-lookup"><span data-stu-id="f68f0-105">Parts</span></span>  
  
|<span data-ttu-id="f68f0-106">Termine</span><span class="sxs-lookup"><span data-stu-id="f68f0-106">Term</span></span>|<span data-ttu-id="f68f0-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="f68f0-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="f68f0-108">Nome dell'evento da gestire.</span><span class="sxs-lookup"><span data-stu-id="f68f0-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="f68f0-109">Nome della stored procedure che gestisce attualmente l'evento.</span><span class="sxs-lookup"><span data-stu-id="f68f0-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f68f0-110">Note</span><span class="sxs-lookup"><span data-stu-id="f68f0-110">Remarks</span></span>  
 <span data-ttu-id="f68f0-111">Le `AddHandler` istruzioni `RemoveHandler` e consentono di avviare e arrestare la gestione degli eventi per un evento specifico in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="f68f0-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f68f0-112">Per gli eventi personalizzati, `RemoveHandler` l'istruzione richiama la funzione di `RemoveHandler` accesso dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f68f0-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="f68f0-113">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f68f0-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f68f0-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="f68f0-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="f68f0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f68f0-115">See also</span></span>

- [<span data-ttu-id="f68f0-116">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="f68f0-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="f68f0-117">Handles</span><span class="sxs-lookup"><span data-stu-id="f68f0-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="f68f0-118">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="f68f0-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="f68f0-119">Eventi</span><span class="sxs-lookup"><span data-stu-id="f68f0-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)

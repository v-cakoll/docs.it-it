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
ms.openlocfilehash: 47f35bd76d7734878e7b5b206b4aecd856276593
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582015"
---
# <a name="removehandler-statement"></a><span data-ttu-id="80398-102">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="80398-102">RemoveHandler Statement</span></span>
<span data-ttu-id="80398-103">Rimuove l'associazione tra un evento e un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="80398-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80398-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80398-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="80398-105">Parti</span><span class="sxs-lookup"><span data-stu-id="80398-105">Parts</span></span>  
  
|<span data-ttu-id="80398-106">Termine</span><span class="sxs-lookup"><span data-stu-id="80398-106">Term</span></span>|<span data-ttu-id="80398-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="80398-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="80398-108">Nome dell'evento da gestire.</span><span class="sxs-lookup"><span data-stu-id="80398-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="80398-109">Nome della stored procedure che gestisce attualmente l'evento.</span><span class="sxs-lookup"><span data-stu-id="80398-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80398-110">Note</span><span class="sxs-lookup"><span data-stu-id="80398-110">Remarks</span></span>  
 <span data-ttu-id="80398-111">Le istruzioni `AddHandler` e `RemoveHandler` consentono di avviare e arrestare la gestione degli eventi per un evento specifico in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="80398-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80398-112">Per gli eventi personalizzati, l'istruzione `RemoveHandler` richiama la funzione di accesso `RemoveHandler` dell'evento.</span><span class="sxs-lookup"><span data-stu-id="80398-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="80398-113">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="80398-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80398-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="80398-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="80398-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80398-115">See also</span></span>

- [<span data-ttu-id="80398-116">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="80398-116">AddHandler Statement</span></span>](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [<span data-ttu-id="80398-117">Handles</span><span class="sxs-lookup"><span data-stu-id="80398-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="80398-118">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="80398-118">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="80398-119">Eventi</span><span class="sxs-lookup"><span data-stu-id="80398-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)

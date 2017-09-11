---
title: RemoveHandler (istruzione) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
dev_langs:
- VB
helpviewer_keywords:
- RemoveHandler keyword
- RemoveHandler statement
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6e614a1dce4894dcd18509854f3cae149665cbf0
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="removehandler-statement"></a><span data-ttu-id="e949d-102">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="e949d-102">RemoveHandler Statement</span></span>
<span data-ttu-id="e949d-103">Rimuove l'associazione tra un evento e un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e949d-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e949d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e949d-104">Syntax</span></span>  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="e949d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e949d-105">Parts</span></span>  
  
|<span data-ttu-id="e949d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="e949d-106">Term</span></span>|<span data-ttu-id="e949d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="e949d-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="e949d-108">Il nome dell'evento gestito.</span><span class="sxs-lookup"><span data-stu-id="e949d-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="e949d-109">Il nome della routine che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="e949d-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e949d-110">Note</span><span class="sxs-lookup"><span data-stu-id="e949d-110">Remarks</span></span>  
 <span data-ttu-id="e949d-111">Il `AddHandler` e `RemoveHandler` istruzioni consentono di avviare e interrompere la gestione degli eventi per un evento specifico in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="e949d-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e949d-112">Per gli eventi personalizzati, il `RemoveHandler` istruzione richiama l'evento `RemoveHandler` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="e949d-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="e949d-113">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e949d-113">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e949d-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="e949d-114">Example</span></span>  
 <span data-ttu-id="e949d-115">[!code-vb[VbVbalrEvents n.&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e949d-115">[!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e949d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e949d-116">See Also</span></span>  
 <span data-ttu-id="e949d-117">[AddHandler (istruzione)](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e949d-117">[AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="e949d-118"> [Handle](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="e949d-118"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="e949d-119"> [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e949d-119"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="e949d-120"> [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="e949d-120"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>

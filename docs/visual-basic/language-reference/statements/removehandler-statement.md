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
ms.openlocfilehash: 3514a79f2430b148e6a3727b83029b4e207a677b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404252"
---
# <a name="removehandler-statement"></a><span data-ttu-id="6766d-102">Istruzione RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="6766d-102">RemoveHandler Statement</span></span>
<span data-ttu-id="6766d-103">Rimuove l'associazione tra un evento e un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="6766d-103">Removes the association between an event and an event handler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6766d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6766d-104">Syntax</span></span>  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="6766d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6766d-105">Parts</span></span>  
  
|<span data-ttu-id="6766d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="6766d-106">Term</span></span>|<span data-ttu-id="6766d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="6766d-107">Definition</span></span>|  
|---|---|  
|`event`|<span data-ttu-id="6766d-108">Nome dell'evento da gestire.</span><span class="sxs-lookup"><span data-stu-id="6766d-108">The name of the event being handled.</span></span>|  
|`eventhandler`|<span data-ttu-id="6766d-109">Nome della stored procedure che gestisce attualmente l'evento.</span><span class="sxs-lookup"><span data-stu-id="6766d-109">The name of the procedure currently handling the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6766d-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="6766d-110">Remarks</span></span>  
 <span data-ttu-id="6766d-111">Le `AddHandler` `RemoveHandler` istruzioni e consentono di avviare e arrestare la gestione degli eventi per un evento specifico in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="6766d-111">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling for a specific event at any time during program execution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6766d-112">Per gli eventi personalizzati, l' `RemoveHandler` istruzione richiama la funzione di `RemoveHandler` accesso dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6766d-112">For custom events, the `RemoveHandler` statement invokes the event's `RemoveHandler` accessor.</span></span> <span data-ttu-id="6766d-113">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6766d-113">For more information on custom events, see [Event Statement](event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6766d-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="6766d-114">Example</span></span>  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a><span data-ttu-id="6766d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6766d-115">See also</span></span>

- [<span data-ttu-id="6766d-116">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="6766d-116">AddHandler Statement</span></span>](addhandler-statement.md)
- [<span data-ttu-id="6766d-117">Selettori</span><span class="sxs-lookup"><span data-stu-id="6766d-117">Handles</span></span>](handles-clause.md)
- [<span data-ttu-id="6766d-118">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="6766d-118">Event Statement</span></span>](event-statement.md)
- [<span data-ttu-id="6766d-119">Events</span><span class="sxs-lookup"><span data-stu-id="6766d-119">Events</span></span>](../../programming-guide/language-features/events/index.md)

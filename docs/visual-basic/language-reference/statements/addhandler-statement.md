---
title: AddHandler (istruzione) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
dev_langs:
- VB
helpviewer_keywords:
- AddHandler statement
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
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
ms.openlocfilehash: cd821a568a35f33c722c1631eb7fbaf8f877cf4f
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="addhandler-statement"></a><span data-ttu-id="037d9-102">Istruzione AddHandler</span><span class="sxs-lookup"><span data-stu-id="037d9-102">AddHandler Statement</span></span>
<span data-ttu-id="037d9-103">Associa un evento al gestore eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="037d9-103">Associates an event with an event handler at run time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="037d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="037d9-104">Syntax</span></span>  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a><span data-ttu-id="037d9-105">Parti</span><span class="sxs-lookup"><span data-stu-id="037d9-105">Parts</span></span>  
 `event`  
 <span data-ttu-id="037d9-106">Il nome dell'evento da gestire.</span><span class="sxs-lookup"><span data-stu-id="037d9-106">The name of the event to handle.</span></span>  
  
 `eventhandler`  
 <span data-ttu-id="037d9-107">Il nome di una routine che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="037d9-107">The name of a procedure that handles the event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="037d9-108">Note</span><span class="sxs-lookup"><span data-stu-id="037d9-108">Remarks</span></span>  
 <span data-ttu-id="037d9-109">Il `AddHandler` e `RemoveHandler` istruzioni consentono di avviare e interrompere la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="037d9-109">The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.</span></span>  
  
 <span data-ttu-id="037d9-110">La firma di `eventhandler` procedura deve corrispondere alla firma dell'evento `event`.</span><span class="sxs-lookup"><span data-stu-id="037d9-110">The signature of the `eventhandler` procedure must match the signature of the event `event`.</span></span>  
  
 <span data-ttu-id="037d9-111">La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze.</span><span class="sxs-lookup"><span data-stu-id="037d9-111">The `Handles` keyword and the `AddHandler` statement both allow you to specify that particular procedures handle particular events, but there are differences.</span></span> <span data-ttu-id="037d9-112">L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="037d9-112">The `AddHandler` statement connects procedures to events at run time.</span></span> <span data-ttu-id="037d9-113">Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento.</span><span class="sxs-lookup"><span data-stu-id="037d9-113">Use the `Handles` keyword when defining a procedure to specify that it handles a particular event.</span></span> <span data-ttu-id="037d9-114">Per ulteriori informazioni, vedere [gestisce](../../../visual-basic/language-reference/statements/handles-clause.md).</span><span class="sxs-lookup"><span data-stu-id="037d9-114">For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="037d9-115">Per gli eventi personalizzati, il `AddHandler` istruzione richiama l'evento `AddHandler` della funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="037d9-115">For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor.</span></span> <span data-ttu-id="037d9-116">Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).</span><span class="sxs-lookup"><span data-stu-id="037d9-116">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="037d9-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="037d9-117">Example</span></span>  
 <span data-ttu-id="037d9-118">[!code-vb[VbVbalrEvents n.&17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="037d9-118">[!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="037d9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="037d9-119">See Also</span></span>  
 <span data-ttu-id="037d9-120">[RemoveHandler (istruzione)](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="037d9-120">[RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="037d9-121"> [Handle](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="037d9-121"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="037d9-122"> [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="037d9-122"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="037d9-123"> [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="037d9-123"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>

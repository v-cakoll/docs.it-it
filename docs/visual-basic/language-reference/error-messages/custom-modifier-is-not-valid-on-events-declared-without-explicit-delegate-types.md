---
title: "&#39; Custom &#39; modificatore non è valido negli eventi dichiarati senza tipi delegati espliciti"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords: BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 844bd033ea05e373b04a04f80777af77179c1263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="7bc41-102">&#39; Custom &#39; modificatore non è valido negli eventi dichiarati senza tipi delegati espliciti</span><span class="sxs-lookup"><span data-stu-id="7bc41-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="7bc41-103">A differenza di un evento non personalizzato, un `Custom Event` dichiarazione richiede un `As` clausola dopo il nome di evento che specifica in modo esplicito il tipo di delegato per l'evento.</span><span class="sxs-lookup"><span data-stu-id="7bc41-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="7bc41-104">Gli eventi non personalizzati possono essere definiti con un `As` clausola esplicita tipo delegato e con un parametro elenco immediatamente dopo il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="7bc41-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="7bc41-105">**ID errore:** BC31122</span><span class="sxs-lookup"><span data-stu-id="7bc41-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7bc41-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7bc41-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="7bc41-107">Definire un delegato con lo stesso elenco di parametri dell'evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7bc41-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="7bc41-108">Ad esempio, se il `Custom Event` è stato definito da `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, quindi il delegato corrispondente potrebbe essere la seguente.</span><span class="sxs-lookup"><span data-stu-id="7bc41-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]  
  
2.  <span data-ttu-id="7bc41-109">Sostituire l'elenco di parametri dell'evento personalizzato con un `As` clausola che specifica il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="7bc41-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="7bc41-110">Continuando con l'esempio, `Custom Event` dichiarazione potrebbe essere riscritto come segue.</span><span class="sxs-lookup"><span data-stu-id="7bc41-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="7bc41-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bc41-111">Example</span></span>  
 <span data-ttu-id="7bc41-112">In questo esempio dichiara un `Custom Event` e specifica la `As` clausola con un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="7bc41-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7bc41-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bc41-113">See Also</span></span>  
 [<span data-ttu-id="7bc41-114">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="7bc41-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="7bc41-115">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="7bc41-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="7bc41-116">Eventi</span><span class="sxs-lookup"><span data-stu-id="7bc41-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)

---
title: "Modificatore &quot;Custom&quot; non è valido negli eventi dichiarati senza tipi delegati espliciti | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31122
- bc31122
dev_langs:
- VB
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
caps.latest.revision: 9
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
ms.openlocfilehash: 449e5a690f06ce35d1ccc799daf5f2c1ad1c6dac
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="39custom39-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="29bdd-102">Modificatore 'Custom' non è valido negli eventi dichiarati senza tipi delegati espliciti</span><span class="sxs-lookup"><span data-stu-id="29bdd-102">&#39;Custom&#39; modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="29bdd-103">A differenza di un evento non personalizzato, un `Custom Event` dichiarazione richiede un `As` clausola dopo il nome di evento che specifica in modo esplicito il tipo di delegato per l'evento.</span><span class="sxs-lookup"><span data-stu-id="29bdd-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="29bdd-104">Gli eventi non personalizzati possono essere definiti con un `As` clausola ed esplicita tipo delegato o con un parametro elenco immediatamente dopo il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="29bdd-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="29bdd-105">**ID errore:** BC31122</span><span class="sxs-lookup"><span data-stu-id="29bdd-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29bdd-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="29bdd-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="29bdd-107">Definire un delegato con lo stesso elenco di parametri dell'evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="29bdd-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="29bdd-108">Ad esempio, se il `Custom Event` è stato definito da `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, quindi il delegato corrispondente sarebbe il seguente.</span><span class="sxs-lookup"><span data-stu-id="29bdd-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     <span data-ttu-id="29bdd-109">[!code-vb[VbVbalrEventError&#18;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="29bdd-109">[!code-vb[VbVbalrEventError#18](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_1.vb)]</span></span>  
  
2.  <span data-ttu-id="29bdd-110">Sostituire l'elenco di parametri dell'evento personalizzato con un `As` clausola che specifica il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="29bdd-110">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="29bdd-111">Continuando con l'esempio, `Custom Event` dichiarazione potrebbe essere riscritto come segue.</span><span class="sxs-lookup"><span data-stu-id="29bdd-111">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     <span data-ttu-id="29bdd-112">[!code-vb[&#19; VbVbalrEventError](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="29bdd-112">[!code-vb[VbVbalrEventError#19](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="29bdd-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="29bdd-113">Example</span></span>  
 <span data-ttu-id="29bdd-114">In questo esempio dichiara un `Custom Event` e specifica le `As` clausola con un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="29bdd-114">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 <span data-ttu-id="29bdd-115">[!code-vb[VbVbalrEventError n.&2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="29bdd-115">[!code-vb[VbVbalrEventError#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bdd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29bdd-116">See Also</span></span>  
 <span data-ttu-id="29bdd-117">[Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="29bdd-117">[Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="29bdd-118"> [Delegate (istruzione)](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="29bdd-118"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="29bdd-119"> [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="29bdd-119"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>

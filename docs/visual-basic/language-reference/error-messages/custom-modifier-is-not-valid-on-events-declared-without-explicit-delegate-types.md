---
title: Modificatore 'Custom' non valido negli eventi dichiarati senza tipi delegati espliciti
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 0fc645671eb899faff0dbb5c6d745ba23faf4557
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827224"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="9f71e-102">Modificatore 'Custom' non valido negli eventi dichiarati senza tipi delegati espliciti</span><span class="sxs-lookup"><span data-stu-id="9f71e-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="9f71e-103">A differenza di un evento non personalizzato, un `Custom Event` dichiarazione richiede un `As` clausola dopo il nome dell'evento che specifichi esplicitamente il tipo di delegato per l'evento.</span><span class="sxs-lookup"><span data-stu-id="9f71e-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="9f71e-104">Gli eventi personalizzati non possono essere definite con un `As` clausola ed esplicita tipo delegato o con un parametro di elenco immediatamente dopo il nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="9f71e-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="9f71e-105">**ID errore:** BC31122</span><span class="sxs-lookup"><span data-stu-id="9f71e-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9f71e-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9f71e-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="9f71e-107">Definire un delegato con lo stesso elenco di parametri dell'evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9f71e-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="9f71e-108">Ad esempio, se il `Custom Event` è stato definito da `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, quindi il delegato corrispondente sarebbe il seguente.</span><span class="sxs-lookup"><span data-stu-id="9f71e-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2.  <span data-ttu-id="9f71e-109">Sostituire l'elenco di parametri dell'evento personalizzato con un `As` clausola che specifica il tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="9f71e-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="9f71e-110">Continuando con l'esempio `Custom Event` dichiarazione potrebbe essere riscritto come segue.</span><span class="sxs-lookup"><span data-stu-id="9f71e-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="9f71e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="9f71e-111">Example</span></span>  
 <span data-ttu-id="9f71e-112">Questo esempio viene dichiarata una `Custom Event` e specifica la necessaria `As` clausola con un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="9f71e-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9f71e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f71e-113">See also</span></span>

- [<span data-ttu-id="9f71e-114">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="9f71e-114">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="9f71e-115">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="9f71e-115">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="9f71e-116">Eventi</span><span class="sxs-lookup"><span data-stu-id="9f71e-116">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)

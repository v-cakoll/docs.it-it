---
title: Modificatore 'Custom' non valido negli eventi dichiarati senza tipi delegati espliciti
ms.date: 07/20/2015
f1_keywords:
- vbc31122
- bc31122
helpviewer_keywords:
- BC31122
ms.assetid: 6911f0d1-641a-473b-906d-8ee5681194be
ms.openlocfilehash: 0c5a4188fedf9685afdd1cde4c1de93a0b43b919
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409783"
---
# <a name="custom-modifier-is-not-valid-on-events-declared-without-explicit-delegate-types"></a><span data-ttu-id="15f4d-102">Modificatore 'Custom' non valido negli eventi dichiarati senza tipi delegati espliciti</span><span class="sxs-lookup"><span data-stu-id="15f4d-102">'Custom' modifier is not valid on events declared without explicit delegate types</span></span>
<span data-ttu-id="15f4d-103">A differenza di un evento non personalizzato, una `Custom Event` dichiarazione richiede una `As` clausola che segue il nome dell'evento che specifica in modo esplicito il tipo di delegato per l'evento.</span><span class="sxs-lookup"><span data-stu-id="15f4d-103">Unlike a non-custom event, a `Custom Event` declaration requires an `As` clause following the event name that explicitly specifies the delegate type for the event.</span></span>  
  
 <span data-ttu-id="15f4d-104">Gli eventi non personalizzati possono essere definiti con una `As` clausola e un tipo di delegato esplicito o con un elenco di parametri immediatamente successivo al nome dell'evento.</span><span class="sxs-lookup"><span data-stu-id="15f4d-104">Non-custom events can be defined either with an `As` clause and an explicit delegate type, or with a parameter list immediately following the event name.</span></span>  
  
 <span data-ttu-id="15f4d-105">**ID errore:** BC31122</span><span class="sxs-lookup"><span data-stu-id="15f4d-105">**Error ID:** BC31122</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="15f4d-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="15f4d-106">To correct this error</span></span>  
  
1. <span data-ttu-id="15f4d-107">Definire un delegato con lo stesso elenco di parametri dell'evento personalizzato.</span><span class="sxs-lookup"><span data-stu-id="15f4d-107">Define a delegate with the same parameter list as the custom event.</span></span>  
  
     <span data-ttu-id="15f4d-108">Se, ad esempio, `Custom Event` è stato definito da `Custom Event Test(ByVal sender As Object, ByVal i As Integer)` , il delegato corrispondente sarà il seguente.</span><span class="sxs-lookup"><span data-stu-id="15f4d-108">For example, if the `Custom Event` was defined by `Custom Event Test(ByVal sender As Object, ByVal i As Integer)`, then the corresponding delegate would be the following.</span></span>  
  
     [!code-vb[VbVbalrEventError#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#18)]  
  
2. <span data-ttu-id="15f4d-109">Sostituire l'elenco di parametri dell'evento personalizzato con una `As` clausola che specifica il tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="15f4d-109">Replace the parameter list of the custom event with an `As` clause specifying the delegate type.</span></span>  
  
     <span data-ttu-id="15f4d-110">Continuando con l'esempio, la `Custom Event` dichiarazione verrebbe riscritta nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="15f4d-110">Continuing with the example, `Custom Event` declaration would be rewritten as follows.</span></span>  
  
     [!code-vb[VbVbalrEventError#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="15f4d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="15f4d-111">Example</span></span>  
 <span data-ttu-id="15f4d-112">In questo esempio viene dichiarato un oggetto `Custom Event` e viene specificata la `As` clausola obbligatoria con un tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="15f4d-112">This example declares a `Custom Event` and specifies the required `As` clause with a delegate type.</span></span>  
  
 [!code-vb[VbVbalrEventError#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEventError/VB/VbVbalrEventError.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="15f4d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f4d-113">See also</span></span>

- [<span data-ttu-id="15f4d-114">Istruzione Event</span><span class="sxs-lookup"><span data-stu-id="15f4d-114">Event Statement</span></span>](../statements/event-statement.md)
- [<span data-ttu-id="15f4d-115">Istruzione Delegate</span><span class="sxs-lookup"><span data-stu-id="15f4d-115">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="15f4d-116">Events</span><span class="sxs-lookup"><span data-stu-id="15f4d-116">Events</span></span>](../../programming-guide/language-features/events/index.md)

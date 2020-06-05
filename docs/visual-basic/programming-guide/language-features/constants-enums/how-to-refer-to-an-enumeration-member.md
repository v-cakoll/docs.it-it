---
title: 'Procedura: fare riferimento a un membro di enumerazione'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: 66c527bd4ba4721065de8fca8534fe652d0139be
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414414"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="0b650-102">Procedura: fare riferimento a un membro di enumerazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b650-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="0b650-103">Le enumerazioni rappresentano un modo pratico per usare set di costanti correlate e per associare i valori costanti ai nomi.</span><span class="sxs-lookup"><span data-stu-id="0b650-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="0b650-104">Ad esempio, si può dichiarare un'enumerazione per un set di costanti integer associate ai giorni della settimana e quindi usare i nomi dei giorni anziché i relativi valori integer nel codice.</span><span class="sxs-lookup"><span data-stu-id="0b650-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="0b650-105">È possibile evitare di utilizzare nomi completi con l' `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0b650-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="0b650-106">Per altre informazioni, vedere [enumerazioni e qualificazione del nome](enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="0b650-106">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="0b650-107">Per fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="0b650-107">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="0b650-108">Qualificare il nome del membro con l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0b650-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="0b650-109">Nell'esempio seguente, ad esempio, il `Saturday` membro dell'enumerazione viene assegnato `FirstDayOfWeek` alla variabile `DayValue` .</span><span class="sxs-lookup"><span data-stu-id="0b650-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="0b650-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b650-110">See also</span></span>

- [<span data-ttu-id="0b650-111">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="0b650-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="0b650-112">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="0b650-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="0b650-113">Procedura: scorrere un'enumerazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0b650-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="0b650-114">Procedura: determinare la stringa associata a un valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="0b650-114">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="0b650-115">Quando utilizzare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="0b650-115">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)

---
title: 'Procedura: Fare riferimento a un membro di enumerazione (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: e9ea359d58dfa11f7bba7fec3d31955e18d24953
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813977"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="a07ae-102">Procedura: Fare riferimento a un membro di enumerazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a07ae-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="a07ae-103">Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i nomi di valori costanti.</span><span class="sxs-lookup"><span data-stu-id="a07ae-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="a07ae-104">Ad esempio, si può dichiarare un'enumerazione per un set di costanti integer associate ai giorni della settimana e quindi usare i nomi dei giorni anziché i relativi valori integer nel codice.</span><span class="sxs-lookup"><span data-stu-id="a07ae-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="a07ae-105">È possibile evitare di utilizzare nomi pienamente qualificati con il `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="a07ae-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="a07ae-106">Per altre informazioni, vedere [qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="a07ae-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="a07ae-107">Per fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="a07ae-107">To refer to an enumeration member</span></span>  
  
-   <span data-ttu-id="a07ae-108">Qualificare il nome del membro con l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a07ae-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="a07ae-109">Ad esempio, l'esempio seguente assegna il `Saturday` membro del `FirstDayOfWeek` enumerazione alla variabile `DayValue`.</span><span class="sxs-lookup"><span data-stu-id="a07ae-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="a07ae-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a07ae-110">See also</span></span>

- [<span data-ttu-id="a07ae-111">Procedura: Dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="a07ae-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="a07ae-112">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="a07ae-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="a07ae-113">Procedura: Scorrere un'enumerazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a07ae-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="a07ae-114">Procedura: Determinare la stringa associata a un valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="a07ae-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="a07ae-115">Quando usare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="a07ae-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)

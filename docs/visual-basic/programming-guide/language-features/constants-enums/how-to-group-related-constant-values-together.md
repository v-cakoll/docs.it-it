---
title: 'Procedura: raggruppare i valori delle costanti correlate (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 320373116ad4d61293690353fce6b7b152e79a4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646404"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="24f4c-102">Procedura: raggruppare i valori delle costanti correlate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24f4c-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="24f4c-103">Un'enumerazione è il modo migliore per raggruppare le costanti correlate.</span><span class="sxs-lookup"><span data-stu-id="24f4c-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="24f4c-104">Per creare un'enumerazione con la `Enum` istruzione nella sezione delle dichiarazioni di una classe o un modulo.</span><span class="sxs-lookup"><span data-stu-id="24f4c-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="24f4c-105">Per ulteriori informazioni, vedere [procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="24f4c-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="24f4c-106">Al gruppo di valori delle costanti correlate</span><span class="sxs-lookup"><span data-stu-id="24f4c-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="24f4c-107">Scrivere una dichiarazione che include un livello di accesso di codice, il `Enum` (parola chiave) e un nome valido.</span><span class="sxs-lookup"><span data-stu-id="24f4c-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="24f4c-108">Questo esempio viene creata la `Private` enumerazione `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="24f4c-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  <span data-ttu-id="24f4c-109">Definire le costanti dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="24f4c-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="24f4c-110">Questo esempio viene creata la `Public` enumerazione `temperatureValues` e assegna i valori.</span><span class="sxs-lookup"><span data-stu-id="24f4c-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="24f4c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24f4c-111">See Also</span></span>  
 [<span data-ttu-id="24f4c-112">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="24f4c-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="24f4c-113">Procedura: Fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="24f4c-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="24f4c-114">Quando usare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="24f4c-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="24f4c-115">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="24f4c-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="24f4c-116">Tipi di dati costanti e letterali</span><span class="sxs-lookup"><span data-stu-id="24f4c-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="24f4c-117">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="24f4c-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)

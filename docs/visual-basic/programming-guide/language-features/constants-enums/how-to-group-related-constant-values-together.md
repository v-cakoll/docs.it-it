---
title: 'Procedura: Raggruppare i valori delle costanti correlate insieme (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: a4f74e48cfdd5c0bc0f745d0f32eb39442f5bd83
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333328"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="77b4d-102">Procedura: Raggruppare i valori delle costanti correlate insieme (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77b4d-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="77b4d-103">Un'enumerazione è il modo migliore per raggruppare le costanti correlate tra loro.</span><span class="sxs-lookup"><span data-stu-id="77b4d-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="77b4d-104">Per creare un'enumerazione con i `Enum` istruzione nella sezione delle dichiarazioni di una classe o un modulo.</span><span class="sxs-lookup"><span data-stu-id="77b4d-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="77b4d-105">Per altre informazioni, vedere [Procedura: Dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="77b4d-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="77b4d-106">Al gruppo di valori delle costanti correlate</span><span class="sxs-lookup"><span data-stu-id="77b4d-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="77b4d-107">Scrivere una dichiarazione che include un livello di accesso di codice, il `Enum` (parola chiave) e un nome valido.</span><span class="sxs-lookup"><span data-stu-id="77b4d-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="77b4d-108">Questo esempio viene creato il `Private` enumerazione `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="77b4d-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="77b4d-109">Definire le costanti nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="77b4d-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="77b4d-110">Questo esempio viene creato il `Public` enumerazione `temperatureValues` e assegna i valori.</span><span class="sxs-lookup"><span data-stu-id="77b4d-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="77b4d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77b4d-111">See also</span></span>

- [<span data-ttu-id="77b4d-112">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="77b4d-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="77b4d-113">Procedura: Fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="77b4d-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="77b4d-114">Quando utilizzare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="77b4d-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="77b4d-115">Panoramica sulle costanti</span><span class="sxs-lookup"><span data-stu-id="77b4d-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="77b4d-116">Tipi di dati costanti e letterali</span><span class="sxs-lookup"><span data-stu-id="77b4d-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="77b4d-117">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="77b4d-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)

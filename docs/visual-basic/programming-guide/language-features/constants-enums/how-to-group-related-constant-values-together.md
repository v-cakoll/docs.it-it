---
title: 'Procedura: raggruppare i valori delle costanti correlate'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: d2393af8b0c2b0c2e528f9908a78fbc7f182c8cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414440"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="a59d4-102">Procedura: raggruppare i valori delle costanti correlate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a59d4-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="a59d4-103">Un'enumerazione rappresenta il modo migliore per raggruppare le costanti correlate.</span><span class="sxs-lookup"><span data-stu-id="a59d4-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="a59d4-104">Si crea un'enumerazione con l' `Enum` istruzione nella sezione delle dichiarazioni di una classe o di un modulo.</span><span class="sxs-lookup"><span data-stu-id="a59d4-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="a59d4-105">Per altre informazioni, vedere [procedura: dichiarare un'enumerazione](how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="a59d4-105">For more information, see [How to: Declare an Enumeration](how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="a59d4-106">Per raggruppare i valori delle costanti correlate</span><span class="sxs-lookup"><span data-stu-id="a59d4-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="a59d4-107">Scrivere una dichiarazione che includa un livello di accesso al codice, la `Enum` parola chiave e un nome valido.</span><span class="sxs-lookup"><span data-stu-id="a59d4-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="a59d4-108">In questo esempio viene creata l' `Private` enumerazione `temperatureValues` .</span><span class="sxs-lookup"><span data-stu-id="a59d4-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="a59d4-109">Definire le costanti nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="a59d4-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="a59d4-110">Questo esempio crea l' `Public` enumerazione `temperatureValues` e ne assegna i valori.</span><span class="sxs-lookup"><span data-stu-id="a59d4-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a59d4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a59d4-111">See also</span></span>

- [<span data-ttu-id="a59d4-112">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="a59d4-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="a59d4-113">Procedura: fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="a59d4-113">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="a59d4-114">Quando utilizzare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="a59d4-114">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="a59d4-115">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="a59d4-115">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="a59d4-116">Tipi di dati costanti e letterali</span><span class="sxs-lookup"><span data-stu-id="a59d4-116">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="a59d4-117">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="a59d4-117">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)

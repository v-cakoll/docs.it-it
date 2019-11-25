---
title: Widening
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 1c9aa78549ca6e41c9fe54c12e0aaec8e7cc30cb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347836"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="4d7e3-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d7e3-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="4d7e3-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span><span class="sxs-lookup"><span data-stu-id="4d7e3-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="4d7e3-104">Converting with the Widening Keyword</span><span class="sxs-lookup"><span data-stu-id="4d7e3-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="4d7e3-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span><span class="sxs-lookup"><span data-stu-id="4d7e3-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="4d7e3-106">Widening conversions always succeed at run time and never incur data loss.</span><span class="sxs-lookup"><span data-stu-id="4d7e3-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="4d7e3-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span><span class="sxs-lookup"><span data-stu-id="4d7e3-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="4d7e3-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span><span class="sxs-lookup"><span data-stu-id="4d7e3-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="4d7e3-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span><span class="sxs-lookup"><span data-stu-id="4d7e3-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="4d7e3-110">The `Widening` keyword can be used in this context:</span><span class="sxs-lookup"><span data-stu-id="4d7e3-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="4d7e3-111">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="4d7e3-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="4d7e3-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4d7e3-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d7e3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d7e3-113">See also</span></span>

- [<span data-ttu-id="4d7e3-114">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="4d7e3-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="4d7e3-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="4d7e3-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="4d7e3-116">Conversioni di ampliamento e restrizione</span><span class="sxs-lookup"><span data-stu-id="4d7e3-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="4d7e3-117">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="4d7e3-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="4d7e3-118">Funzione CType</span><span class="sxs-lookup"><span data-stu-id="4d7e3-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="4d7e3-119">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="4d7e3-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="4d7e3-120">Procedura: Definire un operatore di conversione</span><span class="sxs-lookup"><span data-stu-id="4d7e3-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)

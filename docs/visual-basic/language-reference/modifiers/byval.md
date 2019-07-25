---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: abfe1489cb7e0d06b03c308e0704ce6f69ee55da
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433811"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="9c188-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c188-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="9c188-103">Specifica che un argomento viene passato [per valore](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), in modo che la routine o proprietà chiamata non possa modificare il valore di una variabile sottostante l'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="9c188-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="9c188-104">Se non si specifica alcun modificatore, ByVal è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="9c188-104">If no modifier is specified, ByVal is the default.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9c188-105">Note</span><span class="sxs-lookup"><span data-stu-id="9c188-105">Remarks</span></span>  
 <span data-ttu-id="9c188-106">Il modificatore `ByVal` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c188-106">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="9c188-107">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="9c188-107">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="9c188-108">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="9c188-108">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="9c188-109">Istruzione Operator</span><span class="sxs-lookup"><span data-stu-id="9c188-109">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="9c188-110">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="9c188-110">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="9c188-111">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="9c188-111">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="9c188-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9c188-112">Example</span></span>  
 <span data-ttu-id="9c188-113">Nell'esempio seguente viene illustrato l'utilizzo del `ByVal` meccanismo di passaggio del parametro con un argomento di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="9c188-113">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="9c188-114">Nell'esempio, l'argomento è `c1`, un'istanza della classe. `Class1`</span><span class="sxs-lookup"><span data-stu-id="9c188-114">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="9c188-115">`ByVal`impedisce al codice nelle procedure di modificare il valore sottostante dell'argomento di riferimento, `c1`, ma non protegge i campi e le proprietà accessibili di. `c1`</span><span class="sxs-lookup"><span data-stu-id="9c188-115">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="9c188-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c188-116">See also</span></span>

- [<span data-ttu-id="9c188-117">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="9c188-117">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="9c188-118">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="9c188-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)

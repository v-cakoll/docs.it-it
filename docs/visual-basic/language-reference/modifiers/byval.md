---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: c4cdafafa6bae3246c0512e28f94fde7e88d230b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373024"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="73515-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73515-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="73515-103">Specifica che un argomento viene passato [per valore](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), in modo che la routine o proprietà chiamata non possa modificare il valore di una variabile sottostante l'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="73515-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="73515-104">Se non si specifica alcun modificatore, ByVal è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="73515-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="73515-105">Poiché è l'impostazione predefinita, non è necessario specificare in modo esplicito la `ByVal` parola chiave nelle firme dei metodi.</span><span class="sxs-lookup"><span data-stu-id="73515-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="73515-106">Tende a produrre codice rumoroso e spesso conduce alla parola chiave non predefinita da `ByRef` trascurare.</span><span class="sxs-lookup"><span data-stu-id="73515-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="73515-107">Commenti</span><span class="sxs-lookup"><span data-stu-id="73515-107">Remarks</span></span>
 <span data-ttu-id="73515-108">Il modificatore `ByVal` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="73515-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="73515-109">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="73515-109">Declare Statement</span></span>](../statements/declare-statement.md)

 [<span data-ttu-id="73515-110">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="73515-110">Function Statement</span></span>](../statements/function-statement.md)
  
 [<span data-ttu-id="73515-111">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="73515-111">Operator Statement</span></span>](../statements/operator-statement.md)
  
 [<span data-ttu-id="73515-112">Property Statement</span><span class="sxs-lookup"><span data-stu-id="73515-112">Property Statement</span></span>](../statements/property-statement.md)
  
 [<span data-ttu-id="73515-113">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="73515-113">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="73515-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="73515-114">Example</span></span>
 <span data-ttu-id="73515-115">Nell'esempio seguente viene illustrato l'utilizzo del `ByVal` meccanismo di passaggio del parametro con un argomento di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="73515-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="73515-116">Nell'esempio, l'argomento è `c1` , un'istanza della classe `Class1` .</span><span class="sxs-lookup"><span data-stu-id="73515-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="73515-117">`ByVal`impedisce al codice nelle procedure di modificare il valore sottostante dell'argomento di riferimento, `c1` , ma non protegge i campi e le proprietà accessibili di `c1` .</span><span class="sxs-lookup"><span data-stu-id="73515-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="73515-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73515-118">See also</span></span>

- [<span data-ttu-id="73515-119">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="73515-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="73515-120">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="73515-120">Passing Arguments by Value and by Reference</span></span>](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)

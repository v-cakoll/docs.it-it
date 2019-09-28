---
title: Operatore &amp; = (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: 82d791e5d66c301442c99d2cc73e3172c3e30f17
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591633"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="6810d-102">Operatore &amp; = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6810d-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="6810d-103">Concatena un'espressione `String` a una variabile o una proprietà `String` e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="6810d-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6810d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6810d-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="6810d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="6810d-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="6810d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6810d-106">Required.</span></span> <span data-ttu-id="6810d-107">Qualsiasi variabile o proprietà `String`.</span><span class="sxs-lookup"><span data-stu-id="6810d-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="6810d-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="6810d-108">Required.</span></span> <span data-ttu-id="6810d-109">Qualsiasi espressione `String` .</span><span class="sxs-lookup"><span data-stu-id="6810d-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6810d-110">Note</span><span class="sxs-lookup"><span data-stu-id="6810d-110">Remarks</span></span>  
 <span data-ttu-id="6810d-111">L'elemento sul lato sinistro dell'operatore `&=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="6810d-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="6810d-112">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="6810d-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="6810d-113">L'operatore `&=` concatena l'espressione `String` a destra della variabile `String` o della proprietà a sinistra e assegna il risultato alla variabile o alla proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="6810d-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="6810d-114">Overload</span><span class="sxs-lookup"><span data-stu-id="6810d-114">Overloading</span></span>  
 <span data-ttu-id="6810d-115">L' [operatore &](../../../visual-basic/language-reference/operators/concatenation-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="6810d-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="6810d-116">L'overload dell'operatore `&` influiscono sul comportamento dell'operatore `&=`.</span><span class="sxs-lookup"><span data-stu-id="6810d-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="6810d-117">Se il codice USA `&=` su una classe o una struttura che esegue l'overload `&`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="6810d-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="6810d-118">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6810d-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6810d-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="6810d-119">Example</span></span>  
 <span data-ttu-id="6810d-120">Nell'esempio seguente viene usato l'operatore `&=` per concatenare due variabili `String` e assegnare il risultato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="6810d-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6810d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6810d-121">See also</span></span>

- [<span data-ttu-id="6810d-122">Operatore &</span><span class="sxs-lookup"><span data-stu-id="6810d-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="6810d-123">Operatore +=</span><span class="sxs-lookup"><span data-stu-id="6810d-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="6810d-124">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="6810d-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="6810d-125">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="6810d-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="6810d-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6810d-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="6810d-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="6810d-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="6810d-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="6810d-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)

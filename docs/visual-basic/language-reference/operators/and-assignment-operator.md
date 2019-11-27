---
title: Operatore &amp;=
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
ms.openlocfilehash: 8668bfcbf32bb34b422efe8116bbd12a2d80b1d4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350271"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="1c9f5-102">Operatore &amp;= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c9f5-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="1c9f5-103">Concatena un'espressione `String` a una variabile o una proprietà `String` e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c9f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c9f5-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="1c9f5-105">Parti</span><span class="sxs-lookup"><span data-stu-id="1c9f5-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="1c9f5-106">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-106">Required.</span></span> <span data-ttu-id="1c9f5-107">Qualsiasi `String` variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="1c9f5-108">Obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-108">Required.</span></span> <span data-ttu-id="1c9f5-109">Qualsiasi espressione `String` .</span><span class="sxs-lookup"><span data-stu-id="1c9f5-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c9f5-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1c9f5-110">Remarks</span></span>  
 <span data-ttu-id="1c9f5-111">L'elemento sul lato sinistro dell'operatore `&=` può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="1c9f5-112">La variabile o la proprietà non può essere di sola [lettura](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="1c9f5-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="1c9f5-113">L'operatore `&=` concatena l'espressione `String` a destra della variabile `String` o della proprietà a sinistra e assegna il risultato alla variabile o alla proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="1c9f5-114">Overload</span><span class="sxs-lookup"><span data-stu-id="1c9f5-114">Overloading</span></span>  
 <span data-ttu-id="1c9f5-115">L' [operatore &](../../../visual-basic/language-reference/operators/concatenation-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="1c9f5-116">L'overload dell'operatore `&` influiscono sul comportamento dell'operatore `&=`.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="1c9f5-117">Se il codice USA `&=` su una classe o una struttura che esegue l'overload di `&`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1c9f5-118">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1c9f5-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c9f5-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c9f5-119">Example</span></span>  
 <span data-ttu-id="1c9f5-120">Nell'esempio seguente viene usato l'operatore `&=` per concatenare due variabili `String` e assegnare il risultato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="1c9f5-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1c9f5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c9f5-121">See also</span></span>

- [<span data-ttu-id="1c9f5-122">Operatore &</span><span class="sxs-lookup"><span data-stu-id="1c9f5-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="1c9f5-123">Operatore +=</span><span class="sxs-lookup"><span data-stu-id="1c9f5-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="1c9f5-124">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="1c9f5-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="1c9f5-125">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="1c9f5-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="1c9f5-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c9f5-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="1c9f5-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="1c9f5-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="1c9f5-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="1c9f5-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)

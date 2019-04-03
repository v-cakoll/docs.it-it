---
title: '&amp;= Operatore (Visual Basic)'
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
ms.openlocfilehash: a79e779d8fcf549daeabc494e0a55deee30b5d22
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835466"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="da92d-102">&amp;= Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da92d-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="da92d-103">Concatena una `String` espressione da un `String` proprietà o variabile e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="da92d-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da92d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da92d-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="da92d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="da92d-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="da92d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="da92d-106">Required.</span></span> <span data-ttu-id="da92d-107">Qualsiasi `String` variabile o una proprietà.</span><span class="sxs-lookup"><span data-stu-id="da92d-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="da92d-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="da92d-108">Required.</span></span> <span data-ttu-id="da92d-109">Qualsiasi espressione `String` .</span><span class="sxs-lookup"><span data-stu-id="da92d-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da92d-110">Note</span><span class="sxs-lookup"><span data-stu-id="da92d-110">Remarks</span></span>  
 <span data-ttu-id="da92d-111">L'elemento sul lato sinistro del `&=` operatore può essere una variabile semplice scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="da92d-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="da92d-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="da92d-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="da92d-113">Il `&=` operatore consente di concatenare il `String` espressione alla sua destra per il `String` variabile o una proprietà alla sua sinistra e assegna il risultato alla variabile o proprietà alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="da92d-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="da92d-114">Overload</span><span class="sxs-lookup"><span data-stu-id="da92d-114">Overloading</span></span>  
 <span data-ttu-id="da92d-115">Il [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="da92d-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="da92d-116">L'overload di `&` operatore influisce sul comportamento del `&=` operatore.</span><span class="sxs-lookup"><span data-stu-id="da92d-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="da92d-117">Se il codice usi `&=` in una classe o struttura che esegue l'overload `&`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="da92d-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="da92d-118">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="da92d-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="da92d-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="da92d-119">Example</span></span>  
 <span data-ttu-id="da92d-120">L'esempio seguente usa il `&=` per concatenare due `String` variabili e assegna il risultato per la prima variabile.</span><span class="sxs-lookup"><span data-stu-id="da92d-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="da92d-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da92d-121">See also</span></span>

- [<span data-ttu-id="da92d-122">Operatore &</span><span class="sxs-lookup"><span data-stu-id="da92d-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="da92d-123">Operatore +=</span><span class="sxs-lookup"><span data-stu-id="da92d-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="da92d-124">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="da92d-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="da92d-125">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="da92d-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="da92d-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="da92d-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="da92d-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="da92d-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="da92d-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="da92d-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)

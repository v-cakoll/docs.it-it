---
title: Operatore IsTrue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 780e67cf54c0bec230d5b052b877cf97a76d3f6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641122"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="3eb29-102">Operatore IsTrue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3eb29-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="3eb29-103">Determina se un'espressione è `True`.</span><span class="sxs-lookup"><span data-stu-id="3eb29-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="3eb29-104">Non è possibile chiamare `IsTrue` in modo esplicito nel codice, ma Visual Basic compilatore può utilizzarlo per generare codice da `OrElse` clausole.</span><span class="sxs-lookup"><span data-stu-id="3eb29-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="3eb29-105">Se si definisce una classe o struttura e quindi usare una variabile di quel tipo in un `OrElse` clausola, è necessario definire `IsTrue` in quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="3eb29-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="3eb29-106">Il compilatore considera il `IsTrue` e `IsFalse` operatori come una *coppia associata*.</span><span class="sxs-lookup"><span data-stu-id="3eb29-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="3eb29-107">Ciò significa che se si definisce uno di essi, è necessario anche definire un'altra.</span><span class="sxs-lookup"><span data-stu-id="3eb29-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="3eb29-108">Uso del compilatore di IsTrue</span><span class="sxs-lookup"><span data-stu-id="3eb29-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="3eb29-109">Dopo aver definito una classe o struttura, è possibile usare una variabile di quel tipo in un `For`, `If`, `Else If`, o `While` istruzione o in un `When` clausola.</span><span class="sxs-lookup"><span data-stu-id="3eb29-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="3eb29-110">In questo caso, il compilatore richiede un operatore che converta il tipo in un `Boolean` valore in modo che è possibile testare una condizione.</span><span class="sxs-lookup"><span data-stu-id="3eb29-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="3eb29-111">La ricerca di un operatore appropriato nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="3eb29-111">It searches for a suitable operator in the following order:</span></span>  
  
1.  <span data-ttu-id="3eb29-112">Un operatore di conversione widening nella classe o struttura `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="3eb29-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2.  <span data-ttu-id="3eb29-113">Un operatore di conversione widening nella classe o struttura `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="3eb29-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3.  <span data-ttu-id="3eb29-114">Il `IsTrue` operatore sulla classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="3eb29-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4.  <span data-ttu-id="3eb29-115">Conversioni verso `Boolean?` che non comporta una conversione da `Boolean` a `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="3eb29-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5.  <span data-ttu-id="3eb29-116">Un operatore di conversione narrowing nella classe o struttura `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="3eb29-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="3eb29-117">Se non è stata definita alcuna conversione a `Boolean` o un `IsTrue` (operatore), il compilatore segnalerà un errore.</span><span class="sxs-lookup"><span data-stu-id="3eb29-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3eb29-118">Il `IsTrue` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="3eb29-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="3eb29-119">Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="3eb29-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3eb29-120">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="3eb29-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eb29-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="3eb29-121">Example</span></span>  
 <span data-ttu-id="3eb29-122">Esempio di codice seguente definisce la struttura di una struttura che include le definizioni per il `IsFalse` e `IsTrue` operatori.</span><span class="sxs-lookup"><span data-stu-id="3eb29-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3eb29-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eb29-123">See also</span></span>
- [<span data-ttu-id="3eb29-124">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="3eb29-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="3eb29-125">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="3eb29-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="3eb29-126">Operatore OrElse</span><span class="sxs-lookup"><span data-stu-id="3eb29-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)

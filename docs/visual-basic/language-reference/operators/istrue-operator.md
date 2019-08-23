---
title: Operatore IsTrue (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 1152f4b512a85ae183f8fc8d476b69685e2926ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966924"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="f56e0-102">Operatore IsTrue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f56e0-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="f56e0-103">Determina se un'espressione è `True`.</span><span class="sxs-lookup"><span data-stu-id="f56e0-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="f56e0-104">Non è possibile `IsTrue` chiamare in modo esplicito nel codice, ma il compilatore Visual Basic può usarlo per generare `OrElse` codice da clausole.</span><span class="sxs-lookup"><span data-stu-id="f56e0-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="f56e0-105">Se si definisce una classe o una struttura e quindi si usa una variabile di quel tipo `OrElse` in una clausola, è `IsTrue` necessario definire su tale classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="f56e0-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="f56e0-106">Il compilatore considera gli `IsTrue` operatori `IsFalse` e come una *coppia corrispondente*.</span><span class="sxs-lookup"><span data-stu-id="f56e0-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="f56e0-107">Ciò significa che se si definisce uno di essi, è necessario definire anche l'altro.</span><span class="sxs-lookup"><span data-stu-id="f56e0-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="f56e0-108">Uso del compilatore di IsTrue</span><span class="sxs-lookup"><span data-stu-id="f56e0-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="f56e0-109">Una volta definita una classe o una struttura, è possibile utilizzare una variabile di quel tipo in un' `For`istruzione `If`, `Else If`, o `While` o in una `When` clausola.</span><span class="sxs-lookup"><span data-stu-id="f56e0-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="f56e0-110">In tal caso, il compilatore richiede un operatore che converte il tipo in un `Boolean` valore in modo che possa testare una condizione.</span><span class="sxs-lookup"><span data-stu-id="f56e0-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="f56e0-111">Cerca un operatore appropriato nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="f56e0-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="f56e0-112">Un operatore di conversione verso un tipo di dati più ampio `Boolean`dalla classe o dalla struttura a.</span><span class="sxs-lookup"><span data-stu-id="f56e0-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="f56e0-113">Un operatore di conversione verso un tipo di dati più ampio `Boolean?`dalla classe o dalla struttura a.</span><span class="sxs-lookup"><span data-stu-id="f56e0-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="f56e0-114">`IsTrue` Operatore sulla classe o sulla struttura.</span><span class="sxs-lookup"><span data-stu-id="f56e0-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="f56e0-115">Una conversione verso un tipo `Boolean?` di caratteri più piccolo non comporta una `Boolean` conversione `Boolean?`da a.</span><span class="sxs-lookup"><span data-stu-id="f56e0-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="f56e0-116">Operatore di conversione verso un tipo di dati più piccolo dalla `Boolean`classe o dalla struttura a.</span><span class="sxs-lookup"><span data-stu-id="f56e0-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="f56e0-117">Se non è stata definita alcuna conversione a `Boolean` o a `IsTrue` un operatore, il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="f56e0-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f56e0-118">L' `IsTrue` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="f56e0-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="f56e0-119">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="f56e0-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f56e0-120">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f56e0-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f56e0-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="f56e0-121">Example</span></span>  
 <span data-ttu-id="f56e0-122">Nell'esempio di codice seguente viene definita la struttura di una struttura che include definizioni `IsFalse` per `IsTrue` gli operatori e.</span><span class="sxs-lookup"><span data-stu-id="f56e0-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="f56e0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f56e0-123">See also</span></span>

- [<span data-ttu-id="f56e0-124">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="f56e0-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="f56e0-125">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="f56e0-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="f56e0-126">Operatore OrElse</span><span class="sxs-lookup"><span data-stu-id="f56e0-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)

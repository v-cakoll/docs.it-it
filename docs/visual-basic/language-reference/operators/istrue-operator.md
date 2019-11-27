---
title: Operatore IsTrue
ms.date: 07/20/2015
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
ms.openlocfilehash: 4b863eed8406a10b9a44d7139f8659ac5cb758ad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349507"
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="1ea15-102">Operatore IsTrue (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ea15-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="1ea15-103">Determina se un'espressione viene `True`.</span><span class="sxs-lookup"><span data-stu-id="1ea15-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="1ea15-104">Non è possibile chiamare `IsTrue` in modo esplicito nel codice, ma il compilatore Visual Basic può usarlo per generare codice da `OrElse` clausole.</span><span class="sxs-lookup"><span data-stu-id="1ea15-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="1ea15-105">Se si definisce una classe o una struttura e quindi si usa una variabile di quel tipo in una clausola `OrElse`, è necessario definire `IsTrue` sulla classe o sulla struttura.</span><span class="sxs-lookup"><span data-stu-id="1ea15-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="1ea15-106">Il compilatore considera gli operatori `IsTrue` e `IsFalse` come *coppia corrispondente*.</span><span class="sxs-lookup"><span data-stu-id="1ea15-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="1ea15-107">Ciò significa che se si definisce uno di essi, è necessario definire anche l'altro.</span><span class="sxs-lookup"><span data-stu-id="1ea15-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="1ea15-108">Uso del compilatore di IsTrue</span><span class="sxs-lookup"><span data-stu-id="1ea15-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="1ea15-109">Una volta definita una classe o una struttura, è possibile usare una variabile di quel tipo in un'istruzione `For`, `If`, `Else If`o `While` oppure in una clausola `When`.</span><span class="sxs-lookup"><span data-stu-id="1ea15-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="1ea15-110">In tal caso, il compilatore richiede un operatore che converte il tipo in un valore `Boolean` in modo che possa testare una condizione.</span><span class="sxs-lookup"><span data-stu-id="1ea15-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="1ea15-111">Cerca un operatore appropriato nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="1ea15-111">It searches for a suitable operator in the following order:</span></span>  
  
1. <span data-ttu-id="1ea15-112">Un operatore di conversione verso un tipo di dati più ampio dalla classe o dalla struttura `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="1ea15-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2. <span data-ttu-id="1ea15-113">Un operatore di conversione verso un tipo di dati più ampio dalla classe o dalla struttura `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="1ea15-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3. <span data-ttu-id="1ea15-114">Operatore `IsTrue` sulla classe o sulla struttura.</span><span class="sxs-lookup"><span data-stu-id="1ea15-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4. <span data-ttu-id="1ea15-115">Una conversione verso un tipo di `Boolean?` più piccolo che non comporta una conversione da `Boolean` a `Boolean?`.</span><span class="sxs-lookup"><span data-stu-id="1ea15-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5. <span data-ttu-id="1ea15-116">Operatore di conversione verso un tipo di dati più piccolo dalla classe o dalla struttura `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="1ea15-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="1ea15-117">Se non è stata definita alcuna conversione a `Boolean` o a un operatore `IsTrue`, il compilatore segnala un errore.</span><span class="sxs-lookup"><span data-stu-id="1ea15-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ea15-118">L'operatore `IsTrue` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="1ea15-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="1ea15-119">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="1ea15-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="1ea15-120">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1ea15-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ea15-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ea15-121">Example</span></span>  
 <span data-ttu-id="1ea15-122">Nell'esempio di codice seguente viene definita la struttura di una struttura che include definizioni per gli operatori `IsFalse` e `IsTrue`.</span><span class="sxs-lookup"><span data-stu-id="1ea15-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="1ea15-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ea15-123">See also</span></span>

- [<span data-ttu-id="1ea15-124">Operatore IsFalse</span><span class="sxs-lookup"><span data-stu-id="1ea15-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="1ea15-125">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="1ea15-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="1ea15-126">Operatore OrElse</span><span class="sxs-lookup"><span data-stu-id="1ea15-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)

---
title: Operatore IsFalse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 85fd6b9264fa80c3636f2cb839c8fc5ed855ddc8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965657"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="8c830-102">Operatore IsFalse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c830-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="8c830-103">Determina se un'espressione è `False`.</span><span class="sxs-lookup"><span data-stu-id="8c830-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="8c830-104">Non è possibile chiamare `IsFalse` in modo esplicito nel codice, ma Visual Basic compilatore può utilizzarlo per generare codice da `AndAlso` clausole.</span><span class="sxs-lookup"><span data-stu-id="8c830-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="8c830-105">Se si definisce una classe o struttura e quindi usare una variabile di quel tipo in un `AndAlso` clausola, è necessario definire `IsFalse` in quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="8c830-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="8c830-106">Il compilatore considera il `IsFalse` e `IsTrue` operatori come una *coppia associata*.</span><span class="sxs-lookup"><span data-stu-id="8c830-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="8c830-107">Ciò significa che se si definisce uno di essi, è necessario anche definire un'altra.</span><span class="sxs-lookup"><span data-stu-id="8c830-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c830-108">Il `IsFalse` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="8c830-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="8c830-109">Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="8c830-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="8c830-110">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="8c830-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c830-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c830-111">Example</span></span>  
 <span data-ttu-id="8c830-112">Esempio di codice seguente definisce la struttura di una struttura che include le definizioni per il `IsFalse` e `IsTrue` operatori.</span><span class="sxs-lookup"><span data-stu-id="8c830-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="8c830-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c830-113">See also</span></span>
- [<span data-ttu-id="8c830-114">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="8c830-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="8c830-115">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="8c830-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="8c830-116">Operatore AndAlso</span><span class="sxs-lookup"><span data-stu-id="8c830-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)

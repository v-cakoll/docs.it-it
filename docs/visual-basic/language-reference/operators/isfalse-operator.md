---
title: Operatore IsFalse (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 49b8493575685a220808df1522ce16835b3ce0ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917148"
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="cb016-102">Operatore IsFalse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb016-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="cb016-103">Determina se un'espressione è `False`.</span><span class="sxs-lookup"><span data-stu-id="cb016-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="cb016-104">Non è possibile `IsFalse` chiamare in modo esplicito nel codice, ma il compilatore Visual Basic può usarlo per generare `AndAlso` codice da clausole.</span><span class="sxs-lookup"><span data-stu-id="cb016-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="cb016-105">Se si definisce una classe o una struttura e quindi si usa una variabile di quel tipo `AndAlso` in una clausola, è `IsFalse` necessario definire su tale classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="cb016-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="cb016-106">Il compilatore considera gli `IsFalse` operatori `IsTrue` e come una *coppia corrispondente*.</span><span class="sxs-lookup"><span data-stu-id="cb016-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="cb016-107">Ciò significa che se si definisce uno di essi, è necessario definire anche l'altro.</span><span class="sxs-lookup"><span data-stu-id="cb016-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb016-108">L' `IsFalse` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="cb016-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="cb016-109">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="cb016-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="cb016-110">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="cb016-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb016-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb016-111">Example</span></span>  
 <span data-ttu-id="cb016-112">Nell'esempio di codice seguente viene definita la struttura di una struttura che include definizioni `IsFalse` per `IsTrue` gli operatori e.</span><span class="sxs-lookup"><span data-stu-id="cb016-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="cb016-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb016-113">See also</span></span>

- [<span data-ttu-id="cb016-114">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="cb016-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="cb016-115">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="cb016-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="cb016-116">Operatore AndAlso</span><span class="sxs-lookup"><span data-stu-id="cb016-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)

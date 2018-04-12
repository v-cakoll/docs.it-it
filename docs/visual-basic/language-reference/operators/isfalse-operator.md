---
title: Operatore IsFalse (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d85fc51a75f82c65cf226b8239a8eee6585bd18a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="746cf-102">Operatore IsFalse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="746cf-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="746cf-103">Determina se un'espressione è `False`.</span><span class="sxs-lookup"><span data-stu-id="746cf-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="746cf-104">Non è possibile chiamare `IsFalse` in modo esplicito nel codice, ma Visual Basic compilatore può utilizzarlo per generare codice da `AndAlso` clausole.</span><span class="sxs-lookup"><span data-stu-id="746cf-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="746cf-105">Se si definisce una classe o struttura e quindi utilizzare una variabile di quel tipo in un `AndAlso` clausola, è necessario definire `IsFalse` in quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="746cf-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="746cf-106">Il compilatore considera il `IsFalse` e `IsTrue` operatori come un *coppia associata*.</span><span class="sxs-lookup"><span data-stu-id="746cf-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="746cf-107">Ciò significa che se si definisce uno di essi, è inoltre necessario definire un'altra.</span><span class="sxs-lookup"><span data-stu-id="746cf-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="746cf-108">Il `IsFalse` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando l'operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="746cf-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="746cf-109">Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="746cf-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="746cf-110">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="746cf-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="746cf-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="746cf-111">Example</span></span>  
 <span data-ttu-id="746cf-112">Esempio di codice seguente definisce la struttura di una struttura che include le definizioni per il `IsFalse` e `IsTrue` operatori.</span><span class="sxs-lookup"><span data-stu-id="746cf-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="746cf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="746cf-113">See Also</span></span>  
 [<span data-ttu-id="746cf-114">Operatore IsTrue</span><span class="sxs-lookup"><span data-stu-id="746cf-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="746cf-115">Procedura: Definire un operatore</span><span class="sxs-lookup"><span data-stu-id="746cf-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="746cf-116">Operatore AndAlso</span><span class="sxs-lookup"><span data-stu-id="746cf-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)

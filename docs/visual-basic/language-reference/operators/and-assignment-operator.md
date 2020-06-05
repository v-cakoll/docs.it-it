---
title: '&amp;= (Operatore)'
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
ms.openlocfilehash: db42f7be7225b866eacf5b73066754e91cd1a0f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371986"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="9fda2-102">&amp;Operatore = (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9fda2-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="9fda2-103">Concatena un' `String` espressione a una `String` variabile o a una proprietà e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="9fda2-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fda2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fda2-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="9fda2-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9fda2-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="9fda2-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9fda2-106">Required.</span></span> <span data-ttu-id="9fda2-107">Qualsiasi `String` variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="9fda2-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="9fda2-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9fda2-108">Required.</span></span> <span data-ttu-id="9fda2-109">Qualsiasi espressione `String` .</span><span class="sxs-lookup"><span data-stu-id="9fda2-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fda2-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="9fda2-110">Remarks</span></span>  
 <span data-ttu-id="9fda2-111">L'elemento sul lato sinistro dell' `&=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="9fda2-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="9fda2-112">La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="9fda2-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span> <span data-ttu-id="9fda2-113">L' `&=` operatore concatena l' `String` espressione a destra della `String` variabile o della proprietà a sinistra e assegna il risultato alla variabile o alla proprietà a sinistra.</span><span class="sxs-lookup"><span data-stu-id="9fda2-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="9fda2-114">Overload</span><span class="sxs-lookup"><span data-stu-id="9fda2-114">Overloading</span></span>  
 <span data-ttu-id="9fda2-115">L' [operatore&](concatenation-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="9fda2-115">The [& Operator](concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9fda2-116">L'overload dell' `&` operatore influiscono sul comportamento dell' `&=` operatore.</span><span class="sxs-lookup"><span data-stu-id="9fda2-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="9fda2-117">Se il codice usa `&=` su una classe o una struttura che esegue l'overload di `&` , assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="9fda2-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9fda2-118">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9fda2-118">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fda2-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="9fda2-119">Example</span></span>  
 <span data-ttu-id="9fda2-120">Nell'esempio seguente viene usato l' `&=` operatore per concatenare due `String` variabili e assegnare il risultato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="9fda2-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9fda2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fda2-121">See also</span></span>

- [<span data-ttu-id="9fda2-122">Operatore&</span><span class="sxs-lookup"><span data-stu-id="9fda2-122">& Operator</span></span>](concatenation-operator.md)
- [<span data-ttu-id="9fda2-123">Operatore + =</span><span class="sxs-lookup"><span data-stu-id="9fda2-123">+= Operator</span></span>](addition-assignment-operator.md)
- [<span data-ttu-id="9fda2-124">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="9fda2-124">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="9fda2-125">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="9fda2-125">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="9fda2-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9fda2-126">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="9fda2-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="9fda2-127">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="9fda2-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="9fda2-128">Statements</span></span>](../../programming-guide/language-features/statements.md)

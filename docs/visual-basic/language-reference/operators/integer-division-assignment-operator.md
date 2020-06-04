---
title: Operatore \=
ms.date: 07/20/2015
f1_keywords:
- '\='
- vb.\=
helpviewer_keywords:
- '\= operator [Visual Basic]'
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator \= [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 6f39915d-e398-4045-afcc-da6885e57b9c
ms.openlocfilehash: a546d8b0c9b3852386970f80d3da96794da2351c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370947"
---
# <a name="-operator"></a><span data-ttu-id="a7983-102">\\= (Operatore)</span><span class="sxs-lookup"><span data-stu-id="a7983-102">\\= Operator</span></span>
<span data-ttu-id="a7983-103">Divide il valore di una variabile o di una proprietà in base al valore di un'espressione e assegna il risultato Integer alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="a7983-103">Divides the value of a variable or property by the value of an expression and assigns the integer result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7983-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7983-104">Syntax</span></span>  
  
```vb  
variableorproperty \= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a7983-105">Parti</span><span class="sxs-lookup"><span data-stu-id="a7983-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a7983-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a7983-106">Required.</span></span> <span data-ttu-id="a7983-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="a7983-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a7983-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a7983-108">Required.</span></span> <span data-ttu-id="a7983-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="a7983-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7983-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="a7983-110">Remarks</span></span>  
 <span data-ttu-id="a7983-111">L'elemento sul lato sinistro dell' `\=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="a7983-111">The element on the left side of the `\=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a7983-112">La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="a7983-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a7983-113">L' `\=` operatore divide il valore di una variabile o di una proprietà a sinistra del valore a destra e assegna il risultato Integer alla variabile o alla proprietà a sinistra</span><span class="sxs-lookup"><span data-stu-id="a7983-113">The `\=` operator divides the value of a variable or property on its left by the value on its right, and assigns the integer result to the variable or property on its left</span></span>  
  
 <span data-ttu-id="a7983-114">Per ulteriori informazioni sulla divisione di interi, vedere [\ operator (Visual Basic)](integer-division-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a7983-114">For further information on integer division, see [\ Operator (Visual Basic)](integer-division-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a7983-115">Overload</span><span class="sxs-lookup"><span data-stu-id="a7983-115">Overloading</span></span>  
 <span data-ttu-id="a7983-116">L' `\` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="a7983-116">The `\` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a7983-117">L'overload dell' `\` operatore influiscono sul comportamento dell' `\=` operatore.</span><span class="sxs-lookup"><span data-stu-id="a7983-117">Overloading the `\` operator affects the behavior of the `\=` operator.</span></span> <span data-ttu-id="a7983-118">Se il codice usa `\=` su una classe o una struttura che esegue l'overload di `\` , assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="a7983-118">If your code uses `\=` on a class or structure that overloads `\`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a7983-119">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a7983-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7983-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="a7983-120">Example</span></span>  
 <span data-ttu-id="a7983-121">Nell'esempio seguente viene usato l' `\=` operatore per dividere una `Integer` variabile per secondo e assegnare il risultato Integer alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="a7983-121">The following example uses the `\=` operator to divide one `Integer` variable by a second and assign the integer result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="a7983-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7983-122">See also</span></span>

- [<span data-ttu-id="a7983-123">Operatore \ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7983-123">\ Operator (Visual Basic)</span></span>](integer-division-operator.md)
- [<span data-ttu-id="a7983-124">Operatore /= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7983-124">/= Operator (Visual Basic)</span></span>](floating-point-division-assignment-operator.md)
- [<span data-ttu-id="a7983-125">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="a7983-125">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="a7983-126">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="a7983-126">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="a7983-127">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7983-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="a7983-128">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="a7983-128">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="a7983-129">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="a7983-129">Statements</span></span>](../../programming-guide/language-features/statements.md)

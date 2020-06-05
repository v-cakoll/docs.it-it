---
title: Operatore ^=
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: e631cc9a484b56ee059449ca1fbd9fc69405333d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371401"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="663ba-102">Operatore ^= (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="663ba-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="663ba-103">Genera il valore di una variabile o di una proprietà alla potenza di un'espressione e assegna il risultato alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="663ba-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="663ba-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="663ba-105">Parti</span><span class="sxs-lookup"><span data-stu-id="663ba-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="663ba-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="663ba-106">Required.</span></span> <span data-ttu-id="663ba-107">Qualsiasi variabile o proprietà numerica.</span><span class="sxs-lookup"><span data-stu-id="663ba-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="663ba-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="663ba-108">Required.</span></span> <span data-ttu-id="663ba-109">Qualsiasi espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="663ba-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="663ba-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="663ba-110">Remarks</span></span>  
 <span data-ttu-id="663ba-111">L'elemento sul lato sinistro dell' `^=` operatore può essere una variabile scalare semplice, una proprietà o un elemento di una matrice.</span><span class="sxs-lookup"><span data-stu-id="663ba-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="663ba-112">La variabile o la proprietà non può essere di sola [lettura](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="663ba-112">The variable or property cannot be [ReadOnly](../modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="663ba-113">L' `^=` operatore eleva prima di tutto il valore della variabile o della proprietà (sul lato sinistro dell'operatore) alla potenza del valore dell'espressione (sul lato destro dell'operatore).</span><span class="sxs-lookup"><span data-stu-id="663ba-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="663ba-114">L'operatore assegna quindi il risultato dell'operazione alla variabile o alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="663ba-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="663ba-115">Visual Basic esegue sempre l'elevamento a potenza nel [tipo di dati Double](../data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="663ba-115">Visual Basic always performs exponentiation in the [Double Data Type](../data-types/double-data-type.md).</span></span> <span data-ttu-id="663ba-116">Gli operandi di qualsiasi tipo diverso vengono convertiti in `Double` e il risultato è sempre `Double` .</span><span class="sxs-lookup"><span data-stu-id="663ba-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="663ba-117">Il valore di `expression` può essere frazionario, negativo o entrambi.</span><span class="sxs-lookup"><span data-stu-id="663ba-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="663ba-118">Overload</span><span class="sxs-lookup"><span data-stu-id="663ba-118">Overloading</span></span>  
 <span data-ttu-id="663ba-119">L' [operatore ^](exponentiation-operator.md) può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="663ba-119">The [^ Operator](exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="663ba-120">L'overload dell' `^` operatore influiscono sul comportamento dell' `^=` operatore.</span><span class="sxs-lookup"><span data-stu-id="663ba-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="663ba-121">Se il codice usa `^=` su una classe o una struttura che esegue l'overload di `^` , assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="663ba-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="663ba-122">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="663ba-122">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="663ba-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="663ba-123">Example</span></span>  
 <span data-ttu-id="663ba-124">Nell'esempio seguente viene usato l' `^=` operatore per aumentare il valore di una `Integer` variabile alla potenza di una seconda variabile e assegnare il risultato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="663ba-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="663ba-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="663ba-125">See also</span></span>

- [<span data-ttu-id="663ba-126">Operatore ^</span><span class="sxs-lookup"><span data-stu-id="663ba-126">^ Operator</span></span>](exponentiation-operator.md)
- [<span data-ttu-id="663ba-127">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="663ba-127">Assignment Operators</span></span>](assignment-operators.md)
- [<span data-ttu-id="663ba-128">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="663ba-128">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="663ba-129">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="663ba-129">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="663ba-130">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="663ba-130">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="663ba-131">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="663ba-131">Statements</span></span>](../../programming-guide/language-features/statements.md)

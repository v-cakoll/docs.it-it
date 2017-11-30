---
title: '&amp;= Operatore (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 929a9e8c3384451679fc52ad478eb03219d67192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="40cc1-102">&amp;= Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40cc1-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="40cc1-103">Concatena una `String` espressione da un `String` variabile o proprietà e assegna il risultato alla variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="40cc1-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40cc1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40cc1-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="40cc1-105">Parti</span><span class="sxs-lookup"><span data-stu-id="40cc1-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="40cc1-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="40cc1-106">Required.</span></span> <span data-ttu-id="40cc1-107">Qualsiasi `String` variabile o proprietà.</span><span class="sxs-lookup"><span data-stu-id="40cc1-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="40cc1-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="40cc1-108">Required.</span></span> <span data-ttu-id="40cc1-109">Qualsiasi espressione `String`.</span><span class="sxs-lookup"><span data-stu-id="40cc1-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40cc1-110">Note</span><span class="sxs-lookup"><span data-stu-id="40cc1-110">Remarks</span></span>  
 <span data-ttu-id="40cc1-111">L'elemento sul lato sinistro del `&=` operatore può essere una semplice variabile scalare, una proprietà o un elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="40cc1-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="40cc1-112">La variabile o proprietà non può essere [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="40cc1-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="40cc1-113">Il `&=` operatore concatena il `String` espressione alla sua destra per il `String` variabile o proprietà alla sua sinistra e assegna il risultato alla variabile o proprietà alla sua sinistra.</span><span class="sxs-lookup"><span data-stu-id="40cc1-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="40cc1-114">Overload</span><span class="sxs-lookup"><span data-stu-id="40cc1-114">Overloading</span></span>  
 <span data-ttu-id="40cc1-115">Il [& operatore](../../../visual-basic/language-reference/operators/concatenation-operator.md) può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="40cc1-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="40cc1-116">L'overload di `&` operatore influisce sul comportamento del `&=` operatore.</span><span class="sxs-lookup"><span data-stu-id="40cc1-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="40cc1-117">Se il codice utilizza `&=` in una classe o struttura che esegue l'overload `&`, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="40cc1-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="40cc1-118">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="40cc1-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="40cc1-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="40cc1-119">Example</span></span>  
 <span data-ttu-id="40cc1-120">L'esempio seguente usa il `&=` per concatenare due `String` variabili e assegnare il risultato alla prima variabile.</span><span class="sxs-lookup"><span data-stu-id="40cc1-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="40cc1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40cc1-121">See Also</span></span>  
 [<span data-ttu-id="40cc1-122">Operatore &</span><span class="sxs-lookup"><span data-stu-id="40cc1-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [<span data-ttu-id="40cc1-123">Operatore +=</span><span class="sxs-lookup"><span data-stu-id="40cc1-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="40cc1-124">Operatori di assegnazione</span><span class="sxs-lookup"><span data-stu-id="40cc1-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="40cc1-125">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="40cc1-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="40cc1-126">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40cc1-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="40cc1-127">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="40cc1-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="40cc1-128">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="40cc1-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)

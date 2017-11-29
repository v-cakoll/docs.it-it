---
title: '&amp;Operatore (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76c8fc52a518dfe7850a5680b7d4f06f3d09bf73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="13af8-102">&amp;Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13af8-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="13af8-103">Genera una concatenazione di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="13af8-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13af8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13af8-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="13af8-105">Parti</span><span class="sxs-lookup"><span data-stu-id="13af8-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="13af8-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="13af8-106">Required.</span></span> <span data-ttu-id="13af8-107">Qualsiasi `String` o `Object` variabile.</span><span class="sxs-lookup"><span data-stu-id="13af8-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="13af8-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="13af8-108">Required.</span></span> <span data-ttu-id="13af8-109">Qualsiasi espressione con un tipo di dati che si amplia in `String`.</span><span class="sxs-lookup"><span data-stu-id="13af8-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="13af8-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="13af8-110">Required.</span></span> <span data-ttu-id="13af8-111">Qualsiasi espressione con un tipo di dati che si amplia in `String`.</span><span class="sxs-lookup"><span data-stu-id="13af8-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13af8-112">Note</span><span class="sxs-lookup"><span data-stu-id="13af8-112">Remarks</span></span>  
 <span data-ttu-id="13af8-113">Se il tipo di dati `expression1` o `expression2` non `String` ma si amplia in `String`, viene convertito in `String`.</span><span class="sxs-lookup"><span data-stu-id="13af8-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="13af8-114">Se uno dei tipi di dati si amplia in `String`, il compilatore genera un errore.</span><span class="sxs-lookup"><span data-stu-id="13af8-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="13af8-115">Il tipo di dati `result` è `String`.</span><span class="sxs-lookup"><span data-stu-id="13af8-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="13af8-116">Se una o entrambe le espressioni restituiscono [nulla](../../../visual-basic/language-reference/nothing.md) o hanno un valore di <xref:System.DBNull.Value?displayProperty=nameWithType>, vengono considerate come una stringa con un valore di "".</span><span class="sxs-lookup"><span data-stu-id="13af8-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13af8-117">Il `&` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="13af8-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="13af8-118">Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="13af8-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="13af8-119">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="13af8-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13af8-120">Il carattere e commerciale (&) consente inoltre di identificare le variabili di tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="13af8-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="13af8-121">Per ulteriori informazioni, vedere [caratteri di tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="13af8-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="13af8-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="13af8-122">Example</span></span>  
 <span data-ttu-id="13af8-123">Questo esempio viene utilizzato il `&` operatore per forzare la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="13af8-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="13af8-124">Il risultato è un valore stringa che rappresenta la concatenazione ai due operandi stringa.</span><span class="sxs-lookup"><span data-stu-id="13af8-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="13af8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13af8-125">See Also</span></span>  
 [<span data-ttu-id="13af8-126">Operatore &=</span><span class="sxs-lookup"><span data-stu-id="13af8-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="13af8-127">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="13af8-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="13af8-128">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13af8-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="13af8-129">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="13af8-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="13af8-130">Operatori di concatenazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13af8-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)

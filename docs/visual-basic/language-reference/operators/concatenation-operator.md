---
title: '&amp; Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 28d8cdb22974d77edf055ab9b2c6c767872e6783
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604302"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="9ca8d-102">&amp; Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ca8d-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="9ca8d-103">Genera una concatenazione di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ca8d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ca8d-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="9ca8d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9ca8d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="9ca8d-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-106">Required.</span></span> <span data-ttu-id="9ca8d-107">Qualsiasi `String` o `Object` variabile.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="9ca8d-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-108">Required.</span></span> <span data-ttu-id="9ca8d-109">Qualsiasi espressione con un tipo di dati che si amplia in `String`.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="9ca8d-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-110">Required.</span></span> <span data-ttu-id="9ca8d-111">Qualsiasi espressione con un tipo di dati che si amplia in `String`.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ca8d-112">Note</span><span class="sxs-lookup"><span data-stu-id="9ca8d-112">Remarks</span></span>  
 <span data-ttu-id="9ca8d-113">Se il tipo di dati `expression1` o `expression2` non `String` ma si amplia in `String`, viene convertito in `String`.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="9ca8d-114">Se uno dei tipi di dati si amplia in `String`, il compilatore genera un errore.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="9ca8d-115">Il tipo di dati `result` è `String`.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="9ca8d-116">Se una o entrambe le espressioni restituiscono [nulla](../../../visual-basic/language-reference/nothing.md) o hanno un valore di <xref:System.DBNull.Value?displayProperty=nameWithType>, vengono considerate come una stringa con un valore di "".</span><span class="sxs-lookup"><span data-stu-id="9ca8d-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ca8d-117">Il `&` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9ca8d-118">Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9ca8d-119">Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9ca8d-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ca8d-120">Il carattere e commerciale (&) consente inoltre di identificare le variabili di tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="9ca8d-121">Per ulteriori informazioni, vedere [caratteri di tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="9ca8d-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ca8d-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ca8d-122">Example</span></span>  
 <span data-ttu-id="9ca8d-123">Questo esempio viene utilizzato il `&` operatore per forzare la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="9ca8d-124">Il risultato è un valore stringa che rappresenta la concatenazione ai due operandi stringa.</span><span class="sxs-lookup"><span data-stu-id="9ca8d-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9ca8d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ca8d-125">See Also</span></span>  
 [<span data-ttu-id="9ca8d-126">Operatore &=</span><span class="sxs-lookup"><span data-stu-id="9ca8d-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="9ca8d-127">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="9ca8d-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="9ca8d-128">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ca8d-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="9ca8d-129">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="9ca8d-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="9ca8d-130">Operatori di concatenazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ca8d-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)

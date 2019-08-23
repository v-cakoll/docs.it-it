---
title: '&amp;Operatore (Visual Basic)'
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
ms.openlocfilehash: d387b2dfdbb3fefe357364f7b2a3dde155cbd489
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968346"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="9d28d-102">&amp;Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d28d-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="9d28d-103">Genera una concatenazione di stringhe di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="9d28d-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d28d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d28d-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="9d28d-105">Parti</span><span class="sxs-lookup"><span data-stu-id="9d28d-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="9d28d-106">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="9d28d-106">Required.</span></span> <span data-ttu-id="9d28d-107">Qualsiasi `String` variabile `Object` o.</span><span class="sxs-lookup"><span data-stu-id="9d28d-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="9d28d-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="9d28d-108">Required.</span></span> <span data-ttu-id="9d28d-109">Qualsiasi espressione con un tipo di dati che si allarga `String`a.</span><span class="sxs-lookup"><span data-stu-id="9d28d-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="9d28d-110">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="9d28d-110">Required.</span></span> <span data-ttu-id="9d28d-111">Qualsiasi espressione con un tipo di dati che si allarga `String`a.</span><span class="sxs-lookup"><span data-stu-id="9d28d-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d28d-112">Note</span><span class="sxs-lookup"><span data-stu-id="9d28d-112">Remarks</span></span>  
 <span data-ttu-id="9d28d-113">Se il tipo di dati `expression1` di `expression2` o non `String` è ma si allarga `String`a, viene convertito in `String`.</span><span class="sxs-lookup"><span data-stu-id="9d28d-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="9d28d-114">Se uno dei tipi di dati non viene ampliato `String`a, il compilatore genera un errore.</span><span class="sxs-lookup"><span data-stu-id="9d28d-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="9d28d-115">Il tipo di dati `result` di `String`è.</span><span class="sxs-lookup"><span data-stu-id="9d28d-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="9d28d-116">Se una o entrambe le espressioni restituiscono [Nothing](../../../visual-basic/language-reference/nothing.md) o hanno un valore <xref:System.DBNull.Value?displayProperty=nameWithType>, vengono considerate come una stringa con un valore di "".</span><span class="sxs-lookup"><span data-stu-id="9d28d-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d28d-117">L' `&` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="9d28d-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="9d28d-118">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="9d28d-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="9d28d-119">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9d28d-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d28d-120">Il carattere e commerciale (&) può essere usato anche per identificare le variabili `Long`come tipo.</span><span class="sxs-lookup"><span data-stu-id="9d28d-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="9d28d-121">Per ulteriori informazioni, vedere [caratteri di tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="9d28d-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d28d-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="9d28d-122">Example</span></span>  
 <span data-ttu-id="9d28d-123">In questo esempio viene `&` usato l'operatore per forzare la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="9d28d-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="9d28d-124">Il risultato è un valore stringa che rappresenta la concatenazione dei due operandi di stringa.</span><span class="sxs-lookup"><span data-stu-id="9d28d-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9d28d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d28d-125">See also</span></span>

- [<span data-ttu-id="9d28d-126">Operatore &=</span><span class="sxs-lookup"><span data-stu-id="9d28d-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="9d28d-127">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="9d28d-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="9d28d-128">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d28d-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="9d28d-129">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="9d28d-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="9d28d-130">Operatori di concatenazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d28d-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)

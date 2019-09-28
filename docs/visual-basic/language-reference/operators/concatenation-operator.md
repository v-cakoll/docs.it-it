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
ms.openlocfilehash: aaa7c1b9ab7f6c920180d97b55c3bdeb23f00e02
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592238"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="197f6-102">&amp;Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="197f6-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="197f6-103">Genera una concatenazione di stringhe di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="197f6-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="197f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="197f6-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="197f6-105">Parti</span><span class="sxs-lookup"><span data-stu-id="197f6-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="197f6-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="197f6-106">Required.</span></span> <span data-ttu-id="197f6-107">Qualsiasi variabile `String` o `Object`.</span><span class="sxs-lookup"><span data-stu-id="197f6-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="197f6-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="197f6-108">Required.</span></span> <span data-ttu-id="197f6-109">Qualsiasi espressione con un tipo di dati che si allarga a `String`.</span><span class="sxs-lookup"><span data-stu-id="197f6-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="197f6-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="197f6-110">Required.</span></span> <span data-ttu-id="197f6-111">Qualsiasi espressione con un tipo di dati che si allarga a `String`.</span><span class="sxs-lookup"><span data-stu-id="197f6-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="197f6-112">Note</span><span class="sxs-lookup"><span data-stu-id="197f6-112">Remarks</span></span>  
 <span data-ttu-id="197f6-113">Se il tipo di dati di `expression1` o `expression2` non è `String` ma viene ampliato a `String`, viene convertito in `String`.</span><span class="sxs-lookup"><span data-stu-id="197f6-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="197f6-114">Se uno dei tipi di dati non viene ampliato a `String`, il compilatore genera un errore.</span><span class="sxs-lookup"><span data-stu-id="197f6-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="197f6-115">Il tipo di dati di `result` è `String`.</span><span class="sxs-lookup"><span data-stu-id="197f6-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="197f6-116">Se una o entrambe le espressioni restituiscono [Nothing](../../../visual-basic/language-reference/nothing.md) o hanno un valore <xref:System.DBNull.Value?displayProperty=nameWithType>, vengono considerate come una stringa con un valore di "".</span><span class="sxs-lookup"><span data-stu-id="197f6-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="197f6-117">L'operatore `&` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="197f6-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="197f6-118">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="197f6-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="197f6-119">Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="197f6-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="197f6-120">Il carattere e commerciale (&) può essere usato anche per identificare le variabili come tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="197f6-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="197f6-121">Per ulteriori informazioni, vedere [caratteri di tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="197f6-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="197f6-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="197f6-122">Example</span></span>  
 <span data-ttu-id="197f6-123">Questo esempio usa l'operatore `&` per forzare la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="197f6-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="197f6-124">Il risultato è un valore stringa che rappresenta la concatenazione dei due operandi di stringa.</span><span class="sxs-lookup"><span data-stu-id="197f6-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="197f6-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="197f6-125">See also</span></span>

- [<span data-ttu-id="197f6-126">Operatore &=</span><span class="sxs-lookup"><span data-stu-id="197f6-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="197f6-127">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="197f6-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="197f6-128">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="197f6-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="197f6-129">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="197f6-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="197f6-130">Operatori di concatenazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="197f6-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)

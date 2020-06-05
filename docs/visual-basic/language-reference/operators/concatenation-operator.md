---
title: Operatore &amp;
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
ms.openlocfilehash: d778c0c99d6d074fe8b73aaf3660074643e7e136
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371609"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="fe81f-102">&amp;Operatore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe81f-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="fe81f-103">Genera una concatenazione di stringhe di due espressioni.</span><span class="sxs-lookup"><span data-stu-id="fe81f-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe81f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe81f-104">Syntax</span></span>  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="fe81f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="fe81f-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="fe81f-106">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fe81f-106">Required.</span></span> <span data-ttu-id="fe81f-107">Qualsiasi `String` `Object` variabile o.</span><span class="sxs-lookup"><span data-stu-id="fe81f-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="fe81f-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fe81f-108">Required.</span></span> <span data-ttu-id="fe81f-109">Qualsiasi espressione con un tipo di dati che si allarga a `String` .</span><span class="sxs-lookup"><span data-stu-id="fe81f-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="fe81f-110">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fe81f-110">Required.</span></span> <span data-ttu-id="fe81f-111">Qualsiasi espressione con un tipo di dati che si allarga a `String` .</span><span class="sxs-lookup"><span data-stu-id="fe81f-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe81f-112">Commenti</span><span class="sxs-lookup"><span data-stu-id="fe81f-112">Remarks</span></span>  
 <span data-ttu-id="fe81f-113">Se il tipo di dati di `expression1` o `expression2` non è `String` ma si allarga a `String` , viene convertito in `String` .</span><span class="sxs-lookup"><span data-stu-id="fe81f-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="fe81f-114">Se uno dei tipi di dati non viene ampliato a `String` , il compilatore genera un errore.</span><span class="sxs-lookup"><span data-stu-id="fe81f-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="fe81f-115">Il tipo di dati di `result` è `String` .</span><span class="sxs-lookup"><span data-stu-id="fe81f-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="fe81f-116">Se una o entrambe le espressioni restituiscono [Nothing](../nothing.md) o hanno un valore <xref:System.DBNull.Value?displayProperty=nameWithType> , vengono considerate come una stringa con un valore di "".</span><span class="sxs-lookup"><span data-stu-id="fe81f-116">If one or both expressions evaluate to [Nothing](../nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe81f-117">L' `&` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="fe81f-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="fe81f-118">Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito.</span><span class="sxs-lookup"><span data-stu-id="fe81f-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="fe81f-119">Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fe81f-119">For more information, see [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe81f-120">Il carattere e commerciale (&) può essere usato anche per identificare le variabili come tipo `Long` .</span><span class="sxs-lookup"><span data-stu-id="fe81f-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="fe81f-121">Per ulteriori informazioni, vedere [caratteri di tipo](../../programming-guide/language-features/data-types/type-characters.md).</span><span class="sxs-lookup"><span data-stu-id="fe81f-121">For more information, see [Type Characters](../../programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe81f-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe81f-122">Example</span></span>  
 <span data-ttu-id="fe81f-123">In questo esempio viene usato l' `&` operatore per forzare la concatenazione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="fe81f-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="fe81f-124">Il risultato è un valore stringa che rappresenta la concatenazione dei due operandi di stringa.</span><span class="sxs-lookup"><span data-stu-id="fe81f-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="fe81f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe81f-125">See also</span></span>

- [<span data-ttu-id="fe81f-126">Operatore&=</span><span class="sxs-lookup"><span data-stu-id="fe81f-126">&= Operator</span></span>](and-assignment-operator.md)
- [<span data-ttu-id="fe81f-127">Operatori di concatenazione</span><span class="sxs-lookup"><span data-stu-id="fe81f-127">Concatenation Operators</span></span>](concatenation-operators.md)
- [<span data-ttu-id="fe81f-128">Precedenza tra gli operatori in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe81f-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="fe81f-129">Elenco degli operatori per funzionalità</span><span class="sxs-lookup"><span data-stu-id="fe81f-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="fe81f-130">Operatori di concatenazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fe81f-130">Concatenation Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)

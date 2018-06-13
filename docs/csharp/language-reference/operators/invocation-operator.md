---
title: Operatore () (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 2ded01ef3192e0f34d586cd63d93b894b5347e7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275025"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f762b-102">Operatore () (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="f762b-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="f762b-103">Oltre a specificare l'ordine in cui devono essere eseguite le operazioni di un'espressione, le parentesi vengono usate per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f762b-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="f762b-104">Specificare i cast, ovvero le conversioni di tipi.</span><span class="sxs-lookup"><span data-stu-id="f762b-104">Specify casts, or type conversions.</span></span>  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  <span data-ttu-id="f762b-105">Richiamare metodi o delegati.</span><span class="sxs-lookup"><span data-stu-id="f762b-105">Invoke methods or delegates.</span></span>  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="f762b-106">Note</span><span class="sxs-lookup"><span data-stu-id="f762b-106">Remarks</span></span>  
 <span data-ttu-id="f762b-107">Un cast richiama l'operatore di conversione in modo esplicito da un tipo a un altro. Se tale operatore di conversione non viene definito, il cast non sarà eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f762b-107">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="f762b-108">Per informazioni sulla definizione di un operatore di conversione, vedere [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="f762b-108">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="f762b-109">Non è possibile sottoporre l'operatore `()` a overload.</span><span class="sxs-lookup"><span data-stu-id="f762b-109">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="f762b-110">Per altre informazioni, vedere [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="f762b-110">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="f762b-111">Un'espressione cast può determinare una sintassi ambigua.</span><span class="sxs-lookup"><span data-stu-id="f762b-111">A cast expression could lead to ambiguous syntax.</span></span> <span data-ttu-id="f762b-112">Ad esempio, l'espressione `(x)–y` potrebbe essere interpretata come espressione cast (un cast di -y sul tipo x) oppure come espressione di addizione combinata con un'espressione tra parentesi che calcola il valore x - y.</span><span class="sxs-lookup"><span data-stu-id="f762b-112">For example, the expression `(x)–y` could be either interpreted as a cast expression (a cast of –y to type x) or as an additive expression combined with a parenthesized expression, which computes the value x – y.</span></span>  
  
 <span data-ttu-id="f762b-113">Per altre informazioni sulla chiamata al metodo, vedere [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="f762b-113">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f762b-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="f762b-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f762b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f762b-115">See Also</span></span>  
 [<span data-ttu-id="f762b-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="f762b-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f762b-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="f762b-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f762b-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="f762b-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

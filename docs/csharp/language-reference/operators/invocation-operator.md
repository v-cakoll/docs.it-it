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
ms.openlocfilehash: 29097dc4aa0bf712b9b2beda4450820a66472ba7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44179671"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a9739-102">Operatore () (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="a9739-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="a9739-103">Oltre a specificare l'ordine in cui devono essere eseguite le operazioni di un'espressione, le parentesi vengono usate per eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9739-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="a9739-104">Specificare i cast, ovvero le conversioni di tipi.</span><span class="sxs-lookup"><span data-stu-id="a9739-104">Specify casts, or type conversions.</span></span>  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  <span data-ttu-id="a9739-105">Richiamare metodi o delegati.</span><span class="sxs-lookup"><span data-stu-id="a9739-105">Invoke methods or delegates.</span></span>  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="a9739-106">Note</span><span class="sxs-lookup"><span data-stu-id="a9739-106">Remarks</span></span>  
 <span data-ttu-id="a9739-107">Un cast richiama l'operatore di conversione in modo esplicito da un tipo a un altro. Se tale operatore di conversione non viene definito, il cast non sarà eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9739-107">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="a9739-108">Per informazioni sulla definizione di un operatore di conversione, vedere [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="a9739-108">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="a9739-109">Non è possibile sottoporre l'operatore `()` a overload.</span><span class="sxs-lookup"><span data-stu-id="a9739-109">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="a9739-110">Per altre informazioni, vedere [Cast e conversioni di tipi](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="a9739-110">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="a9739-111">Per altre informazioni sulla chiamata al metodo, vedere [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="a9739-111">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a9739-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a9739-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a9739-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9739-113">See Also</span></span>

- [<span data-ttu-id="a9739-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="a9739-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a9739-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="a9739-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a9739-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="a9739-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

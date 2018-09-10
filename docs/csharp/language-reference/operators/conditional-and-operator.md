---
title: '&amp;&amp; Operatore (Riferimenti per C#)'
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 459b791fde3e4d3940dbd3d916f940e81f365da6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529235"
---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="417db-102">&amp;&amp; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="417db-102">&amp;&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="417db-103">L'operatore AND condizionale (`&&`) esegue un AND logico sugli operandi `bool`, ma valuta il secondo operando solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="417db-103">The conditional-AND operator (`&&`) performs a logical-AND of its `bool` operands, but only evaluates its second operand if necessary.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="417db-104">Note</span><span class="sxs-lookup"><span data-stu-id="417db-104">Remarks</span></span>  
 <span data-ttu-id="417db-105">L'operazione</span><span class="sxs-lookup"><span data-stu-id="417db-105">The operation</span></span>  
  
```csharp  
x && y  
```  
  
 <span data-ttu-id="417db-106">corrisponde all'operazione</span><span class="sxs-lookup"><span data-stu-id="417db-106">corresponds to the operation</span></span>  
  
```csharp  
x & y  
```  
  
 <span data-ttu-id="417db-107">tuttavia se `x` è `false`, `y` non viene valutato, poiché il risultato dell'operazione AND sarà `false` indipendentemente dal valore di `y`.</span><span class="sxs-lookup"><span data-stu-id="417db-107">except that if `x` is `false`, `y` is not evaluated, because the result of the AND operation is `false` no matter what the value of `y`  is.</span></span> <span data-ttu-id="417db-108">Questa condizione è denominata "valutazione short circuit".</span><span class="sxs-lookup"><span data-stu-id="417db-108">This is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="417db-109">L'operatore AND condizionale non può essere soggetto a overload, ma anche gli overload degli operatori logici comuni e degli operatori [true](../../../csharp/language-reference/keywords/true.md) e [false](../../../csharp/language-reference/keywords/false.md) (con certe limitazioni) sono considerati overload degli operatori logici condizionali.</span><span class="sxs-lookup"><span data-stu-id="417db-109">The conditional-AND operator cannot be overloaded, but overloads of the regular logical operators and operators [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) are, with certain restrictions, also considered overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="417db-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="417db-110">Example</span></span>  
 <span data-ttu-id="417db-111">Nell'esempio seguente l'espressione condizionale nella seconda istruzione `if` valuta solo il primo operando, perché l'operando restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="417db-111">In the following example, the conditional expression in the second `if` statement evaluates only the first operand because the operand returns `false`.</span></span>  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="417db-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="417db-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="417db-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="417db-113">See Also</span></span>

- [<span data-ttu-id="417db-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="417db-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="417db-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="417db-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="417db-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="417db-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

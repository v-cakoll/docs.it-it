---
title: Operatore || (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: d22e57d097edb0fe52b604e9c6431e167c410f0b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b760c-102">Operatore || (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b760c-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="b760c-103">L'operatore OR condizionale (`||`) esegue un'operazione OR logica sui propri operandi `bool`.</span><span class="sxs-lookup"><span data-stu-id="b760c-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="b760c-104">Se il primo operando restituisce `true`, il secondo operando non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="b760c-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="b760c-105">Se il primo operando restituisce `false`, il secondo operando determina se l'espressione OR nel suo complesso restituisce `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="b760c-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b760c-106">Note</span><span class="sxs-lookup"><span data-stu-id="b760c-106">Remarks</span></span>  
 <span data-ttu-id="b760c-107">L'operazione</span><span class="sxs-lookup"><span data-stu-id="b760c-107">The operation</span></span>  
  
```csharp  
x || y  
```  
  
 <span data-ttu-id="b760c-108">corrisponde all'operazione</span><span class="sxs-lookup"><span data-stu-id="b760c-108">corresponds to the operation</span></span>  
  
```csharp  
x | y  
```  
  
 <span data-ttu-id="b760c-109">tuttavia se `x` è `true`, `y` non viene valutato, perché l'operazione OR è `true` indipendentemente dal valore di `y`.</span><span class="sxs-lookup"><span data-stu-id="b760c-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="b760c-110">Questa concetto è noto come "valutazione a corto circuito".</span><span class="sxs-lookup"><span data-stu-id="b760c-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="b760c-111">L'operatore OR condizionale non può essere soggetto a overload, ma anche gli overload degli operatori logici comuni e degli operatori [true](../../../csharp/language-reference/keywords/true.md) e [false](../../../csharp/language-reference/keywords/false.md) (con certe limitazioni) sono considerati overload degli operatori logici condizionali.</span><span class="sxs-lookup"><span data-stu-id="b760c-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b760c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b760c-112">Example</span></span>  
 <span data-ttu-id="b760c-113">Negli esempi seguenti l'espressione che usa `||` valuta solo il primo operando.</span><span class="sxs-lookup"><span data-stu-id="b760c-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="b760c-114">L'espressione che usa `|` valuta entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="b760c-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="b760c-115">Nel secondo esempio, si verifica un'eccezione in fase di esecuzione se vengono valutati entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="b760c-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b760c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b760c-116">See Also</span></span>  
 [<span data-ttu-id="b760c-117">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b760c-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b760c-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b760c-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b760c-119">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b760c-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

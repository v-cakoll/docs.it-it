---
title: Operatore || (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '||_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 57bcb25b0d453fa59855f40c3189eb4af2bb8b7f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="1d15b-102">Operatore || (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1d15b-102">|| Operator (C# Reference)</span></span>
<span data-ttu-id="1d15b-103">L'operatore OR condizionale (`||`) esegue un'operazione OR logica sui propri operandi `bool`.</span><span class="sxs-lookup"><span data-stu-id="1d15b-103">The conditional-OR operator (`||`) performs a logical-OR of its `bool` operands.</span></span> <span data-ttu-id="1d15b-104">Se il primo operando restituisce `true`, il secondo operando non viene valutato.</span><span class="sxs-lookup"><span data-stu-id="1d15b-104">If the first operand evaluates to `true`, the second operand isn't evaluated.</span></span> <span data-ttu-id="1d15b-105">Se il primo operando restituisce `false`, il secondo operando determina se l'espressione OR nel suo complesso restituisce `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="1d15b-105">If the first operand evaluates to `false`, the second operator determines whether the OR expression as a whole evaluates to `true` or `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d15b-106">Note</span><span class="sxs-lookup"><span data-stu-id="1d15b-106">Remarks</span></span>  
 <span data-ttu-id="1d15b-107">L'operazione</span><span class="sxs-lookup"><span data-stu-id="1d15b-107">The operation</span></span>  
  
```  
x || y  
```  
  
 <span data-ttu-id="1d15b-108">corrisponde all'operazione</span><span class="sxs-lookup"><span data-stu-id="1d15b-108">corresponds to the operation</span></span>  
  
```  
x | y  
```  
  
 <span data-ttu-id="1d15b-109">tuttavia se `x` è `true`, `y` non viene valutato, perché l'operazione OR è `true` indipendentemente dal valore di `y`.</span><span class="sxs-lookup"><span data-stu-id="1d15b-109">except that if `x` is `true`, `y` is not evaluated because the OR operation is `true` regardless of the value of `y`.</span></span> <span data-ttu-id="1d15b-110">Questa concetto è noto come "valutazione a corto circuito".</span><span class="sxs-lookup"><span data-stu-id="1d15b-110">This concept is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="1d15b-111">L'operatore OR condizionale non può essere soggetto a overload, ma anche gli overload degli operatori logici comuni e degli operatori [true](../../../csharp/language-reference/keywords/true.md) e [false](../../../csharp/language-reference/keywords/false.md) (con certe limitazioni) sono considerati overload degli operatori logici condizionali.</span><span class="sxs-lookup"><span data-stu-id="1d15b-111">The conditional-OR operator cannot be overloaded, but overloads of the regular logical operators and the [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) operators are, with certain restrictions, also considered to be overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d15b-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d15b-112">Example</span></span>  
 <span data-ttu-id="1d15b-113">Negli esempi seguenti l'espressione che usa `||` valuta solo il primo operando.</span><span class="sxs-lookup"><span data-stu-id="1d15b-113">In the following examples, the expression that uses `||` evaluates only the first operand.</span></span> <span data-ttu-id="1d15b-114">L'espressione che usa `|` valuta entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="1d15b-114">The expression that uses `|` evaluates both operands.</span></span> <span data-ttu-id="1d15b-115">Nel secondo esempio, si verifica un'eccezione in fase di esecuzione se vengono valutati entrambi gli operandi.</span><span class="sxs-lookup"><span data-stu-id="1d15b-115">In the second example, a run-time exception occurs if both operands are evaluated.</span></span>  
  
 <span data-ttu-id="1d15b-116">[!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1d15b-116">[!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d15b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d15b-117">See Also</span></span>  
 <span data-ttu-id="1d15b-118">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1d15b-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1d15b-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1d15b-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="1d15b-120">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="1d15b-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


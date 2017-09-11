---
title: '&amp;&amp; Operatore (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&&_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
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
ms.openlocfilehash: 1da61947cbc85e5b3045513e99e013d1e4fae4b3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="05e32-102">&amp;&amp; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="05e32-102">&amp;&amp; Operator (C# Reference)</span></span>
<span data-ttu-id="05e32-103">L'operatore AND condizionale (`&&`) esegue un AND logico sugli operandi `bool`, ma valuta il secondo operando solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="05e32-103">The conditional-AND operator (`&&`) performs a logical-AND of its `bool` operands, but only evaluates its second operand if necessary.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05e32-104">Note</span><span class="sxs-lookup"><span data-stu-id="05e32-104">Remarks</span></span>  
 <span data-ttu-id="05e32-105">L'operazione</span><span class="sxs-lookup"><span data-stu-id="05e32-105">The operation</span></span>  
  
```  
x && y  
```  
  
 <span data-ttu-id="05e32-106">corrisponde all'operazione</span><span class="sxs-lookup"><span data-stu-id="05e32-106">corresponds to the operation</span></span>  
  
```  
x & y  
```  
  
 <span data-ttu-id="05e32-107">tuttavia se `x` è `false`, `y` non viene valutato, poiché il risultato dell'operazione AND sarà `false` indipendentemente dal valore di `y`.</span><span class="sxs-lookup"><span data-stu-id="05e32-107">except that if `x` is `false`, `y` is not evaluated, because the result of the AND operation is `false` no matter what the value of `y`  is.</span></span> <span data-ttu-id="05e32-108">Questa condizione è denominata "valutazione short circuit".</span><span class="sxs-lookup"><span data-stu-id="05e32-108">This is known as "short-circuit" evaluation.</span></span>  
  
 <span data-ttu-id="05e32-109">L'operatore AND condizionale non può essere soggetto a overload, ma anche gli overload degli operatori logici comuni e degli operatori [true](../../../csharp/language-reference/keywords/true.md) e [false](../../../csharp/language-reference/keywords/false.md) (con certe limitazioni) sono considerati overload degli operatori logici condizionali.</span><span class="sxs-lookup"><span data-stu-id="05e32-109">The conditional-AND operator cannot be overloaded, but overloads of the regular logical operators and operators [true](../../../csharp/language-reference/keywords/true.md) and [false](../../../csharp/language-reference/keywords/false.md) are, with certain restrictions, also considered overloads of the conditional logical operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05e32-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="05e32-110">Example</span></span>  
 <span data-ttu-id="05e32-111">Nell'esempio seguente l'espressione condizionale nella seconda istruzione `if` valuta solo il primo operando, perché l'operando restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="05e32-111">In the following example, the conditional expression in the second `if` statement evaluates only the first operand because the operand returns `false`.</span></span>  
  
 <span data-ttu-id="05e32-112">[!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="05e32-112">[!code-cs[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="05e32-113">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="05e32-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05e32-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05e32-114">See Also</span></span>  
 <span data-ttu-id="05e32-115">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="05e32-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="05e32-116">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="05e32-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="05e32-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="05e32-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


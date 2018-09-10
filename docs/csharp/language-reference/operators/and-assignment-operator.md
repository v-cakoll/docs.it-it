---
title: Operatore &amp;= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: f3a6fe20ca89a90b5a64118d73fb39e9a364d1e9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506401"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="0799c-102">Operatore &amp;= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0799c-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="0799c-103">Operatore di assegnazione AND.</span><span class="sxs-lookup"><span data-stu-id="0799c-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0799c-104">Note</span><span class="sxs-lookup"><span data-stu-id="0799c-104">Remarks</span></span>  
 <span data-ttu-id="0799c-105">Un'espressione che usa l'operatore di assegnazione `&=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="0799c-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```csharp  
x &= y  
```  
  
 <span data-ttu-id="0799c-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="0799c-106">is equivalent to</span></span>  
  
```csharp  
x = x & y  
```  
  
 <span data-ttu-id="0799c-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0799c-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="0799c-108">L'[operatore &](../../../csharp/language-reference/operators/and-operator.md) esegue un'operazione con AND logico bit per bit su operandi integrali e un'operazione con AND logico sugli operandi `bool`.</span><span class="sxs-lookup"><span data-stu-id="0799c-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="0799c-109">L'operatore `&=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore &](../../../csharp/language-reference/operators/and-operator.md) binario (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="0799c-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0799c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="0799c-110">Example</span></span>  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0799c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0799c-111">See Also</span></span>

- [<span data-ttu-id="0799c-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0799c-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="0799c-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0799c-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="0799c-114">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="0799c-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

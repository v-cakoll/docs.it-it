---
title: Operatore *= (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: 16
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
ms.openlocfilehash: 2969ba3ce303da591353fd0114dccf752e63f2c3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="80772-102">Operatore *= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="80772-102">*= Operator (C# Reference)</span></span>
<span data-ttu-id="80772-103">Operatore di assegnazione di moltiplicazione binario.</span><span class="sxs-lookup"><span data-stu-id="80772-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80772-104">Note</span><span class="sxs-lookup"><span data-stu-id="80772-104">Remarks</span></span>  
 <span data-ttu-id="80772-105">Un'espressione che usa l'operatore di assegnazione `*=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="80772-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="80772-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="80772-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="80772-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="80772-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="80772-108">Per i tipi numerici, l'[operatore *](../../../csharp/language-reference/operators/multiplication-operator.md) è predefinito per l'esecuzione di moltiplicazioni.</span><span class="sxs-lookup"><span data-stu-id="80772-108">The [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="80772-109">L'operatore `*=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore *](../../../csharp/language-reference/operators/multiplication-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="80772-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="80772-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="80772-110">Example</span></span>  
 <span data-ttu-id="80772-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="80772-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80772-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80772-112">See Also</span></span>  
 <span data-ttu-id="80772-113">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="80772-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="80772-114">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="80772-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="80772-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="80772-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


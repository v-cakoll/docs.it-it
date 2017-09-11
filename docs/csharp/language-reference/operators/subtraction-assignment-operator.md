---
title: Operatore -= (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- -=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
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
ms.openlocfilehash: d7f26ae1fce54eb0d03a314a83ce523baeb3f348
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="--operator-c-reference"></a><span data-ttu-id="68dbe-102">Operatore -= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="68dbe-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="68dbe-103">Operatore di assegnazione di sottrazione.</span><span class="sxs-lookup"><span data-stu-id="68dbe-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68dbe-104">Note</span><span class="sxs-lookup"><span data-stu-id="68dbe-104">Remarks</span></span>  
 <span data-ttu-id="68dbe-105">Un'espressione che usa l'operatore di assegnazione `-=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="68dbe-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```  
x -= y  
```  
  
 <span data-ttu-id="68dbe-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="68dbe-106">is equivalent to</span></span>  
  
```  
x = x - y  
```  
  
 <span data-ttu-id="68dbe-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="68dbe-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="68dbe-108">Il significato dell'[operatore -](../../../csharp/language-reference/operators/subtraction-operator.md) dipende dai tipi di `x` e `y` (sottrazione per gli operandi numerici, rimozione del delegato per gli operandi delegati e così via).</span><span class="sxs-lookup"><span data-stu-id="68dbe-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="68dbe-109">L'operatore `-=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore -](../../../csharp/language-reference/operators/subtraction-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="68dbe-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="68dbe-110">L'operatore -= viene anche usato in C# per annullare la sottoscrizione a un evento.</span><span class="sxs-lookup"><span data-stu-id="68dbe-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="68dbe-111">Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="68dbe-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="68dbe-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="68dbe-112">Example</span></span>  
 <span data-ttu-id="68dbe-113">[!code-cs[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="68dbe-113">[!code-cs[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68dbe-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68dbe-114">See Also</span></span>  
 <span data-ttu-id="68dbe-115">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="68dbe-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="68dbe-116">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="68dbe-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="68dbe-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="68dbe-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


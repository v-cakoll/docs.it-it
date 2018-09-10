---
title: Operatore -= (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 7cade0811536d836480f80a56cf8c4d09e089a0b
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43773987"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="775ff-102">Operatore -= (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="775ff-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="775ff-103">Operatore di assegnazione di sottrazione.</span><span class="sxs-lookup"><span data-stu-id="775ff-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="775ff-104">Note</span><span class="sxs-lookup"><span data-stu-id="775ff-104">Remarks</span></span>  
 <span data-ttu-id="775ff-105">Un'espressione che usa l'operatore di assegnazione `-=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="775ff-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```csharp  
x -= y  
```  
  
 <span data-ttu-id="775ff-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="775ff-106">is equivalent to</span></span>  
  
```csharp  
x = x - y  
```  
  
 <span data-ttu-id="775ff-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="775ff-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="775ff-108">Il significato dell'[operatore -](../../../csharp/language-reference/operators/subtraction-operator.md) dipende dai tipi di `x` e `y` (sottrazione per gli operandi numerici, rimozione del delegato per gli operandi delegati e così via).</span><span class="sxs-lookup"><span data-stu-id="775ff-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="775ff-109">L'operatore `-=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore -](../../../csharp/language-reference/operators/subtraction-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="775ff-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="775ff-110">L'operatore -= viene anche usato in C# per annullare la sottoscrizione a un evento.</span><span class="sxs-lookup"><span data-stu-id="775ff-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="775ff-111">Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span><span class="sxs-lookup"><span data-stu-id="775ff-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="775ff-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="775ff-112">Example</span></span>  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="775ff-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="775ff-113">See Also</span></span>

- [<span data-ttu-id="775ff-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="775ff-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="775ff-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="775ff-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="775ff-116">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="775ff-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

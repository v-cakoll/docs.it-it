---
title: Operatore += (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
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
ms.openlocfilehash: 42567b2d8e7d9b694ce64ccb88e0fd4bfe05b020
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="af71d-102">Operatore += (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="af71d-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="af71d-103">Operatore di assegnazione di addizione.</span><span class="sxs-lookup"><span data-stu-id="af71d-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af71d-104">Note</span><span class="sxs-lookup"><span data-stu-id="af71d-104">Remarks</span></span>  
 <span data-ttu-id="af71d-105">Un'espressione che usa l'operatore di assegnazione `+=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="af71d-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```  
x += y  
```  
  
 <span data-ttu-id="af71d-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="af71d-106">is equivalent to</span></span>  
  
```  
x = x + y  
```  
  
 <span data-ttu-id="af71d-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="af71d-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="af71d-108">Il significato dell'[operatore +](../../../csharp/language-reference/operators/addition-operator.md) dipende dai tipi di `x` e `y` (addizione per gli operandi numerici, concatenazione per gli operandi stringa e così via).</span><span class="sxs-lookup"><span data-stu-id="af71d-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="af71d-109">L'operatore `+=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore +](../../../csharp/language-reference/operators/addition-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="af71d-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="af71d-110">L'operatore `+=` viene usato anche per specificare un metodo che verrà chiamato in risposta a un evento. I metodi di questo tipo sono chiamati gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="af71d-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="af71d-111">L'uso dell'operatore `+=` in questo contesto è detto *sottoscrizione di un evento*.</span><span class="sxs-lookup"><span data-stu-id="af71d-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="af71d-112">Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)</span><span class="sxs-lookup"><span data-stu-id="af71d-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span> <span data-ttu-id="af71d-113">e [Delegati](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="af71d-113">and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af71d-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="af71d-114">Example</span></span>  
 <span data-ttu-id="af71d-115">[!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="af71d-115">[!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af71d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af71d-116">See Also</span></span>  
 <span data-ttu-id="af71d-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="af71d-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="af71d-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="af71d-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="af71d-119">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="af71d-119">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


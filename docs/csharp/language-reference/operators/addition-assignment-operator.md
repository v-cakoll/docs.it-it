---
title: Operatore += (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: de83f48fc644d8b232d9ef9e1698272f20a27d65
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8b791-102">Operatore += (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8b791-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="8b791-103">Operatore di assegnazione di addizione.</span><span class="sxs-lookup"><span data-stu-id="8b791-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b791-104">Note</span><span class="sxs-lookup"><span data-stu-id="8b791-104">Remarks</span></span>  
 <span data-ttu-id="8b791-105">Un'espressione che usa l'operatore di assegnazione `+=`, ad esempio</span><span class="sxs-lookup"><span data-stu-id="8b791-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```  
x += y  
```  
  
 <span data-ttu-id="8b791-106">equivale a</span><span class="sxs-lookup"><span data-stu-id="8b791-106">is equivalent to</span></span>  
  
```  
x = x + y  
```  
  
 <span data-ttu-id="8b791-107">con la differenza che `x` viene valutato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="8b791-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="8b791-108">Il significato dell'[operatore +](../../../csharp/language-reference/operators/addition-operator.md) dipende dai tipi di `x` e `y` (addizione per gli operandi numerici, concatenazione per gli operandi stringa e così via).</span><span class="sxs-lookup"><span data-stu-id="8b791-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="8b791-109">L'operatore `+=` non può essere sottoposto direttamente a overload. I tipi definiti dall'utente, tuttavia, possono eseguire l'overload dell'[operatore +](../../../csharp/language-reference/operators/addition-operator.md) (vedere [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="8b791-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="8b791-110">L'operatore `+=` viene usato anche per specificare un metodo che verrà chiamato in risposta a un evento. I metodi di questo tipo sono chiamati gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="8b791-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="8b791-111">L'uso dell'operatore `+=` in questo contesto è detto *sottoscrizione di un evento*.</span><span class="sxs-lookup"><span data-stu-id="8b791-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="8b791-112">Per altre informazioni, vedere [Procedura: sottoscrivere e annullare la sottoscrizione di eventi](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) e [Delegati](../../../csharp/programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="8b791-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b791-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b791-113">Example</span></span>  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8b791-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b791-114">See Also</span></span>  
 [<span data-ttu-id="8b791-115">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8b791-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8b791-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8b791-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8b791-117">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="8b791-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

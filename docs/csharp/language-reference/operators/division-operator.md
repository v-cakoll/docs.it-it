---
title: Operatore / (Riferimenti per C#)
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 9d0bbff1fd9f4ab3c93c879d12ccd5fde1187b44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272571"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="93341-102">Operatore / (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="93341-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="93341-103">L'operatore di divisione (`/`) divide il primo operando per il secondo operando.</span><span class="sxs-lookup"><span data-stu-id="93341-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="93341-104">Tutti i tipi numerici hanno operatori di divisione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="93341-104">All numeric types have predefined division operators.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="93341-105">Note</span><span class="sxs-lookup"><span data-stu-id="93341-105">Remarks</span></span>  
 <span data-ttu-id="93341-106">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `/` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="93341-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="93341-107">Un overload dell'operatore `/` ha come risultato l'overload implicito dell'[operatore / =](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="93341-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="93341-108">Quando si dividono due numeri interi, il risultato è sempre un numero intero.</span><span class="sxs-lookup"><span data-stu-id="93341-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="93341-109">Ad esempio, il risultato di 7/3 è 2.</span><span class="sxs-lookup"><span data-stu-id="93341-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="93341-110">Questo comportamento non deve essere confuso con la divisione con arrotondamento all'intero più grande (floor), perché l'operatore `/` arrotonda per difetto: -7/3 è -2.</span><span class="sxs-lookup"><span data-stu-id="93341-110">This is not to be confused with floored division, as the `/` operator rounds towards zero: -7 / 3 is -2.</span></span>  
  
 <span data-ttu-id="93341-111">Per ottenere un quoziente sotto forma di numero razionale, usare i tipi `float`, `double` o `decimal`.</span><span class="sxs-lookup"><span data-stu-id="93341-111">To obtain a quotient as a rational number, use the `float`, `double`, or `decimal` types.</span></span> <span data-ttu-id="93341-112">Esistono molti modi per eseguire conversioni tra i [tipi numerici predefiniti](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span><span class="sxs-lookup"><span data-stu-id="93341-112">There are many ways to convert between [built in numeric types](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span></span>  
  
 <span data-ttu-id="93341-113">Per determinare il resto, usare l'[operatore di resto](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span><span class="sxs-lookup"><span data-stu-id="93341-113">To determine the remainder, use the [remainder operator](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93341-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="93341-114">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="93341-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93341-115">See Also</span></span>  
 [<span data-ttu-id="93341-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="93341-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="93341-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="93341-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="93341-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="93341-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

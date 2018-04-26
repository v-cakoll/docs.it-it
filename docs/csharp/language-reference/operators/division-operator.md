---
title: Operatore / (Riferimenti per C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5b17d122e3e3f75012e084903b6f8975fb53d46c
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b9c13-102">Operatore / (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b9c13-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="b9c13-103">L'operatore di divisione (`/`) divide il primo operando per il secondo operando.</span><span class="sxs-lookup"><span data-stu-id="b9c13-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="b9c13-104">Tutti i tipi numerici hanno operatori di divisione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b9c13-104">All numeric types have predefined division operators.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b9c13-105">Note</span><span class="sxs-lookup"><span data-stu-id="b9c13-105">Remarks</span></span>  
 <span data-ttu-id="b9c13-106">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `/` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b9c13-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="b9c13-107">Un overload dell'operatore `/` ha come risultato l'overload implicito dell'[operatore / =](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b9c13-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="b9c13-108">Quando si dividono due numeri interi, il risultato è sempre un numero intero.</span><span class="sxs-lookup"><span data-stu-id="b9c13-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="b9c13-109">Ad esempio, il risultato di 7/3 è 2.</span><span class="sxs-lookup"><span data-stu-id="b9c13-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="b9c13-110">Questo comportamento non deve essere confuso con la divisione con arrotondamento all'intero più grande (floor), perché l'operatore `/` arrotonda per difetto: -7/3 è -2.</span><span class="sxs-lookup"><span data-stu-id="b9c13-110">This is not to be confused with floored division, as the `/` operator rounds towards zero: -7 / 3 is -2.</span></span>  
  
 <span data-ttu-id="b9c13-111">Per ottenere un quoziente sotto forma di numero razionale, usare i tipi `float`, `double` o `decimal`.</span><span class="sxs-lookup"><span data-stu-id="b9c13-111">To obtain a quotient as a rational number, use the `float`, `double`, or `decimal` types.</span></span> <span data-ttu-id="b9c13-112">Esistono molti modi per eseguire conversioni tra i [tipi numerici predefiniti](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span><span class="sxs-lookup"><span data-stu-id="b9c13-112">There are many ways to convert between [built in numeric types](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span></span>  
  
 <span data-ttu-id="b9c13-113">Per determinare il resto, usare l'[operatore di resto](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span><span class="sxs-lookup"><span data-stu-id="b9c13-113">To determine the remainder, use the [remainder operator](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9c13-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="b9c13-114">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b9c13-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9c13-115">See Also</span></span>  
 [<span data-ttu-id="b9c13-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b9c13-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b9c13-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b9c13-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b9c13-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="b9c13-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

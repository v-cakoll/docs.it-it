---
title: Operatore / (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
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
ms.openlocfilehash: 2972261996467f987fa457213b1bcb482d9f1519
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="13e2a-102">Operatore / (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="13e2a-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="13e2a-103">L'operatore di divisione (`/`) divide il primo operando per il secondo operando.</span><span class="sxs-lookup"><span data-stu-id="13e2a-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="13e2a-104">Tutti i tipi numerici hanno operatori di divisione predefiniti.</span><span class="sxs-lookup"><span data-stu-id="13e2a-104">All numeric types have predefined division operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13e2a-105">Note</span><span class="sxs-lookup"><span data-stu-id="13e2a-105">Remarks</span></span>  
 <span data-ttu-id="13e2a-106">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `/` (vedere [operatore](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="13e2a-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="13e2a-107">Un overload dell'operatore `/` ha come risultato l'overload implicito dell'[operatore / =](division-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="13e2a-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="13e2a-108">Quando si dividono due numeri interi, il risultato è sempre un numero intero.</span><span class="sxs-lookup"><span data-stu-id="13e2a-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="13e2a-109">Ad esempio, il risultato di 7/3 è 2.</span><span class="sxs-lookup"><span data-stu-id="13e2a-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="13e2a-110">Per determinare il resto di 7/3, usare l'operatore di resto ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span><span class="sxs-lookup"><span data-stu-id="13e2a-110">To determine the remainder of 7 / 3, use the remainder operator ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span></span> <span data-ttu-id="13e2a-111">Per ottenere un quoziente come numero razionale o come frazione, assegnare al dividendo o al divisore il tipo `float` o il tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="13e2a-111">To obtain a quotient as a rational number or fraction, give the dividend or divisor type `float` or type `double`.</span></span> <span data-ttu-id="13e2a-112">È possibile assegnare il tipo in modo implicito se si esprime il dividendo o il divisore come numero decimale mettendo una cifra sul lato destro del punto decimale, come mostra l'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="13e2a-112">You can assign the type implicitly if you express the dividend or divisor as a decimal by putting a digit to the right side of the decimal point, as the following example shows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13e2a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="13e2a-113">Example</span></span>  
 <span data-ttu-id="13e2a-114">[!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="13e2a-114">[!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e2a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13e2a-115">See Also</span></span>  
 <span data-ttu-id="13e2a-116">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="13e2a-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="13e2a-117">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="13e2a-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="13e2a-118">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="13e2a-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


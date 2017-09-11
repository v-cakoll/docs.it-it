---
title: '&lt;&lt; Operatore (Riferimenti per C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
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
ms.openlocfilehash: 4e6ad17232ec4eb087ca300342331af6a30789b1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="0ace9-102">&lt;&lt; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0ace9-102">&lt;&lt; Operator (C# Reference)</span></span>
<span data-ttu-id="0ace9-103">L'operatore di spostamento a sinistra (`<<`) sposta verso sinistra il primo operando del numero di bit specificato dal secondo operando.</span><span class="sxs-lookup"><span data-stu-id="0ace9-103">The left-shift operator (`<<`) shifts its first operand left by the number of bits specified by its second operand.</span></span> <span data-ttu-id="0ace9-104">Il tipo del secondo operando deve essere un [int](../../../csharp/language-reference/keywords/int.md) o un tipo con una conversione numerica implicita predefinita in `int`.</span><span class="sxs-lookup"><span data-stu-id="0ace9-104">The type of the second operand must be an [int](../../../csharp/language-reference/keywords/int.md) or a type that has a predefined implicit numeric conversion to `int`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ace9-105">Note</span><span class="sxs-lookup"><span data-stu-id="0ace9-105">Remarks</span></span>  
 <span data-ttu-id="0ace9-106">Se il primo operando è di tipo [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) (quantità a 32 bit), il conteggio dello spostamento è dato dai cinque bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="0ace9-106">If the first operand is an [int](../../../csharp/language-reference/keywords/int.md) or [uint](../../../csharp/language-reference/keywords/uint.md) (32-bit quantity), the shift count is given by the low-order five bits of the second operand.</span></span> <span data-ttu-id="0ace9-107">Il conteggio dello spostamento effettivo, quindi, è compreso tra 0 e 31 bit.</span><span class="sxs-lookup"><span data-stu-id="0ace9-107">That is, the actual shift count is 0 to 31 bits.</span></span>  
  
 <span data-ttu-id="0ace9-108">Se il primo operando è di tipo [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) (quantità a 64 bit), il conteggio dello spostamento è dato dai sei bit meno significativi del secondo operando.</span><span class="sxs-lookup"><span data-stu-id="0ace9-108">If the first operand is a [long](../../../csharp/language-reference/keywords/long.md) or [ulong](../../../csharp/language-reference/keywords/ulong.md) (64-bit quantity), the shift count is given by the low-order six bits of the second operand.</span></span> <span data-ttu-id="0ace9-109">Il conteggio dello spostamento effettivo, quindi, è compreso tra 0 e 63 bit.</span><span class="sxs-lookup"><span data-stu-id="0ace9-109">That is, the actual shift count is 0 to 63 bits.</span></span>  
  
 <span data-ttu-id="0ace9-110">Tutti i bit più significativi che non rientrano nell'intervallo del tipo del primo operando dopo lo spostamento vengono scartati, mentre i bit vuoti meno significativi vengono riempiti con zero.</span><span class="sxs-lookup"><span data-stu-id="0ace9-110">Any high-order bits that are not within the range of the type of the first operand after the shift are discarded, and the low-order empty bits are zero-filled.</span></span> <span data-ttu-id="0ace9-111">Le operazioni di spostamento non provocano mai overflow.</span><span class="sxs-lookup"><span data-stu-id="0ace9-111">Shift operations never cause overflows.</span></span>  
  
 <span data-ttu-id="0ace9-112">I tipi definiti dall'utente possono eseguire l'overload dell'operatore `<<` (vedere [operator](../../../csharp/language-reference/keywords/operator.md)): il tipo del primo operando deve essere il tipo definito dall'utente e il tipo del secondo operando deve essere `int`.</span><span class="sxs-lookup"><span data-stu-id="0ace9-112">User-defined types can overload the `<<` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)); the type of the first operand must be the user-defined type, and the type of the second operand must be `int`.</span></span> <span data-ttu-id="0ace9-113">Quando viene eseguito l'overload di un operatore binario, viene anche eseguito in modo implicito l'overload dell'operatore di assegnazione corrispondente, se presente.</span><span class="sxs-lookup"><span data-stu-id="0ace9-113">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ace9-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ace9-114">Example</span></span>  
 <span data-ttu-id="0ace9-115">[!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0ace9-115">[!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="0ace9-116">Commenti</span><span class="sxs-lookup"><span data-stu-id="0ace9-116">Comments</span></span>  
 <span data-ttu-id="0ace9-117">Osservare come `i<<1` e `i<<33` generino lo stesso risultato, poiché 1 e 33 hanno gli stessi cinque bit meno significativi.</span><span class="sxs-lookup"><span data-stu-id="0ace9-117">Note that `i<<1` and `i<<33` give the same result, because 1 and 33 have the same low-order five bits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ace9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ace9-118">See Also</span></span>  
 <span data-ttu-id="0ace9-119">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ace9-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0ace9-120">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0ace9-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0ace9-121">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="0ace9-121">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)


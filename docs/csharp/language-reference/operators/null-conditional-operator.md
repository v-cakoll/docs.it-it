---
title: ?? Operatore (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ??_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: 17
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
ms.openlocfilehash: 86e50b97d7ded8adc74f031faf026b69ccdd0c87
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="3d17a-103">??</span><span class="sxs-lookup"><span data-stu-id="3d17a-103">??</span></span> <span data-ttu-id="3d17a-104">Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3d17a-104">Operator (C# Reference)</span></span>
<span data-ttu-id="3d17a-105">L'operatore `??` viene chiamato operatore null-coalescing.</span><span class="sxs-lookup"><span data-stu-id="3d17a-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="3d17a-106">Restituisce l'operando sinistro se non è Null. In caso contrario, restituisce l'operando destro.</span><span class="sxs-lookup"><span data-stu-id="3d17a-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d17a-107">Note</span><span class="sxs-lookup"><span data-stu-id="3d17a-107">Remarks</span></span>  
 <span data-ttu-id="3d17a-108">Un tipo nullable può rappresentare un valore dal dominio del tipo oppure il valore può essere indefinito, nel qual caso è Null.</span><span class="sxs-lookup"><span data-stu-id="3d17a-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="3d17a-109">È possibile utilizzare l'espressività sintattica dell'operatore `??` per restituire un valore appropriato (l'operando destro) quando l'operando sinistro è un tipo nullable il cui valore è Null.</span><span class="sxs-lookup"><span data-stu-id="3d17a-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullible type whose value is null.</span></span> <span data-ttu-id="3d17a-110">Se si tenta di assegnare un tipo di valore nullable a un tipo non nullable senza utilizzare l'operatore `??`, verrà generato un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="3d17a-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="3d17a-111">Se si utilizza un cast e il tipo di valore nullable non è attualmente definito, verrà generata un'eccezione `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="3d17a-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="3d17a-112">Per altre informazioni, vedere [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="3d17a-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="3d17a-113">Il risultato di un operatore ??</span><span class="sxs-lookup"><span data-stu-id="3d17a-113">The result of a ??</span></span> <span data-ttu-id="3d17a-114">non viene considerato come una costante, anche se entrambi gli argomenti dell'operatore sono costanti.</span><span class="sxs-lookup"><span data-stu-id="3d17a-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d17a-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d17a-115">Example</span></span>  
 <span data-ttu-id="3d17a-116">[!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3d17a-116">[!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d17a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d17a-117">See Also</span></span>  
 <span data-ttu-id="3d17a-118">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d17a-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3d17a-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d17a-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3d17a-120">[Operatori C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d17a-120">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="3d17a-121">[Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d17a-121">[Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) </span></span>  
 [<span data-ttu-id="3d17a-122">Cosa significa esattamente "elevato"?</span><span class="sxs-lookup"><span data-stu-id="3d17a-122">What Exactly Does 'Lifted' mean?</span></span>](http://go.microsoft.com/fwlink/?LinkID=112382)


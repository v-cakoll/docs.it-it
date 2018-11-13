---
title: ?? Operatore (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: fbcfda07cc55628aeed82eb7561516f7012bc4fe
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2018
ms.locfileid: "50980674"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ee305-103">??</span><span class="sxs-lookup"><span data-stu-id="ee305-103">??</span></span> <span data-ttu-id="ee305-104">Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ee305-104">Operator (C# Reference)</span></span>
<span data-ttu-id="ee305-105">L'operatore `??` viene chiamato operatore null-coalescing.</span><span class="sxs-lookup"><span data-stu-id="ee305-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="ee305-106">Restituisce l'operando sinistro se non è Null. In caso contrario, restituisce l'operando destro.</span><span class="sxs-lookup"><span data-stu-id="ee305-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee305-107">Note</span><span class="sxs-lookup"><span data-stu-id="ee305-107">Remarks</span></span>  
 <span data-ttu-id="ee305-108">Un tipo nullable può rappresentare un valore dal dominio del tipo oppure il valore può essere indefinito, nel qual caso è Null.</span><span class="sxs-lookup"><span data-stu-id="ee305-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="ee305-109">È possibile usare l'espressività sintattica dell'operatore `??` per restituire un valore appropriato (l'operando destro) quando l'operando sinistro è un tipo nullable il cui valore è Null.</span><span class="sxs-lookup"><span data-stu-id="ee305-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="ee305-110">Se si tenta di assegnare un tipo di valore nullable a un tipo non nullable senza utilizzare l'operatore `??`, verrà generato un errore in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ee305-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="ee305-111">Se si utilizza un cast e il tipo di valore nullable non è attualmente definito, verrà generata un'eccezione `InvalidOperationException`.</span><span class="sxs-lookup"><span data-stu-id="ee305-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>  
  
 <span data-ttu-id="ee305-112">Per altre informazioni, vedere [Tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="ee305-112">For more information, see [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md).</span></span>  
  
 <span data-ttu-id="ee305-113">Il risultato di un operatore ??</span><span class="sxs-lookup"><span data-stu-id="ee305-113">The result of a ??</span></span> <span data-ttu-id="ee305-114">non viene considerato come una costante, anche se entrambi gli argomenti dell'operatore sono costanti.</span><span class="sxs-lookup"><span data-stu-id="ee305-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee305-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee305-115">Example</span></span>  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ee305-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ee305-116">C# Language Specification</span></span>  

<span data-ttu-id="ee305-117">Per altre informazioni, vedere [Operatore di unione Null](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="ee305-117">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="ee305-118">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="ee305-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ee305-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee305-119">See Also</span></span>

- [<span data-ttu-id="ee305-120">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="ee305-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="ee305-121">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ee305-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ee305-122">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="ee305-122">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="ee305-123">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="ee305-123">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
- [<span data-ttu-id="ee305-124">Cosa significa esattamente "elevato"?</span><span class="sxs-lookup"><span data-stu-id="ee305-124">What Exactly Does 'Lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)

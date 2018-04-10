---
title: where (vincolo di tipo generico) (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f2b7b159689aa771d3f9d59e3b1dd340c85b1d79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="5c25e-102">where (vincolo di tipo generico) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5c25e-102">where (generic type constraint) (C# Reference)</span></span>
<span data-ttu-id="5c25e-103">In una definizione di tipo generico, la clausola `where` viene usata per specificare i vincoli per i tipi che possono essere usati come argomenti per un parametro di tipo definito in una dichiarazione generica.</span><span class="sxs-lookup"><span data-stu-id="5c25e-103">In a generic type definition, the `where` clause is used to specify constraints on the types that can be used as arguments for a type parameter defined in a generic declaration.</span></span> <span data-ttu-id="5c25e-104">Ad esempio, una classe generica, `MyGenericClass`, può essere dichiarata in modo che tramite il parametro di tipo `T` venga implementata l'interfaccia <xref:System.IComparable%601>:</span><span class="sxs-lookup"><span data-stu-id="5c25e-104">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  <span data-ttu-id="5c25e-105">Per altre informazioni sulla clausola where in un'espressione di query, vedere [Clausola where](../../../csharp/language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5c25e-105">For more information on the where clause in a query expression, see [where clause](../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
 <span data-ttu-id="5c25e-106">Oltre ai vincoli di interfaccia, una clausola `where` può includere un vincolo di classe di base, che stabilisce che un tipo deve usare la classe specificata come classe di base (o essere la classe stessa) per poter essere usato come argomento di tipo per tale tipo generico.</span><span class="sxs-lookup"><span data-stu-id="5c25e-106">In addition to interface constraints, a `where` clause can include a base class constraint, which states that a type must have the specified class as a base class (or be that class itself) in order to be used as a type argument for that generic type.</span></span> <span data-ttu-id="5c25e-107">Se viene usato tale vincolo, deve apparire prima di tutti gli altri vincoli per quel parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="5c25e-107">If such a constraint is used, it must appear before any other constraints on that type parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 <span data-ttu-id="5c25e-108">La clausola `where` può anche includere un vincolo di costruttore.</span><span class="sxs-lookup"><span data-stu-id="5c25e-108">The `where` clause may also include a constructor constraint.</span></span> <span data-ttu-id="5c25e-109">È possibile creare un'istanza di un parametro di tipo usando l'operatore new. Tuttavia, per poter eseguire questa operazione, è necessario che il parametro di tipo sia vincolato dal vincolo di costruttore, `new()`.</span><span class="sxs-lookup"><span data-stu-id="5c25e-109">It is possible to create an instance of a type parameter using the new operator; however, in order to do so the type parameter must be constrained by the constructor constraint, `new()`.</span></span> <span data-ttu-id="5c25e-110">Il [vincolo new()](../../../csharp/language-reference/keywords/new-constraint.md) consente al compilatore di sapere che ogni argomento di tipo specificato deve usare un costruttore accessibile senza parametri o predefinito.</span><span class="sxs-lookup"><span data-stu-id="5c25e-110">The [new() Constraint](../../../csharp/language-reference/keywords/new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="5c25e-111">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5c25e-111">For example:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 <span data-ttu-id="5c25e-112">Il vincolo `new()` viene visualizzato per ultimo nella clausola `where`.</span><span class="sxs-lookup"><span data-stu-id="5c25e-112">The `new()` constraint appears last in the `where` clause.</span></span>  
  
 <span data-ttu-id="5c25e-113">Con più parametri di tipo, usare una clausola `where` per ogni parametro di tipo, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5c25e-113">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 <span data-ttu-id="5c25e-114">È anche possibile associare vincoli ai parametri di tipo di metodi generici, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5c25e-114">You can also attach constraints to type parameters of generic methods, like this:</span></span>  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 <span data-ttu-id="5c25e-115">Si noti che la sintassi usata per descrivere i vincoli dei parametri di tipo per i delegati è uguale a quella dei metodi:</span><span class="sxs-lookup"><span data-stu-id="5c25e-115">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 <span data-ttu-id="5c25e-116">Per informazioni sui delegati generici, vedere [Delegati generici](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="5c25e-116">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
 <span data-ttu-id="5c25e-117">Per informazioni dettagliate sulla sintassi e sull'uso dei vincoli, vedere [Vincoli sui parametri di tipo](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5c25e-117">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5c25e-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="5c25e-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c25e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c25e-119">See Also</span></span>  
 [<span data-ttu-id="5c25e-120">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="5c25e-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5c25e-121">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5c25e-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5c25e-122">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="5c25e-122">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [<span data-ttu-id="5c25e-123">Vincolo new</span><span class="sxs-lookup"><span data-stu-id="5c25e-123">new Constraint</span></span>](../../../csharp/language-reference/keywords/new-constraint.md)  
 [<span data-ttu-id="5c25e-124">Vincoli sui parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="5c25e-124">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)

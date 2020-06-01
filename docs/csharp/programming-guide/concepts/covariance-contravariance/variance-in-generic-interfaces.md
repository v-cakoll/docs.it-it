---
title: Varianza nelle interfacce generiche (C#)
ms.date: 06/06/2019
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: ea5d3d35bc9ee438263707efd16829b6217a1968
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241331"
---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="d1128-102">Varianza nelle interfacce generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="d1128-102">Variance in Generic Interfaces (C#)</span></span>

<span data-ttu-id="d1128-103">In .NET framework 4 è stato introdotto il supporto della varianza per diverse interfacce generiche esistenti.</span><span class="sxs-lookup"><span data-stu-id="d1128-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="d1128-104">Il supporto della varianza consente la conversione implicita delle classi che implementano tali interfacce.</span><span class="sxs-lookup"><span data-stu-id="d1128-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span>

<span data-ttu-id="d1128-105">A partire da .NET Framework 4, le interfacce seguenti sono varianti:</span><span class="sxs-lookup"><span data-stu-id="d1128-105">Starting with .NET Framework 4, the following interfaces are variant:</span></span>

- <span data-ttu-id="d1128-106"><xref:System.Collections.Generic.IEnumerable%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="d1128-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>

- <span data-ttu-id="d1128-107"><xref:System.Collections.Generic.IEnumerator%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="d1128-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>

- <span data-ttu-id="d1128-108"><xref:System.Linq.IQueryable%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="d1128-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>

- <span data-ttu-id="d1128-109"><xref:System.Linq.IGrouping%602> (`TKey` e `TElement` sono covarianti)</span><span class="sxs-lookup"><span data-stu-id="d1128-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>

- <span data-ttu-id="d1128-110"><xref:System.Collections.Generic.IComparer%601> (T è controvariante)</span><span class="sxs-lookup"><span data-stu-id="d1128-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="d1128-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T è controvariante)</span><span class="sxs-lookup"><span data-stu-id="d1128-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>

- <span data-ttu-id="d1128-112"><xref:System.IComparable%601> (T è controvariante)</span><span class="sxs-lookup"><span data-stu-id="d1128-112"><xref:System.IComparable%601> (T is contravariant)</span></span>

<span data-ttu-id="d1128-113">A partire da .NET Framework 4.5, le interfacce seguenti sono varianti:</span><span class="sxs-lookup"><span data-stu-id="d1128-113">Starting with .NET Framework 4.5, the following interfaces are variant:</span></span>

- <span data-ttu-id="d1128-114"><xref:System.Collections.Generic.IReadOnlyList%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="d1128-114"><xref:System.Collections.Generic.IReadOnlyList%601> (T is covariant)</span></span>

- <span data-ttu-id="d1128-115"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T è covariante)</span><span class="sxs-lookup"><span data-stu-id="d1128-115"><xref:System.Collections.Generic.IReadOnlyCollection%601> (T is covariant)</span></span>

<span data-ttu-id="d1128-116">La covarianza consente a un metodo di avere un tipo restituito più derivato rispetto a quello definito dal parametro di tipo generico dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d1128-116">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="d1128-117">Per illustrare la funzionalità di covarianza, considerare le seguenti interfacce generiche: `IEnumerable<Object>` e `IEnumerable<String>`.</span><span class="sxs-lookup"><span data-stu-id="d1128-117">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="d1128-118">L'interfaccia `IEnumerable<String>` non eredita l'interfaccia`IEnumerable<Object>`.</span><span class="sxs-lookup"><span data-stu-id="d1128-118">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="d1128-119">Tuttavia, il tipo `String` eredita il tipo `Object` e in alcuni casi è opportuno assegnare gli oggetti di ogni interfaccia all'altra.</span><span class="sxs-lookup"><span data-stu-id="d1128-119">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="d1128-120">Vedere il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d1128-120">This is shown in the following code example.</span></span>

```csharp
IEnumerable<String> strings = new List<String>();
IEnumerable<Object> objects = strings;
```

<span data-ttu-id="d1128-121">Nelle versioni precedenti di .NET Framework, questo codice causa un errore di compilazione in C# e, se `Option Strict` è attivato, in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d1128-121">In earlier versions of .NET Framework, this code causes a compilation error in C# and, if `Option Strict` is on, in Visual Basic.</span></span> <span data-ttu-id="d1128-122">Ora è invece possibile usare `strings` anziché `objects`, come illustrato nell'esempio precedente, poiché l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> è covariante.</span><span class="sxs-lookup"><span data-stu-id="d1128-122">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>

<span data-ttu-id="d1128-123">La controvarianza consente a un metodo di avere tipi di argomenti meno derivati rispetto a quelli specificati dal parametro generico dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d1128-123">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="d1128-124">Per illustrare la controvarianza, si supponga di aver creato una classe `BaseComparer` per confrontare le istanze della classe `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="d1128-124">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="d1128-125">La classe `BaseComparer` implementa l'interfaccia `IEqualityComparer<BaseClass>`.</span><span class="sxs-lookup"><span data-stu-id="d1128-125">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="d1128-126">Poiché l'interfaccia `BaseClass` è ora controvariante, è possibile usare <xref:System.Collections.Generic.IEqualityComparer%601> per confrontare le istanze delle classi che ereditano la classe `BaseComparer`.</span><span class="sxs-lookup"><span data-stu-id="d1128-126">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="d1128-127">Vedere il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d1128-127">This is shown in the following code example.</span></span>

```csharp
// Simple hierarchy of classes.
class BaseClass { }
class DerivedClass : BaseClass { }

// Comparer class.
class BaseComparer : IEqualityComparer<BaseClass>
{
    public int GetHashCode(BaseClass baseInstance)
    {
        return baseInstance.GetHashCode();
    }
    public bool Equals(BaseClass x, BaseClass y)
    {
        return x == y;
    }
}
class Program
{
    static void Test()
    {
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();

        // Implicit conversion of IEqualityComparer<BaseClass> to
        // IEqualityComparer<DerivedClass>.
        IEqualityComparer<DerivedClass> childComparer = baseComparer;
    }
}
```

<span data-ttu-id="d1128-128">Per altri esempi, vedere [Uso della varianza nelle interfacce per le raccolte generiche (C#)](./using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="d1128-128">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](./using-variance-in-interfaces-for-generic-collections.md).</span></span>

<span data-ttu-id="d1128-129">La varianza nelle interfacce generiche è supportata solo per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="d1128-129">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="d1128-130">I tipi di valore non supportano la varianza.</span><span class="sxs-lookup"><span data-stu-id="d1128-130">Value types do not support variance.</span></span> <span data-ttu-id="d1128-131">Ad esempio, non è possibile convertire `IEnumerable<int>` in modo implicito in `IEnumerable<object>` perché i valori integer sono rappresentati da un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="d1128-131">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>

```csharp
IEnumerable<int> integers = new List<int>();
// The following statement generates a compiler error,
// because int is a value type.
// IEnumerable<Object> objects = integers;
```

<span data-ttu-id="d1128-132">È anche importante ricordare che le classi che implementano le interfacce varianti sono comunque invariabili.</span><span class="sxs-lookup"><span data-stu-id="d1128-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="d1128-133">Ad esempio, sebbene <xref:System.Collections.Generic.List%601> implementi l'interfaccia covariante <xref:System.Collections.Generic.IEnumerable%601>, non è possibile convertire `List<String>` in `List<Object>` in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="d1128-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<String>` to `List<Object>`.</span></span> <span data-ttu-id="d1128-134">come illustra l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d1128-134">This is illustrated in the following code example.</span></span>

```csharp
// The following line generates a compiler error
// because classes are invariant.
// List<Object> list = new List<String>();

// You can use the interface object instead.
IEnumerable<Object> listObjects = new List<String>();
```

## <a name="see-also"></a><span data-ttu-id="d1128-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1128-135">See also</span></span>

- [<span data-ttu-id="d1128-136">Uso della varianza nelle interfacce per le raccolte generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="d1128-136">Using Variance in Interfaces for Generic Collections (C#)</span></span>](./using-variance-in-interfaces-for-generic-collections.md)
- [<span data-ttu-id="d1128-137">Creazione di interfacce generiche varianti (C#)</span><span class="sxs-lookup"><span data-stu-id="d1128-137">Creating Variant Generic Interfaces (C#)</span></span>](./creating-variant-generic-interfaces.md)
- [<span data-ttu-id="d1128-138">Interfacce generiche</span><span class="sxs-lookup"><span data-stu-id="d1128-138">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)
- [<span data-ttu-id="d1128-139">Varianza nei delegati (C#)</span><span class="sxs-lookup"><span data-stu-id="d1128-139">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)

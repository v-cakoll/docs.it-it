---
title: Creazione di interfacce generiche varianti (C#)
description: Informazioni su come creare interfacce generiche variant con parametri di tipo generico covariante o controvariante.
ms.date: 07/20/2015
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
ms.openlocfilehash: 38b32784b681e748cd508c3d431fd4b18ec2c81a
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105727"
---
# <a name="creating-variant-generic-interfaces-c"></a><span data-ttu-id="2443e-103">Creazione di interfacce generiche varianti (C#)</span><span class="sxs-lookup"><span data-stu-id="2443e-103">Creating Variant Generic Interfaces (C#)</span></span>

<span data-ttu-id="2443e-104">È possibile dichiarare parametri di tipo generico nelle interfacce come covarianti o controvarianti.</span><span class="sxs-lookup"><span data-stu-id="2443e-104">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="2443e-105">La *covarianza* consente ai metodi di interfaccia di avere tipi restituiti più derivati rispetto a quelli definiti dai parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="2443e-105">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="2443e-106">La *controvarianza* consente ai metodi di interfaccia di avere tipi di argomenti meno derivati rispetto a quelli specificati dai parametri generici.</span><span class="sxs-lookup"><span data-stu-id="2443e-106">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="2443e-107">Un'interfaccia generica che ha parametri di tipo generico varianti e covarianti è definita *variante*.</span><span class="sxs-lookup"><span data-stu-id="2443e-107">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>

> [!NOTE]
> <span data-ttu-id="2443e-108">In .NET framework 4 è stato introdotto il supporto della varianza per diverse interfacce generiche esistenti.</span><span class="sxs-lookup"><span data-stu-id="2443e-108">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="2443e-109">Per l'elenco delle interfacce variant in .NET, vedere [varianza nelle interfacce generiche (C#)](./variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="2443e-109">For the list of the variant interfaces in .NET, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md).</span></span>

## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="2443e-110">Dichiarazione delle interfacce generiche varianti</span><span class="sxs-lookup"><span data-stu-id="2443e-110">Declaring Variant Generic Interfaces</span></span>

<span data-ttu-id="2443e-111">È possibile dichiarare le interfacce generiche varianti usando le parole chiave `in` e `out` per i parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="2443e-111">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2443e-112">I parametri `ref`, `in` e `out` in C# non possono essere varianti.</span><span class="sxs-lookup"><span data-stu-id="2443e-112">`ref`, `in`, and `out` parameters in C# cannot be variant.</span></span> <span data-ttu-id="2443e-113">Anche i tipi di valore non supportano la varianza.</span><span class="sxs-lookup"><span data-stu-id="2443e-113">Value types also do not support variance.</span></span>

<span data-ttu-id="2443e-114">È possibile dichiarare un parametro di tipo generico covariante usando la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="2443e-114">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="2443e-115">Il tipo covariante deve soddisfare le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2443e-115">The covariant type must satisfy the following conditions:</span></span>

- <span data-ttu-id="2443e-116">Il tipo viene usato solo come tipo restituito dei metodi di interfaccia e non come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="2443e-116">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="2443e-117">Come illustrato nell'esempio seguente, il tipo `R` viene dichiarato covariante.</span><span class="sxs-lookup"><span data-stu-id="2443e-117">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        R GetSomething();
        // The following statement generates a compiler error.
        // void SetSomething(R sampleArg);

    }
    ```

    <span data-ttu-id="2443e-118">Esiste un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="2443e-118">There is one exception to this rule.</span></span> <span data-ttu-id="2443e-119">Se si usa un delegato generico controvariante come parametro di metodo, è possibile usare il tipo come parametro di tipo generico per il delegato.</span><span class="sxs-lookup"><span data-stu-id="2443e-119">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="2443e-120">Questo aspetto è illustrato nell'esempio seguente dal tipo `R`.</span><span class="sxs-lookup"><span data-stu-id="2443e-120">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="2443e-121">Per altre informazioni, vedere [Uso della varianza nei delegati (C#)](./variance-in-delegates.md) e [Uso della varianza per i delegati generici Func e Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="2443e-121">For more information, see [Variance in Delegates (C#)](./variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        void DoSomething(Action<R> callback);
    }
    ```

- <span data-ttu-id="2443e-122">Il tipo non viene usato come vincolo generico per i metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2443e-122">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="2443e-123">Questa situazione è illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2443e-123">This is illustrated in the following code.</span></span>

    ```csharp
    interface ICovariant<out R>
    {
        // The following statement generates a compiler error
        // because you can use only contravariant or invariant types
        // in generic constraints.
        // void DoSomething<T>() where T : R;
    }
    ```

<span data-ttu-id="2443e-124">È possibile dichiarare un parametro di tipo generico controvariante usando la parola chiave `in`.</span><span class="sxs-lookup"><span data-stu-id="2443e-124">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="2443e-125">Il tipo controvariante può essere usato solo come tipo di argomenti del metodo e non come tipo restituito dei metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2443e-125">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="2443e-126">Il tipo controvariante può essere usato anche per i vincoli generici.</span><span class="sxs-lookup"><span data-stu-id="2443e-126">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="2443e-127">Il codice seguente illustra come dichiarare un'interfaccia controvariante e usare un vincolo generico per uno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="2443e-127">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>

```csharp
interface IContravariant<in A>
{
    void SetSomething(A sampleArg);
    void DoSomething<T>() where T : A;
    // The following statement generates a compiler error.
    // A GetSomething();
}
```

<span data-ttu-id="2443e-128">È anche possibile supportare sia la covarianza che la controvarianza nella stessa interfaccia, ma per parametri di tipo diverso, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2443e-128">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>

```csharp
interface IVariant<out R, in A>
{
    R GetSomething();
    void SetSomething(A sampleArg);
    R GetSetSomethings(A sampleArg);
}
```

## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="2443e-129">Implementazione di interfacce generiche varianti</span><span class="sxs-lookup"><span data-stu-id="2443e-129">Implementing Variant Generic Interfaces</span></span>

<span data-ttu-id="2443e-130">Implementare le interfacce generiche varianti nelle classi usando la stessa sintassi usata per le interfacce invariabili.</span><span class="sxs-lookup"><span data-stu-id="2443e-130">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="2443e-131">L'esempio di codice seguente illustra come implementare un'interfaccia covariante in una classe generica.</span><span class="sxs-lookup"><span data-stu-id="2443e-131">The following code example shows how to implement a covariant interface in a generic class.</span></span>

```csharp
interface ICovariant<out R>
{
    R GetSomething();
}
class SampleImplementation<R> : ICovariant<R>
{
    public R GetSomething()
    {
        // Some code.
        return default(R);
    }
}
```

<span data-ttu-id="2443e-132">Le classi che implementano le interfacce varianti sono invariabili.</span><span class="sxs-lookup"><span data-stu-id="2443e-132">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="2443e-133">Si consideri il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2443e-133">For example, consider the following code.</span></span>

```csharp
// The interface is covariant.
ICovariant<Button> ibutton = new SampleImplementation<Button>();
ICovariant<Object> iobj = ibutton;

// The class is invariant.
SampleImplementation<Button> button = new SampleImplementation<Button>();
// The following statement generates a compiler error
// because classes are invariant.
// SampleImplementation<Object> obj = button;
```

## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="2443e-134">Estensione di interfacce generiche varianti</span><span class="sxs-lookup"><span data-stu-id="2443e-134">Extending Variant Generic Interfaces</span></span>

<span data-ttu-id="2443e-135">Quando si estende un'interfaccia generica variante è necessario usare le parole chiave `in` e `out` per specificare in modo esplicito se l'interfaccia derivata supporta la varianza.</span><span class="sxs-lookup"><span data-stu-id="2443e-135">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="2443e-136">Il compilatore non deduce la varianza dall'interfaccia che viene estesa.</span><span class="sxs-lookup"><span data-stu-id="2443e-136">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="2443e-137">Si considerino ad esempio le interfacce seguenti.</span><span class="sxs-lookup"><span data-stu-id="2443e-137">For example, consider the following interfaces.</span></span>

```csharp
interface ICovariant<out T> { }
interface IInvariant<T> : ICovariant<T> { }
interface IExtCovariant<out T> : ICovariant<T> { }
```

<span data-ttu-id="2443e-138">Nell'interfaccia `IInvariant<T>` il parametro di tipo generico `T` è invariabile, mentre in `IExtCovariant<out T>` il parametro di tipo è covariante, anche se entrambe le interfacce estendono la stessa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2443e-138">In the `IInvariant<T>` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant<out T>` the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="2443e-139">La stessa regola viene applicata ai parametri di tipo generico controvarianti.</span><span class="sxs-lookup"><span data-stu-id="2443e-139">The same rule is applied to contravariant generic type parameters.</span></span>

<span data-ttu-id="2443e-140">È possibile creare un'interfaccia che estende sia l'interfaccia in cui il parametro di tipo generico `T` è covariante, sia l'interfaccia in cui è controvariante se nell'interfaccia che viene estesa il parametro di tipo generico `T` è invariabile,</span><span class="sxs-lookup"><span data-stu-id="2443e-140">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="2443e-141">come illustra l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2443e-141">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
interface IContravariant<in T> { }
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }
```

<span data-ttu-id="2443e-142">Tuttavia, se un parametro di tipo generico `T` è dichiarato covariante in una sola interfaccia, non è possibile dichiararlo controvariante nell'interfaccia da estendere o viceversa,</span><span class="sxs-lookup"><span data-stu-id="2443e-142">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="2443e-143">come illustra l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="2443e-143">This is illustrated in the following code example.</span></span>

```csharp
interface ICovariant<out T> { }
// The following statement generates a compiler error.
// interface ICoContraVariant<in T> : ICovariant<T> { }
```

### <a name="avoiding-ambiguity"></a><span data-ttu-id="2443e-144">Evitare le ambiguità</span><span class="sxs-lookup"><span data-stu-id="2443e-144">Avoiding Ambiguity</span></span>

<span data-ttu-id="2443e-145">Quando si implementano le interfacce generiche varianti, la varianza può talvolta causare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="2443e-145">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="2443e-146">Tale ambiguità dovrebbe essere evitata.</span><span class="sxs-lookup"><span data-stu-id="2443e-146">Such ambiguity should be avoided.</span></span>

<span data-ttu-id="2443e-147">Ad esempio, se si implementa in modo esplicito la stessa interfaccia generica variante con parametri di tipo generico diversi in una sola classe, è possibile creare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="2443e-147">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="2443e-148">Il compilatore non genera un errore in questo caso, ma non viene specificato quale implementazione dell'interfaccia verrà scelta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2443e-148">The compiler does not produce an error in this case, but it's not specified which interface implementation will be chosen at run time.</span></span> <span data-ttu-id="2443e-149">Questa ambiguità potrebbe causare bug sottili nel codice.</span><span class="sxs-lookup"><span data-stu-id="2443e-149">This ambiguity could lead to subtle bugs in your code.</span></span> <span data-ttu-id="2443e-150">Osservare l'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2443e-150">Consider the following code example.</span></span>

```csharp
// Simple class hierarchy.
class Animal { }
class Cat : Animal { }
class Dog : Animal { }

// This class introduces ambiguity
// because IEnumerable<out T> is covariant.
class Pets : IEnumerable<Cat>, IEnumerable<Dog>
{
    IEnumerator<Cat> IEnumerable<Cat>.GetEnumerator()
    {
        Console.WriteLine("Cat");
        // Some code.
        return null;
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        // Some code.
        return null;
    }

    IEnumerator<Dog> IEnumerable<Dog>.GetEnumerator()
    {
        Console.WriteLine("Dog");
        // Some code.
        return null;
    }
}
class Program
{
    public static void Test()
    {
        IEnumerable<Animal> pets = new Pets();
        pets.GetEnumerator();
    }
}
```

<span data-ttu-id="2443e-151">In questo esempio non viene specificato in che modo il metodo `pets.GetEnumerator` sceglie tra `Cat` e `Dog`.</span><span class="sxs-lookup"><span data-stu-id="2443e-151">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="2443e-152">Ciò potrebbe causare problemi nel codice.</span><span class="sxs-lookup"><span data-stu-id="2443e-152">This could cause problems in your code.</span></span>

## <a name="see-also"></a><span data-ttu-id="2443e-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2443e-153">See also</span></span>

- [<span data-ttu-id="2443e-154">Varianza nelle interfacce generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="2443e-154">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)
- [<span data-ttu-id="2443e-155">Uso della varianza per i delegati generici Func e Action (C#)</span><span class="sxs-lookup"><span data-stu-id="2443e-155">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)

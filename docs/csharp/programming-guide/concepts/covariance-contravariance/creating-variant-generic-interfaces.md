---
title: Creazione di interfacce generiche varianti (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0a6ba6bd85d0bdfa7e98dd85886fee89527b59fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="creating-variant-generic-interfaces-c"></a><span data-ttu-id="62ada-102">Creazione di interfacce generiche varianti (C#)</span><span class="sxs-lookup"><span data-stu-id="62ada-102">Creating Variant Generic Interfaces (C#)</span></span>
<span data-ttu-id="62ada-103">È possibile dichiarare parametri di tipo generico nelle interfacce come covarianti o controvarianti.</span><span class="sxs-lookup"><span data-stu-id="62ada-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="62ada-104">La *covarianza* consente ai metodi di interfaccia di avere tipi restituiti più derivati rispetto a quelli definiti dai parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="62ada-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="62ada-105">La *controvarianza* consente ai metodi di interfaccia di avere tipi di argomenti meno derivati rispetto a quelli specificati dai parametri generici.</span><span class="sxs-lookup"><span data-stu-id="62ada-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="62ada-106">Un'interfaccia generica che ha parametri di tipo generico varianti e covarianti è definita *variante*.</span><span class="sxs-lookup"><span data-stu-id="62ada-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62ada-107">In .NET framework 4 è stato introdotto il supporto della varianza per diverse interfacce generiche esistenti.</span><span class="sxs-lookup"><span data-stu-id="62ada-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="62ada-108">Per l'elenco delle interfacce varianti in .NET Framework, vedere [Varianza nelle interfacce generiche (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="62ada-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="62ada-109">Dichiarazione delle interfacce generiche varianti</span><span class="sxs-lookup"><span data-stu-id="62ada-109">Declaring Variant Generic Interfaces</span></span>  
 <span data-ttu-id="62ada-110">È possibile dichiarare le interfacce generiche varianti usando le parole chiave `in` e `out` per i parametri di tipo generico.</span><span class="sxs-lookup"><span data-stu-id="62ada-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="62ada-111">I parametri `ref` e `out` in C# non possono essere varianti.</span><span class="sxs-lookup"><span data-stu-id="62ada-111">`ref` and `out` parameters in C# cannot be variant.</span></span> <span data-ttu-id="62ada-112">Anche i tipi di valore non supportano la varianza.</span><span class="sxs-lookup"><span data-stu-id="62ada-112">Value types also do not support variance.</span></span>  
  
 <span data-ttu-id="62ada-113">È possibile dichiarare un parametro di tipo generico covariante usando la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="62ada-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="62ada-114">Il tipo covariante deve soddisfare le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62ada-114">The covariant type must satisfy the following conditions:</span></span>  
  
-   <span data-ttu-id="62ada-115">Il tipo viene usato solo come tipo restituito dei metodi di interfaccia e non come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="62ada-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="62ada-116">Come illustrato nell'esempio seguente, il tipo `R` viene dichiarato covariante.</span><span class="sxs-lookup"><span data-stu-id="62ada-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>  
  
    ```csharp  
    interface ICovariant<out R>  
    {  
        R GetSomething();  
        // The following statement generates a compiler error.  
        // void SetSometing(R sampleArg);  
  
    }  
    ```  
  
     <span data-ttu-id="62ada-117">Esiste un'eccezione a questa regola.</span><span class="sxs-lookup"><span data-stu-id="62ada-117">There is one exception to this rule.</span></span> <span data-ttu-id="62ada-118">Se si usa un delegato generico controvariante come parametro di metodo, è possibile usare il tipo come parametro di tipo generico per il delegato.</span><span class="sxs-lookup"><span data-stu-id="62ada-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="62ada-119">Questo aspetto è illustrato nell'esempio seguente dal tipo `R`.</span><span class="sxs-lookup"><span data-stu-id="62ada-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="62ada-120">Per altre informazioni, vedere [Uso della varianza nei delegati (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) e [Uso della varianza per i delegati generici Func e Action (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="62ada-120">For more information, see [Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
    ```csharp  
    interface ICovariant<out R>  
    {  
        void DoSomething(Action<R> callback);  
    }  
    ```  
  
-   <span data-ttu-id="62ada-121">Il tipo non viene usato come vincolo generico per i metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="62ada-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="62ada-122">Questa situazione è illustrata nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="62ada-122">This is illustrated in the following code.</span></span>  
  
    ```csharp  
    interface ICovariant<out R>  
    {  
        // The following statement generates a compiler error  
        // because you can use only contravariant or invariant types  
        // in generic contstraints.  
        // void DoSomething<T>() where T : R;  
    }  
    ```  
  
 <span data-ttu-id="62ada-123">È possibile dichiarare un parametro di tipo generico controvariante usando la parola chiave `in`.</span><span class="sxs-lookup"><span data-stu-id="62ada-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="62ada-124">Il tipo controvariante può essere usato solo come tipo di argomenti del metodo e non come tipo restituito dei metodi di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="62ada-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="62ada-125">Il tipo controvariante può essere usato anche per i vincoli generici.</span><span class="sxs-lookup"><span data-stu-id="62ada-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="62ada-126">Il codice seguente illustra come dichiarare un'interfaccia controvariante e usare un vincolo generico per uno dei relativi metodi.</span><span class="sxs-lookup"><span data-stu-id="62ada-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>  
  
```csharp  
interface IContravariant<in A>  
{  
    void SetSomething(A sampleArg);  
    void DoSomething<T>() where T : A;  
    // The following statement generates a compiler error.  
    // A GetSomething();              
}  
```  
  
 <span data-ttu-id="62ada-127">È anche possibile supportare sia la covarianza che la controvarianza nella stessa interfaccia, ma per parametri di tipo diverso, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="62ada-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>  
  
```csharp  
interface IVariant<out R, in A>  
{  
    R GetSomething();  
    void SetSomething(A sampleArg);  
    R GetSetSometings(A sampleArg);  
}  
```  
  
## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="62ada-128">Implementazione di interfacce generiche varianti</span><span class="sxs-lookup"><span data-stu-id="62ada-128">Implementing Variant Generic Interfaces</span></span>  
 <span data-ttu-id="62ada-129">Implementare le interfacce generiche varianti nelle classi usando la stessa sintassi usata per le interfacce invariabili.</span><span class="sxs-lookup"><span data-stu-id="62ada-129">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="62ada-130">L'esempio di codice seguente illustra come implementare un'interfaccia covariante in una classe generica.</span><span class="sxs-lookup"><span data-stu-id="62ada-130">The following code example shows how to implement a covariant interface in a generic class.</span></span>  
  
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
  
 <span data-ttu-id="62ada-131">Le classi che implementano le interfacce varianti sono invariabili.</span><span class="sxs-lookup"><span data-stu-id="62ada-131">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="62ada-132">Si consideri il codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="62ada-132">For example, consider the following code.</span></span>  
  
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
  
## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="62ada-133">Estensione di interfacce generiche varianti</span><span class="sxs-lookup"><span data-stu-id="62ada-133">Extending Variant Generic Interfaces</span></span>  
 <span data-ttu-id="62ada-134">Quando si estende un'interfaccia generica variante è necessario usare le parole chiave `in` e `out` per specificare in modo esplicito se l'interfaccia derivata supporta la varianza.</span><span class="sxs-lookup"><span data-stu-id="62ada-134">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="62ada-135">Il compilatore non deduce la varianza dall'interfaccia che viene estesa.</span><span class="sxs-lookup"><span data-stu-id="62ada-135">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="62ada-136">Si considerino ad esempio le interfacce seguenti.</span><span class="sxs-lookup"><span data-stu-id="62ada-136">For example, consider the following interfaces.</span></span>  
  
```csharp  
interface ICovariant<out T> { }  
interface IInvariant<T> : ICovariant<T> { }  
interface IExtCovariant<out T> : ICovariant<T> { }  
```  
  
 <span data-ttu-id="62ada-137">Nell'interfaccia `IInvariant<T>` il parametro di tipo generico `T` è invariabile, mentre in `IExtCovariant<out T>` il parametro di tipo è covariante, anche se entrambe le interfacce estendono la stessa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="62ada-137">In the `IInvariant<T>` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant<out T>` the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="62ada-138">La stessa regola viene applicata ai parametri di tipo generico controvarianti.</span><span class="sxs-lookup"><span data-stu-id="62ada-138">The same rule is applied to contravariant generic type parameters.</span></span>  
  
 <span data-ttu-id="62ada-139">È possibile creare un'interfaccia che estende sia l'interfaccia in cui il parametro di tipo generico `T` è covariante, sia l'interfaccia in cui è controvariante se nell'interfaccia che viene estesa il parametro di tipo generico `T` è invariabile,</span><span class="sxs-lookup"><span data-stu-id="62ada-139">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="62ada-140">come illustra l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="62ada-140">This is illustrated in the following code example.</span></span>  
  
```csharp  
interface ICovariant<out T> { }  
interface IContravariant<in T> { }  
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }  
```  
  
 <span data-ttu-id="62ada-141">Tuttavia, se un parametro di tipo generico `T` è dichiarato covariante in una sola interfaccia, non è possibile dichiararlo controvariante nell'interfaccia da estendere o viceversa,</span><span class="sxs-lookup"><span data-stu-id="62ada-141">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="62ada-142">come illustra l'esempio di codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="62ada-142">This is illustrated in the following code example.</span></span>  
  
```csharp  
interface ICovariant<out T> { }  
// The following statement generates a compiler error.  
// interface ICoContraVariant<in T> : ICovariant<T> { }  
```  
  
### <a name="avoiding-ambiguity"></a><span data-ttu-id="62ada-143">Evitare le ambiguità</span><span class="sxs-lookup"><span data-stu-id="62ada-143">Avoiding Ambiguity</span></span>  
 <span data-ttu-id="62ada-144">Quando si implementano le interfacce generiche varianti, la varianza può talvolta causare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="62ada-144">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="62ada-145">Questa evenienza deve essere evitata.</span><span class="sxs-lookup"><span data-stu-id="62ada-145">This should be avoided.</span></span>  
  
 <span data-ttu-id="62ada-146">Ad esempio, se si implementa in modo esplicito la stessa interfaccia generica variante con parametri di tipo generico diversi in una sola classe, è possibile creare ambiguità.</span><span class="sxs-lookup"><span data-stu-id="62ada-146">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="62ada-147">Il compilatore non genera un errore in questo caso, ma non viene specificato quale implementazione dell'interfaccia verrà scelta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="62ada-147">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="62ada-148">Questo potrebbe causare bug nel codice.</span><span class="sxs-lookup"><span data-stu-id="62ada-148">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="62ada-149">Si prenda in considerazione il seguente esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="62ada-149">Consider the following code example.</span></span>  
  
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
  
 <span data-ttu-id="62ada-150">In questo esempio non viene specificato in che modo il metodo `pets.GetEnumerator` sceglie tra `Cat` e `Dog`.</span><span class="sxs-lookup"><span data-stu-id="62ada-150">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="62ada-151">Ciò potrebbe causare problemi nel codice.</span><span class="sxs-lookup"><span data-stu-id="62ada-151">This could cause problems in your code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ada-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62ada-152">See Also</span></span>  
 [<span data-ttu-id="62ada-153">Varianza nelle interfacce generiche (C#)</span><span class="sxs-lookup"><span data-stu-id="62ada-153">Variance in Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [<span data-ttu-id="62ada-154">Uso della varianza per i delegati generici Func e Action (C#)</span><span class="sxs-lookup"><span data-stu-id="62ada-154">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)

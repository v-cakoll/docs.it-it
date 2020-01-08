---
title: Varianza nei delegati (C#)
ms.date: 07/20/2015
ms.assetid: 19de89d2-8224-4406-8964-2965b732b890
ms.openlocfilehash: cdf7cad97ececbf4baae8328b1df55318c627cbb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345172"
---
# <a name="variance-in-delegates-c"></a><span data-ttu-id="1a78a-102">Varianza nei delegati (C#)</span><span class="sxs-lookup"><span data-stu-id="1a78a-102">Variance in Delegates (C#)</span></span>
<span data-ttu-id="1a78a-103">In .NET framework 3.5 è stato introdotto il supporto della varianza per la corrispondenza delle firme del metodo con i tipi di delegati in tutti i delegati in C#.</span><span class="sxs-lookup"><span data-stu-id="1a78a-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C#.</span></span> <span data-ttu-id="1a78a-104">Ciò significa che è possibile assegnare ai delegati non solo i metodi con firme corrispondenti, ma anche i metodi che restituiscono più tipi derivati (covarianza) o accettano parametri con meno tipi derivati (controvarianza) rispetto a quelli specificati dal tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="1a78a-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="1a78a-105">Sono inclusi sia i delegati generici che quelli non generici.</span><span class="sxs-lookup"><span data-stu-id="1a78a-105">This includes both generic and non-generic delegates.</span></span>  
  
 <span data-ttu-id="1a78a-106">Ad esempio, si consideri il codice seguente, che ha due classi e due delegati: generico e non generico.</span><span class="sxs-lookup"><span data-stu-id="1a78a-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>  
  
```csharp  
public class First { }  
public class Second : First { }  
public delegate First SampleDelegate(Second a);  
public delegate R SampleGenericDelegate<A, R>(A a);  
```  
  
 <span data-ttu-id="1a78a-107">Quando si creano i delegati dei tipi `SampleDelegate` o `SampleGenericDelegate<A, R>` è possibile assegnare uno qualsiasi dei metodi seguenti ai delegati.</span><span class="sxs-lookup"><span data-stu-id="1a78a-107">When you create delegates of the `SampleDelegate` or `SampleGenericDelegate<A, R>` types, you can assign any one of the following methods to those delegates.</span></span>  
  
```csharp  
// Matching signature.  
public static First ASecondRFirst(Second second)  
{ return new First(); }  
  
// The return type is more derived.  
public static Second ASecondRSecond(Second second)  
{ return new Second(); }  
  
// The argument type is less derived.  
public static First AFirstRFirst(First first)  
{ return new First(); }  
  
// The return type is more derived   
// and the argument type is less derived.  
public static Second AFirstRSecond(First first)  
{ return new Second(); }  
```  
  
 <span data-ttu-id="1a78a-108">L'esempio di codice seguente viene illustra la conversione implicita tra la firma del metodo e il tipo di delegato.</span><span class="sxs-lookup"><span data-stu-id="1a78a-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>  
  
```csharp  
// Assigning a method with a matching signature   
// to a non-generic delegate. No conversion is necessary.  
SampleDelegate dNonGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type   
// and less derived argument type to a non-generic delegate.  
// The implicit conversion is used.  
SampleDelegate dNonGenericConversion = AFirstRSecond;  
  
// Assigning a method with a matching signature to a generic delegate.  
// No conversion is necessary.  
SampleGenericDelegate<Second, First> dGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type   
// and less derived argument type to a generic delegate.  
// The implicit conversion is used.  
SampleGenericDelegate<Second, First> dGenericConversion = AFirstRSecond;  
```  
  
 <span data-ttu-id="1a78a-109">Per altri esempi, vedere [Uso della varianza nei delegati (C#)](./using-variance-in-delegates.md) e [Uso della varianza per i delegati generici Func e Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="1a78a-109">For more examples, see [Using Variance in Delegates (C#)](./using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="1a78a-110">Varianza nei parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="1a78a-110">Variance in Generic Type Parameters</span></span>  
 <span data-ttu-id="1a78a-111">In .NET Framework 4 o versioni successive è possibile abilitare la conversione implicita tra delegati, in modo che i delegati generici con tipi diversi specificati dai parametri di tipo generico possano essere assegnati l'uno all'altro, se i tipi vengono ereditati reciprocamente come richiesto dalla varianza.</span><span class="sxs-lookup"><span data-stu-id="1a78a-111">In .NET Framework 4 or later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>  
  
 <span data-ttu-id="1a78a-112">Per abilitare la conversione implicita, è necessario dichiarare esplicitamente i parametri generici in un delegato come covariante o controvariante usando la parola chiave `in` o `out`.</span><span class="sxs-lookup"><span data-stu-id="1a78a-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>  
  
 <span data-ttu-id="1a78a-113">L'esempio di codice seguente illustra come creare un delegato con un parametro di tipo generico covariante.</span><span class="sxs-lookup"><span data-stu-id="1a78a-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>  
  
```csharp  
// Type T is declared covariant by using the out keyword.  
public delegate T SampleGenericDelegate <out T>();  
  
public static void Test()  
{  
    SampleGenericDelegate <String> dString = () => " ";  
  
    // You can assign delegates to each other,  
    // because the type T is declared covariant.  
    SampleGenericDelegate <Object> dObject = dString;             
}  
```  
  
 <span data-ttu-id="1a78a-114">Se si usa solo il supporto della varianza per la corrispondenza delle firme del metodo con i tipi delegati e non si usano le parole chiave `in` e `out`, è possibile che in alcuni casi si possano creare istanze di delegati con metodi o espressioni lambda identici, ma non è possibile assegnare un delegato a un altro.</span><span class="sxs-lookup"><span data-stu-id="1a78a-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>  
  
 <span data-ttu-id="1a78a-115">Nell'esempio di codice seguente non è possibile convertire in modo esplicito `SampleGenericDelegate<String>` in `SampleGenericDelegate<Object>`, sebbene `String` erediti `Object`.</span><span class="sxs-lookup"><span data-stu-id="1a78a-115">In the following code example, `SampleGenericDelegate<String>` cannot be explicitly converted to `SampleGenericDelegate<Object>`, although `String` inherits `Object`.</span></span> <span data-ttu-id="1a78a-116">È possibile correggere questo problema contrassegnando il parametro generico `T` con la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="1a78a-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>  
  
```csharp  
public delegate T SampleGenericDelegate<T>();  
  
public static void Test()  
{  
    SampleGenericDelegate<String> dString = () => " ";  
  
    // You can assign the dObject delegate  
    // to the same lambda expression as dString delegate  
    // because of the variance support for   
    // matching method signatures with delegate types.  
    SampleGenericDelegate<Object> dObject = () => " ";  
  
    // The following statement generates a compiler error  
    // because the generic type T is not marked as covariant.  
    // SampleGenericDelegate <Object> dObject = dString;  
  
}  
```  
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="1a78a-117">Delegati generici con parametri di tipo variante in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1a78a-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>  
 <span data-ttu-id="1a78a-118">In .NET framework 4 è stato introdotto il supporto della varianza per i parametri di tipo generico in diversi delegati generici esistenti:</span><span class="sxs-lookup"><span data-stu-id="1a78a-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>  
  
- <span data-ttu-id="1a78a-119">Delegati `Action` dallo spazio dei nomi <xref:System>, ad esempio <xref:System.Action%601> e <xref:System.Action%602></span><span class="sxs-lookup"><span data-stu-id="1a78a-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>  
  
- <span data-ttu-id="1a78a-120">Delegati `Func` dallo spazio dei nomi <xref:System>, ad esempio <xref:System.Func%601> e <xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="1a78a-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>  
  
- <span data-ttu-id="1a78a-121">Delegato <xref:System.Predicate%601>.</span><span class="sxs-lookup"><span data-stu-id="1a78a-121">The <xref:System.Predicate%601> delegate</span></span>  
  
- <span data-ttu-id="1a78a-122">Delegato <xref:System.Comparison%601>.</span><span class="sxs-lookup"><span data-stu-id="1a78a-122">The <xref:System.Comparison%601> delegate</span></span>  
  
- <span data-ttu-id="1a78a-123">Delegato <xref:System.Converter%602>.</span><span class="sxs-lookup"><span data-stu-id="1a78a-123">The <xref:System.Converter%602> delegate</span></span>  
  
 <span data-ttu-id="1a78a-124">Per altre informazioni ed esempi, vedere [Uso della varianza per i delegati generici Func e Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="1a78a-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="1a78a-125">Dichiarare parametri di tipo variante nei delegati generici</span><span class="sxs-lookup"><span data-stu-id="1a78a-125">Declaring Variant Type Parameters in Generic Delegates</span></span>  
 <span data-ttu-id="1a78a-126">Se un delegato generico ha parametri di tipo generico covariante o controvariante, può essere indicato come un *delegato generico variante*.</span><span class="sxs-lookup"><span data-stu-id="1a78a-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>  
  
 <span data-ttu-id="1a78a-127">È possibile dichiarare un parametro di tipo generico covariante in un delegato generico usando la parola chiave `out`.</span><span class="sxs-lookup"><span data-stu-id="1a78a-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="1a78a-128">Il tipo covariante può essere usato solo come tipo restituito del metodo e non come tipo di argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="1a78a-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="1a78a-129">Nell'esempio di codice seguente viene illustrato come dichiarare un delegato generico covariante.</span><span class="sxs-lookup"><span data-stu-id="1a78a-129">The following code example shows how to declare a covariant generic delegate.</span></span>  
  
```csharp  
public delegate R DCovariant<out R>();  
```  
  
 <span data-ttu-id="1a78a-130">È possibile dichiarare un parametro di tipo generico controvariante in un delegato generico usando la parola chiave `in`.</span><span class="sxs-lookup"><span data-stu-id="1a78a-130">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="1a78a-131">Il tipo controvariante può essere usato solo come tipo di argomenti del metodo e non come tipo restituito del metodo.</span><span class="sxs-lookup"><span data-stu-id="1a78a-131">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="1a78a-132">Nell'esempio di codice seguente viene illustrato come dichiarare un delegato generico controvariante.</span><span class="sxs-lookup"><span data-stu-id="1a78a-132">The following code example shows how to declare a contravariant generic delegate.</span></span>  
  
```csharp  
public delegate void DContravariant<in A>(A a);  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="1a78a-133">I parametri `ref`, `in` e `out` in C# non possono essere contrassegnati come varianti.</span><span class="sxs-lookup"><span data-stu-id="1a78a-133">`ref`, `in`, and `out` parameters in C# can't be marked as variant.</span></span>  
  
 <span data-ttu-id="1a78a-134">È anche possibile supportare sia la varianza che la covarianza nello stesso delegato, ma per parametri di tipo diverso.</span><span class="sxs-lookup"><span data-stu-id="1a78a-134">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="1a78a-135">come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1a78a-135">This is shown in the following example.</span></span>  
  
```csharp  
public delegate R DVariant<in A, out R>(A a);  
```  
  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="1a78a-136">Creare un'istanza e richiamare delegati generici varianti</span><span class="sxs-lookup"><span data-stu-id="1a78a-136">Instantiating and Invoking Variant Generic Delegates</span></span>  
 <span data-ttu-id="1a78a-137">È possibile creare un'istanza e richiamare delegati varianti con la stessa procedura con cui si crea un'istanza e si richiamano i delegati invariabili.</span><span class="sxs-lookup"><span data-stu-id="1a78a-137">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="1a78a-138">Nell'esempio seguente viene creata un'istanza del delegato da un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="1a78a-138">In the following example, the delegate is instantiated by a lambda expression.</span></span>  
  
```csharp  
DVariant<String, String> dvariant = (String str) => str + " ";  
dvariant("test");  
```  
  
### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="1a78a-139">Combinare delegati generici varianti</span><span class="sxs-lookup"><span data-stu-id="1a78a-139">Combining Variant Generic Delegates</span></span>  
 <span data-ttu-id="1a78a-140">È consigliabile non combinare i delegati varianti.</span><span class="sxs-lookup"><span data-stu-id="1a78a-140">You should not combine variant delegates.</span></span> <span data-ttu-id="1a78a-141">Il metodo <xref:System.Delegate.Combine%2A> non supporta la conversione dei delegati varianti e prevede che i delegati siano esattamente dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="1a78a-141">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="1a78a-142">Questo può causare un'eccezione in fase di esecuzione quando si combinano delegati usando il metodo <xref:System.Delegate.Combine%2A> o l'operatore `+`, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1a78a-142">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method or by using the `+` operator, as shown in the following code example.</span></span>  
  
```csharp  
Action<object> actObj = x => Console.WriteLine("object: {0}", x);  
Action<string> actStr = x => Console.WriteLine("string: {0}", x);  
// All of the following statements throw exceptions at run time.  
// Action<string> actCombine = actStr + actObj;  
// actStr += actObj;  
// Delegate.Combine(actStr, actObj);  
```  
  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="1a78a-143">Varianza nei parametri di tipo generico per tipi di valore e riferimento</span><span class="sxs-lookup"><span data-stu-id="1a78a-143">Variance in Generic Type Parameters for Value and Reference Types</span></span>  
 <span data-ttu-id="1a78a-144">La varianza per i parametri di tipo generico è supportata solo per i tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="1a78a-144">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="1a78a-145">Ad esempio, `DVariant<int>` non può essere convertito implicitamente in `DVariant<Object>` o `DVariant<long>`, poiché integer è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="1a78a-145">For example, `DVariant<int>` can't be implicitly converted to `DVariant<Object>` or `DVariant<long>`, because integer is a value type.</span></span>  
  
 <span data-ttu-id="1a78a-146">L'esempio seguente dimostra che la varianza nei parametri di tipo generico non è supportata per i tipi di valore.</span><span class="sxs-lookup"><span data-stu-id="1a78a-146">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>  
  
```csharp  
// The type T is covariant.  
public delegate T DVariant<out T>();  
  
// The type T is invariant.  
public delegate T DInvariant<T>();  
  
public static void Test()  
{  
    int i = 0;  
    DInvariant<int> dInt = () => i;  
    DVariant<int> dVariantInt = () => i;  
  
    // All of the following statements generate a compiler error  
    // because type variance in generic parameters is not supported  
    // for value types, even if generic type parameters are declared variant.  
    // DInvariant<Object> dObject = dInt;  
    // DInvariant<long> dLong = dInt;  
    // DVariant<Object> dVariantObject = dVariantInt;  
    // DVariant<long> dVariantLong = dVariantInt;              
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a78a-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a78a-147">See also</span></span>

- [<span data-ttu-id="1a78a-148">Generics</span><span class="sxs-lookup"><span data-stu-id="1a78a-148">Generics</span></span>](../../../../standard/generics/index.md)
- [<span data-ttu-id="1a78a-149">Uso della varianza per i delegati generici Func e Action (C#)</span><span class="sxs-lookup"><span data-stu-id="1a78a-149">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
- [<span data-ttu-id="1a78a-150">Come combinare delegati (delegati multicast)</span><span class="sxs-lookup"><span data-stu-id="1a78a-150">How to combine delegates (Multicast Delegates)</span></span>](../../delegates/how-to-combine-delegates-multicast-delegates.md)

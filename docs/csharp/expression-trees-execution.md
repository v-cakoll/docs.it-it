---
title: Esecuzione di alberi delle espressioni
description: Informazioni sull'esecuzione di alberi delle espressioni convertendoli in istruzioni eseguibili in linguaggio intermedio (IL, Intermediate Language).
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 109e0ac5-2a9c-48b4-ac68-9b6219cdbccf
ms.openlocfilehash: 4ca87c8410a04e9198e9dd6c379760e7b6596585
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="executing-expression-trees"></a><span data-ttu-id="4a23c-104">Esecuzione di alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="4a23c-104">Executing Expression Trees</span></span>

[<span data-ttu-id="4a23c-105">Precedente -- Tipi di framework che supportano alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="4a23c-105">Previous -- Framework Types Supporting Expression Trees</span></span>](expression-classes.md)

<span data-ttu-id="4a23c-106">Un *albero delle espressioni* è una struttura dei dati che rappresenta il codice.</span><span class="sxs-lookup"><span data-stu-id="4a23c-106">An *expression tree* is a data structure that represents some code.</span></span>
<span data-ttu-id="4a23c-107">Non è codice compilato ed eseguibile.</span><span class="sxs-lookup"><span data-stu-id="4a23c-107">It is not compiled and executable code.</span></span> <span data-ttu-id="4a23c-108">Se si vuole eseguire il codice .NET che è rappresentato da un albero delle espressioni, è necessario convertirlo in istruzioni IL eseguibili.</span><span class="sxs-lookup"><span data-stu-id="4a23c-108">If you want to execute the .NET code that is represented by an expression tree, you must convert it into executable IL instructions.</span></span> 
## <a name="lambda-expressions-to-functions"></a><span data-ttu-id="4a23c-109">Espressioni lambda per funzioni</span><span class="sxs-lookup"><span data-stu-id="4a23c-109">Lambda Expressions to Functions</span></span>
<span data-ttu-id="4a23c-110">È possibile convertire qualsiasi LambdaExpression o qualsiasi tipo derivato da LambdaExpression in IL eseguibile.</span><span class="sxs-lookup"><span data-stu-id="4a23c-110">You can convert any LambdaExpression, or any type derived from LambdaExpression into executable IL.</span></span> <span data-ttu-id="4a23c-111">Altri tipi di espressioni non possono essere convertiti direttamente in codice.</span><span class="sxs-lookup"><span data-stu-id="4a23c-111">Other expression types cannot be directly converted into code.</span></span> <span data-ttu-id="4a23c-112">Questa restrizione ha un effetto limitato nella pratica.</span><span class="sxs-lookup"><span data-stu-id="4a23c-112">This restriction has little effect in practice.</span></span> <span data-ttu-id="4a23c-113">Le espressioni lambda sono gli unici tipi di espressioni che potrebbero essere eseguite convertendole in linguaggio intermedio eseguibile (IL).</span><span class="sxs-lookup"><span data-stu-id="4a23c-113">Lambda expressions are the only types of expressions that you would want to execute by converting to executable intermediate language (IL).</span></span> <span data-ttu-id="4a23c-114">(Riflettere su cosa significherebbe eseguire direttamente una `ConstantExpression`.</span><span class="sxs-lookup"><span data-stu-id="4a23c-114">(Think about what it would mean to directly execute a `ConstantExpression`.</span></span> <span data-ttu-id="4a23c-115">Sarebbe utile?) Un albero delle espressioni che è una `LamdbaExpression` o un tipo derivato da `LambdaExpression` può essere convertito in IL.</span><span class="sxs-lookup"><span data-stu-id="4a23c-115">Would it mean anything useful?) Any expression tree that is a `LamdbaExpression`, or a type derived from `LambdaExpression` can be converted to IL.</span></span>
<span data-ttu-id="4a23c-116">Il tipo di espressione `Expression<TDelegate>` è l'unico esempio concreto nelle librerie di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a23c-116">The expression type `Expression<TDelegate>` is the only concrete example in the .NET Core libraries.</span></span> <span data-ttu-id="4a23c-117">Viene usato per rappresentare un'espressione che esegue il mapping a qualsiasi tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="4a23c-117">It's used to represent an expression that maps to any delegate type.</span></span> <span data-ttu-id="4a23c-118">Poiché questo tipo è mappato a un tipo delegato, .NET può esaminare l'espressione e generare IL per un delegato appropriato che corrisponda alla firma dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="4a23c-118">Because this type maps to a delegate type, .NET can examine the expression, and generate IL for an appropriate delegate that matches the signature of the lambda expression.</span></span> 

<span data-ttu-id="4a23c-119">Nella maggior parte dei casi, verrà creato un mapping semplice tra un'espressione e il delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="4a23c-119">In most cases, this creates a simple mapping between an expression, and its corresponding delegate.</span></span> <span data-ttu-id="4a23c-120">Ad esempio, un albero delle espressioni che è rappresentato da `Expression<Func<int>>` viene convertito in un delegato del tipo `Func<int>`.</span><span class="sxs-lookup"><span data-stu-id="4a23c-120">For example, an expression tree that is represented by `Expression<Func<int>>` would be converted to a delegate of the type `Func<int>`.</span></span> <span data-ttu-id="4a23c-121">Per un'espressione lambda con qualsiasi tipo restituito e un elenco di argomenti, esiste un tipo delegato che rappresenta il tipo di destinazione per il codice eseguibile rappresentato dall'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="4a23c-121">For a lambda expression with any return type and argument list, there exists a delegate type that is the target type for the executable code represented by that lamdba expression.</span></span>

<span data-ttu-id="4a23c-122">Il tipo `LamdbaExpression` contiene i membri `Compile` e `CompileToMethod` usati per convertire un albero delle espressioni in codice eseguibile.</span><span class="sxs-lookup"><span data-stu-id="4a23c-122">The `LamdbaExpression` type contains `Compile` and `CompileToMethod` members that you would use to convert an expression tree to executable code.</span></span> <span data-ttu-id="4a23c-123">Il metodo `Compile` crea un delegato.</span><span class="sxs-lookup"><span data-stu-id="4a23c-123">The `Compile` method creates a delegate.</span></span> <span data-ttu-id="4a23c-124">Il metodo `ConmpileToMethod` aggiorna un oggetto `MethodBuilder` con il linguaggio intermedio che rappresenta l'output compilato dell'albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a23c-124">The `ConmpileToMethod` method updates a `MethodBuilder` object with the IL that represents the compiled output of the expression tree.</span></span> <span data-ttu-id="4a23c-125">Si noti che `CompileToMethod` è disponibile solo nella versione desktop completa di Framework, non su .NET Core Framework.</span><span class="sxs-lookup"><span data-stu-id="4a23c-125">Note that `CompileToMethod` is only available on the full desktop framework, not on the .NET Core framework.</span></span>

<span data-ttu-id="4a23c-126">Facoltativamente, è anche possibile specificare un `DebugInfoGenerator` che riceverà le informazioni di debug del simbolo per l'oggetto delegato generato.</span><span class="sxs-lookup"><span data-stu-id="4a23c-126">Optionally, you can also provide a `DebugInfoGenerator` that will receive the symbol debugging information for the generated delegate object.</span></span> <span data-ttu-id="4a23c-127">Ciò consente di convertire l'albero delle espressioni in un oggetto delegato e di avere informazioni di debug complete sul delegato generato.</span><span class="sxs-lookup"><span data-stu-id="4a23c-127">This enables you to convert the expression tree into a delegate object, and have full debugging information about the generated delegate.</span></span>

<span data-ttu-id="4a23c-128">È necessario convertire un'espressione in un delegato tramite il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4a23c-128">You would convert an expression into a delegate using the following code:</span></span>

```csharp
Expression<Func<int>> add = () => 1 + 2;
var func = add.Compile(); // Create Delegate
var answer = func(); // Invoke Delegate
Console.WriteLine(answer);
```

<span data-ttu-id="4a23c-129">Si noti che il tipo delegato è basato sul tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="4a23c-129">Notice that the delegate type is based on the expression type.</span></span> <span data-ttu-id="4a23c-130">Se si vuole usare l'oggetto delegato in modo fortemente tipizzato, è necessario conoscere il tipo restituito e l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="4a23c-130">You must know the return type and the argument list if you want to use the delegate object in a strongly typed manner.</span></span> <span data-ttu-id="4a23c-131">Il metodo `LambdaExpression.Compile()` restituisce il tipo `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="4a23c-131">The `LambdaExpression.Compile()` method returns the `Delegate` type.</span></span> <span data-ttu-id="4a23c-132">È necessario eseguirne il cast al tipo di delegato corretto affinché gli strumenti in fase di compilazione controllino l'elenco di argomenti del tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="4a23c-132">You will have to cast it to the correct delegate type to have any compile-time tools check the argument list of return type.</span></span>

## <a name="execution-and-lifetimes"></a><span data-ttu-id="4a23c-133">Esecuzione e durate</span><span class="sxs-lookup"><span data-stu-id="4a23c-133">Execution and Lifetimes</span></span>

<span data-ttu-id="4a23c-134">Si esegue il codice richiamando il delegato creato durante la chiamata a `LamdbaExpression.Compile()`.</span><span class="sxs-lookup"><span data-stu-id="4a23c-134">You execute the code by invoking the delegate created when you called `LamdbaExpression.Compile()`.</span></span> <span data-ttu-id="4a23c-135">È possibile vederlo qui sopra dove `add.Compile()` restituisce un delegato.</span><span class="sxs-lookup"><span data-stu-id="4a23c-135">You can see this above where `add.Compile()` returns a delegate.</span></span> <span data-ttu-id="4a23c-136">Richiamando il delegato, la chiamata a `func()` esegue il codice.</span><span class="sxs-lookup"><span data-stu-id="4a23c-136">Invoking that delegate, by calling `func()` executes the code.</span></span>

<span data-ttu-id="4a23c-137">Il delegato rappresenta il codice nell'albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a23c-137">That delegate represents the code in the expression tree.</span></span> <span data-ttu-id="4a23c-138">È possibile mantenere il punto di controllo al delegato e richiamarlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="4a23c-138">You can retain the handle to that delegate and invoke it later.</span></span> <span data-ttu-id="4a23c-139">Non è necessario compilare l'albero delle espressioni ogni volta che si vuole eseguire il codice che rappresenta.</span><span class="sxs-lookup"><span data-stu-id="4a23c-139">You don't need to compile the expression tree each time you want to execute the code it represents.</span></span> <span data-ttu-id="4a23c-140">Tenere presente che gli alberi delle espressioni non sono modificabili e la compilazione dello stesso albero delle espressioni in un secondo momento creerà un delegato che esegue lo stesso codice.</span><span class="sxs-lookup"><span data-stu-id="4a23c-140">(Remember that expression trees are immutable, and compiling the same expression tree later will create a delegate that executes the same code.)</span></span>

<span data-ttu-id="4a23c-141">È consigliabile prestare la massima attenzione quando si tenta di creare un meccanismo di memorizzazione nella cache più sofisticato per migliorare le prestazioni evitando chiamate di compilazione non necessarie.</span><span class="sxs-lookup"><span data-stu-id="4a23c-141">I will caution you against trying to create any more sophisticated caching mechanisms to increase performance by avoiding unnecessary compile calls.</span></span> <span data-ttu-id="4a23c-142">Il confronto tra due alberi delle espressioni arbitrari per determinare se rappresentino lo stesso algoritmo richiederà anche molto tempo.</span><span class="sxs-lookup"><span data-stu-id="4a23c-142">Comparing two arbitrary expression trees to determine if they represent the same algorithm will also be time consuming to execute.</span></span> <span data-ttu-id="4a23c-143">Probabilmente si scoprirà che il tempo di calcolo risparmiato evitando le chiamate aggiuntive a `LambdaExpression.Compile()` verrà abbondantemente consumato dal tempo per l'esecuzione del codice che determina due risultati diversi degli alberi delle espressioni nello stesso codice eseguibile.</span><span class="sxs-lookup"><span data-stu-id="4a23c-143">You'll likely find that the compute time you save avoiding any extra calls to `LambdaExpression.Compile()` will be more than consumed by the time executing code that determines of two different expression trees result in the same executable code.</span></span>

## <a name="caveats"></a><span data-ttu-id="4a23c-144">Avvertenze</span><span class="sxs-lookup"><span data-stu-id="4a23c-144">Caveats</span></span>

<span data-ttu-id="4a23c-145">La compilazione di un'espressione lambda a un delegato e la chiamata al delegato è una delle operazioni più semplici che si possono eseguire con un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a23c-145">Compiling a lambda expression to a delegate and invoking that delegate is one of the simplest operations you can perform with an expression tree.</span></span> <span data-ttu-id="4a23c-146">Anche con questa semplice operazione vi sono tuttavia alcune avvertenze da tenere in considerazione.</span><span class="sxs-lookup"><span data-stu-id="4a23c-146">However, even with this simple operation, there are caveats you must be aware of.</span></span> 

<span data-ttu-id="4a23c-147">Le espressioni lambda creano chiusure su tutte le variabili locali a cui si fa riferimento nell'espressione.</span><span class="sxs-lookup"><span data-stu-id="4a23c-147">Lambda Expressions create closures over any local variables that are referenced in the expression.</span></span> <span data-ttu-id="4a23c-148">È necessario garantire che tutte le variabili che fanno parte del delegato siano utilizzabili in corrispondenza della posizione in cui viene chiamato `Compile` e quando si esegue il delegato risultante.</span><span class="sxs-lookup"><span data-stu-id="4a23c-148">You must guarantee that any variables that would be part of the delegate are usable at the location where you call `Compile`, and when you execute the resulting delegate.</span></span>

<span data-ttu-id="4a23c-149">In generale, il compilatore garantirà che questa condizione sia vera.</span><span class="sxs-lookup"><span data-stu-id="4a23c-149">In general, the compiler will ensure that this is true.</span></span> <span data-ttu-id="4a23c-150">Se tuttavia l'espressione accede a una variabile che implementa `IDisposable`, è possibile che il codice elimini l'oggetto mentre è ancora mantenuto attivo dall'albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a23c-150">However, if your expression accesses a variable that implements `IDisposable`, it's possible that your code might dispose of the object while it is still held by the expression tree.</span></span>

<span data-ttu-id="4a23c-151">Ad esempio, questo codice funziona correttamente poiché `int` non implementa `IDisposable`:</span><span class="sxs-lookup"><span data-stu-id="4a23c-151">For example, this code works fine, because `int` does not implement `IDisposable`:</span></span>

```csharp
private static Func<int, int> CreateBoundFunc()
{
    var constant = 5; // constant is captured by the expression tree
    Expression<Func<int, int>> expression = (b) => constant + b;
    var rVal = expression.Compile();
    return rVal;
}
```

<span data-ttu-id="4a23c-152">Il delegato ha acquisito un riferimento alla variabile locale `constant`.</span><span class="sxs-lookup"><span data-stu-id="4a23c-152">The delegate has captured a reference to the local variable `constant`.</span></span>
<span data-ttu-id="4a23c-153">Tale variabile è accessibile in qualsiasi momento successivo, quando viene eseguita la funzione restituita da `CreateBoundFunc`.</span><span class="sxs-lookup"><span data-stu-id="4a23c-153">That variable is accessed at any time later, when the function returned by `CreateBoundFunc` executes.</span></span>

<span data-ttu-id="4a23c-154">Tenere presente tuttavia questa classe (piuttosto improbabile) che implementa `IDisposable`:</span><span class="sxs-lookup"><span data-stu-id="4a23c-154">However, consider this (rather contrived) class that implements `IDisposable`:</span></span>

```csharp
public class Resource : IDisposable
{
    private bool isDisposed = false;
    public int Argument
    {
        get
        {
            if (!isDisposed)
                return 5;
            else throw new ObjectDisposedException("Resource");
        }
    }

    public void Dispose()
    {
        isDisposed = true;
    }
}
```

<span data-ttu-id="4a23c-155">Se usata in un'espressione come illustrato di seguito, si otterrà un `ObjectDisposedException` quando si esegue il codice a cui fa riferimento la proprietà `Resource.Argument`:</span><span class="sxs-lookup"><span data-stu-id="4a23c-155">If you use it in an expression as shown below, you'll get an `ObjectDisposedException` when you execute the code referenced by the `Resource.Argument` property:</span></span>

```csharp
private static Func<int, int> CreateBoundResource()
{
    using (var constant = new Resource()) // constant is captured by the expression tree
    {
        Expression<Func<int, int>> expression = (b) => constant.Argument + b;
        var rVal = expression.Compile();
        return rVal;
    }
}
```

<span data-ttu-id="4a23c-156">Il delegato restituito da questo metodo è stato chiuso sull'oggetto `constant`, che è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="4a23c-156">The delegate returned from this method has closed over the `constant` object, which has been disposed of.</span></span> <span data-ttu-id="4a23c-157">(È stato eliminato, perché è stato dichiarato in un'istruzione `using`.)</span><span class="sxs-lookup"><span data-stu-id="4a23c-157">(It's been disposed, because it was declared in a `using` statement.)</span></span> 

<span data-ttu-id="4a23c-158">A questo punto, quando si esegue il delegato restituito da questo metodo, si avrà una `ObjecctDisposedException` generata al momento dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a23c-158">Now, when you execute the delegate returned from this method, you'll have a `ObjecctDisposedException` thrown at the point of execution.</span></span>

<span data-ttu-id="4a23c-159">Può sembrare strano ricevere un errore di runtime che rappresenta un costrutto in fase di compilazione, ma questo è ciò che avviene negli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a23c-159">It does seem strange to have a runtime error representing a compile-time construct, but that's the world we enter when we work with expression trees.</span></span>

<span data-ttu-id="4a23c-160">Esistono molte variazioni di questo problema, pertanto è difficile offrire indicazioni generali per evitarlo.</span><span class="sxs-lookup"><span data-stu-id="4a23c-160">There are a lot of permutations of this problem, so it's hard to offer general guidance to avoid it.</span></span> <span data-ttu-id="4a23c-161">Prestare attenzione all'accesso alle variabili locali quando si definiscono le espressioni e prestare attenzione all'accesso allo stato nell'oggetto corrente (rappresentato da `this`) quando viene creato un albero delle espressioni che può essere restituito da un'API pubblica.</span><span class="sxs-lookup"><span data-stu-id="4a23c-161">Be careful about accessing local variables when defining expressions, and be careful about accessing state in the current object (represented by `this`) when creating an expression tree that can be returned by a public API.</span></span>

<span data-ttu-id="4a23c-162">Il codice nell'espressione può fare riferimento a metodi o proprietà in altri assembly.</span><span class="sxs-lookup"><span data-stu-id="4a23c-162">The code in your expression may reference methods or properties in other assemblies.</span></span> <span data-ttu-id="4a23c-163">Tale assembly deve essere accessibile quando viene definita l'espressione, quando viene compilata e quando viene richiamato il delegato risultante.</span><span class="sxs-lookup"><span data-stu-id="4a23c-163">That assembly must be accessible when the expression is defined, and when it is compiled, and when the resulting delegate is invoked.</span></span> <span data-ttu-id="4a23c-164">Quando non è presente, si incontrerà una `ReferencedAssemblyNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="4a23c-164">You'll be met with a `ReferencedAssemblyNotFoundException` in cases where it is not present.</span></span>

## <a name="summary"></a><span data-ttu-id="4a23c-165">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4a23c-165">Summary</span></span>

<span data-ttu-id="4a23c-166">Gli alberi delle espressioni che rappresentano le espressioni lambda possono essere compilati per creare un delegato che è possibile eseguire.</span><span class="sxs-lookup"><span data-stu-id="4a23c-166">Expression Trees that represent lambda expressions can be compiled to create a delegate that you can execute.</span></span> <span data-ttu-id="4a23c-167">Questo offre un meccanismo per eseguire il codice rappresentato da un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a23c-167">This provides one mechanism to execute the code represented by an expression tree.</span></span>

<span data-ttu-id="4a23c-168">L'albero delle espressioni non rappresenta il codice da eseguire per qualsiasi costrutto specifico creato.</span><span class="sxs-lookup"><span data-stu-id="4a23c-168">The Expression Tree does represent the code that would execute for any given construct you create.</span></span> <span data-ttu-id="4a23c-169">Finché l'ambiente in cui viene compilato ed eseguito il codice corrisponderà all'ambiente in cui si crea l'espressione, tutto funzionerà come previsto.</span><span class="sxs-lookup"><span data-stu-id="4a23c-169">As long as the environment where you compile and execute the code matches the environment where you create the expression, everything works as expected.</span></span> <span data-ttu-id="4a23c-170">In caso contrario, gli errori sono molto prevedibili e verranno intercettati nei primi test di qualsiasi codice basato sugli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a23c-170">When that doesn't happen, the errors are very predictable, and they will be caught in your first tests of any code using the expression trees.</span></span>

[<span data-ttu-id="4a23c-171">Successivo --Interpretazione di espressioni</span><span class="sxs-lookup"><span data-stu-id="4a23c-171">Next -- Interpreting Expressions</span></span>](expression-trees-interpreting.md)

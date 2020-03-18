---
title: Compilazione di alberi delle espressioni
description: Informazioni sulle tecniche per la creazione di alberi delle espressioni.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 542754a9-7f40-4293-b299-b9f80241902c
ms.openlocfilehash: c93eb16ebf2ff66dc0162afb6841f2cadfce174e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146047"
---
# <a name="building-expression-trees"></a><span data-ttu-id="4a4d5-103">Compilazione di alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="4a4d5-103">Building Expression Trees</span></span>

[<span data-ttu-id="4a4d5-104">Precedente -- Interpretazione di espressioni</span><span class="sxs-lookup"><span data-stu-id="4a4d5-104">Previous -- Interpreting Expressions</span></span>](expression-trees-interpreting.md)

<span data-ttu-id="4a4d5-105">Tutti gli alberi delle espressioni visti finora sono stati creati dal compilatore C#.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-105">All the expression trees you've seen so far have been created by the C# compiler.</span></span> <span data-ttu-id="4a4d5-106">È stato sufficiente creare un'espressione lambda assegnata a una variabile tipizzata come un'espressione `Expression<Func<T>>` o di tipo simile.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-106">All you had to do was create a lambda expression that was assigned to a variable typed as an `Expression<Func<T>>` or some similar type.</span></span> <span data-ttu-id="4a4d5-107">Questo tuttavia non è l'unico modo per creare un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-107">That's not the only way to create an expression tree.</span></span> <span data-ttu-id="4a4d5-108">In molti scenari potrebbe essere necessario compilare un'espressione in memoria in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-108">For many scenarios you may find that you need to build an expression in memory at runtime.</span></span>

<span data-ttu-id="4a4d5-109">La compilazione di alberi delle espressioni è complicata dal fatto che gli alberi delle espressioni non sono modificabili.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-109">Building Expression Trees is complicated by the fact that those expression trees are immutable.</span></span> <span data-ttu-id="4a4d5-110">Ciò significa che l'albero deve essere compilato dalle foglie alla radice.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-110">Being immutable means that you must build the tree from the leaves up to the root.</span></span> <span data-ttu-id="4a4d5-111">Ciò si riflette nelle API usate per compilare gli alberi delle espressioni: i metodi usati per compilare un nodo accettano tutti gli elementi figlio come argomenti.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-111">The APIs you'll use to build expression trees reflect this fact: The methods you'll use to build a node take all its children as arguments.</span></span> <span data-ttu-id="4a4d5-112">I seguenti esempi illustrano le tecniche.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-112">Let's walk through a few examples to show you the techniques.</span></span>

## <a name="creating-nodes"></a><span data-ttu-id="4a4d5-113">Creazione di nodi</span><span class="sxs-lookup"><span data-stu-id="4a4d5-113">Creating Nodes</span></span>

<span data-ttu-id="4a4d5-114">Iniziamo con un esempio relativamente semplicemente,</span><span class="sxs-lookup"><span data-stu-id="4a4d5-114">Let's start relatively simply again.</span></span> <span data-ttu-id="4a4d5-115">usando l'espressione di addizione già impiegata nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-115">We'll use the addition expression I've been working with throughout these sections:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

<span data-ttu-id="4a4d5-116">Per costruire l'albero delle espressioni, è necessario creare i nodi foglia.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-116">To construct that expression tree, you must construct the leaf nodes.</span></span>
<span data-ttu-id="4a4d5-117">I nodi foglia sono costanti, e per costruirli è pertanto possibile usare il metodo `Expression.Constant`:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-117">The leaf nodes are constants, so you can use the `Expression.Constant` method to create the nodes:</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
```

<span data-ttu-id="4a4d5-118">Successivamente, viene creata creato l'espressione di addizione:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-118">Next, you'll build the addition expression:</span></span>

```csharp
var addition = Expression.Add(one, two);
```

<span data-ttu-id="4a4d5-119">Dopo aver creato l'espressione di addizione, è possibile creare l'espressione lambda:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-119">Once you've got the addition expression, you can create the lambda expression:</span></span>

```csharp
var lambda = Expression.Lambda(addition);
```

<span data-ttu-id="4a4d5-120">Si tratta di un'espressione lambda molto semplice, perché non contiene argomenti.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-120">This is a very simple lambda expression, because it contains no arguments.</span></span>
<span data-ttu-id="4a4d5-121">Più avanti in questa sezione verrà illustrato come eseguire il mapping degli argomenti ai parametri e compilare espressioni più complesse.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-121">Later in this section, you'll see how to map arguments to parameters and build more complicated expressions.</span></span>

<span data-ttu-id="4a4d5-122">Per le espressioni semplici come questa, è possibile combinare tutte le chiamate in un'unica istruzione:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-122">For expressions that are as simple as this one, you may combine all the calls into a single statement:</span></span>

```csharp
var lambda = Expression.Lambda(
    Expression.Add(
        Expression.Constant(1, typeof(int)),
        Expression.Constant(2, typeof(int))
    )
);
```

## <a name="building-a-tree"></a><span data-ttu-id="4a4d5-123">Compilazione di una struttura ad albero</span><span class="sxs-lookup"><span data-stu-id="4a4d5-123">Building a Tree</span></span>

<span data-ttu-id="4a4d5-124">Vengono illustrate le nozioni di base per la compilazione di un albero delle espressioni in memoria.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-124">That's the basics of building an expression tree in memory.</span></span> <span data-ttu-id="4a4d5-125">Strutture ad albero più complesse implicano in genere più tipi di nodo e più nodi dell'albero.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-125">More complex trees generally mean more node types, and more nodes in the tree.</span></span> <span data-ttu-id="4a4d5-126">L'esempio seguente mostra due tipi di nodo che vengono in genere compilati quando si creano alberi delle espressioni: i nodi argomento e i nodi di chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-126">Let's run through one more example and show two more node types that you will typically build when you create expression trees: the argument nodes, and method call nodes.</span></span>

<span data-ttu-id="4a4d5-127">Di seguito viene compilato un albero delle espressioni per creare questa espressione:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-127">Let's build an expression tree to create this expression:</span></span>

```csharp
Expression<Func<double, double, double>> distanceCalc =
    (x, y) => Math.Sqrt(x * x + y * y);
```

<span data-ttu-id="4a4d5-128">Si inizia creando espressioni per i parametri per `x` e `y`:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-128">You'll start by creating parameter expressions for `x` and `y`:</span></span>

```csharp
var xParameter = Expression.Parameter(typeof(double), "x");
var yParameter = Expression.Parameter(typeof(double), "y");
```

<span data-ttu-id="4a4d5-129">Per creare le espressioni di addizione e moltiplicazione seguire il modello illustrato in precedenza:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-129">Creating the multiplication and addition expressions follows the pattern you've already seen:</span></span>

```csharp
var xSquared = Expression.Multiply(xParameter, xParameter);
var ySquared = Expression.Multiply(yParameter, yParameter);
var sum = Expression.Add(xSquared, ySquared);
```

<span data-ttu-id="4a4d5-130">Quindi è necessario creare un'espressione di chiamata al metodo per la chiamata a `Math.Sqrt`.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-130">Next, you need to create a method call expression for the call to `Math.Sqrt`.</span></span>

```csharp
var sqrtMethod = typeof(Math).GetMethod("Sqrt", new[] { typeof(double) });
var distance = Expression.Call(sqrtMethod, sum);
```

<span data-ttu-id="4a4d5-131">Infine, inserire la chiamata al metodo in un'espressione lambda e verificare che gli argomenti nell'espressione lambda siano stati definiti:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-131">And  then finally, you put the method call into a lambda expression, and make sure to define the arguments to the lambda expression:</span></span>

```csharp
var distanceLambda = Expression.Lambda(
    distance,
    xParameter,
    yParameter);
```

<span data-ttu-id="4a4d5-132">In questo esempio più complesso, vengono illustrate altre due tecniche spesso necessarie per creare alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-132">In this more complicated example, you see a couple more techniques that you will often need to create expression trees.</span></span>

<span data-ttu-id="4a4d5-133">Innanzitutto è necessario creare gli oggetti che rappresentano i parametri o le variabili locali prima di usarli.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-133">First, you need to create the objects that represent parameters or local variables before you use them.</span></span> <span data-ttu-id="4a4d5-134">Dopo aver creato questi oggetti, è possibile inserirli nell'albero delle espressioni secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-134">Once you've created those objects, you can use them in your expression tree wherever you need.</span></span>

<span data-ttu-id="4a4d5-135">È quindi necessario usare un sottoinsieme dell'API Reflection per creare un oggetto `MethodInfo`, così da poter creare un albero delle espressioni per accedere a tale metodo.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-135">Second, you need to use a subset of the Reflection APIs to create a `MethodInfo` object so that you can create an expression tree to access that method.</span></span> <span data-ttu-id="4a4d5-136">È necessario limitarsi al sottoinsieme delle API Reflection disponibili nella piattaforma .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-136">You must limit yourself to the subset of the Reflection APIs that are available on the .NET Core platform.</span></span> <span data-ttu-id="4a4d5-137">Anche queste tecniche possono essere estese ad altri alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-137">Again, these techniques will extend to other expression trees.</span></span>

## <a name="building-code-in-depth"></a><span data-ttu-id="4a4d5-138">Compilazione di codice complesso</span><span class="sxs-lookup"><span data-stu-id="4a4d5-138">Building Code In Depth</span></span>

<span data-ttu-id="4a4d5-139">Non ci sono limiti alle possibilità di creare usando queste API.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-139">You aren't limited in what you can build using these APIs.</span></span> <span data-ttu-id="4a4d5-140">Tuttavia, più complicato è l'albero delle espressioni che si vuole compilare, più difficile sarà da gestire e leggere il codice.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-140">However, the more complicated expression tree that you want to build, the more difficult the code is to manage and to read.</span></span>

<span data-ttu-id="4a4d5-141">Viene ora creato un albero delle espressioni che è l'equivalente di questo codice:</span><span class="sxs-lookup"><span data-stu-id="4a4d5-141">Let's build an expression tree that is the equivalent of this code:</span></span>

```csharp
Func<int, int> factorialFunc = (n) =>
{
    var res = 1;
    while (n > 1)
    {
        res = res * n;
        n--;
    }
    return res;
};
```

<span data-ttu-id="4a4d5-142">Si noti che non è stato compilato l'albero delle espressioni, ma il delegato.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-142">Notice above that I did not build the expression tree, but simply the delegate.</span></span> <span data-ttu-id="4a4d5-143">Usando la classe `Expression` non è possibile compilare espressioni lambda dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-143">Using the `Expression` class, you can't build statement lambdas.</span></span> <span data-ttu-id="4a4d5-144">Ecco il codice necessario per compilare la stessa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-144">Here's the code that is required to build the same functionality.</span></span> <span data-ttu-id="4a4d5-145">È complicato dal fatto che non esiste un'API per compilare un ciclo `while`, ed è invece necessario creare un ciclo contenente un test condizionale e una destinazione dell'etichetta per uscire dal ciclo.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-145">It's complicated by the fact that there isn't an API to build a `while` loop, instead you need to build a loop that contains a conditional test, and a label target to break out of the loop.</span></span>

```csharp
var nArgument = Expression.Parameter(typeof(int), "n");
var result = Expression.Variable(typeof(int), "result");

// Creating a label that represents the return value
LabelTarget label = Expression.Label(typeof(int));

var initializeResult = Expression.Assign(result, Expression.Constant(1));

// This is the inner block that performs the multiplication,
// and decrements the value of 'n'
var block = Expression.Block(
    Expression.Assign(result,
        Expression.Multiply(result, nArgument)),
    Expression.PostDecrementAssign(nArgument)
);

// Creating a method body.
BlockExpression body = Expression.Block(
    new[] { result },
    initializeResult,
    Expression.Loop(
        Expression.IfThenElse(
            Expression.GreaterThan(nArgument, Expression.Constant(1)),
            block,
            Expression.Break(label, result)
        ),
        label
    )
);
```

<span data-ttu-id="4a4d5-146">Il codice per creare l'albero delle espressioni per la funzione fattoriale è più lungo, più complesso, e include numerose etichette e istruzioni di interruzione che è preferibile evitare nelle quotidiane attività di codifica.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-146">The code to build the expression tree for the factorial function is quite a bit longer, more complicated, and it's riddled with labels and break statements and other elements we'd like to avoid in our everyday coding tasks.</span></span>

<span data-ttu-id="4a4d5-147">Per questa sezione è stato anche aggiornato il codice visitatore, per visitare ogni nodo in questo albero delle espressioni e scrivere le informazioni relative ai nodi creati in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-147">For this section, I've also updated the visitor code to visit every node in this expression tree and write out information about the nodes that are created in this sample.</span></span> <span data-ttu-id="4a4d5-148">È possibile [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/csharp/expression-trees) dal repository GitHub dotnet/docs.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-148">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/csharp/expression-trees) at the dotnet/docs GitHub repository.</span></span> <span data-ttu-id="4a4d5-149">Provare a compilare ed eseguire da soli gli esempi.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-149">Experiment for yourself by building and running the samples.</span></span> <span data-ttu-id="4a4d5-150">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="4a4d5-150">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="examining-the-apis"></a><span data-ttu-id="4a4d5-151">Analisi delle API</span><span class="sxs-lookup"><span data-stu-id="4a4d5-151">Examining the APIs</span></span>

<span data-ttu-id="4a4d5-152">Le API dell'albero delle espressioni sono tra le più difficili da esplorare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-152">The expression tree APIs are some of the more difficult to navigate in .NET Core, but that's fine.</span></span> <span data-ttu-id="4a4d5-153">La loro finalità è piuttosto complessa: consentono di scrivere codice che genera codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-153">Their purpose is a rather complex undertaking: writing code that generates code at runtime.</span></span> <span data-ttu-id="4a4d5-154">Sono intrinsecamente complicate perché devono offrire un equilibrio tra la capacità di supportare tutte le strutture di controllo disponibili nel linguaggio C# e mantenere l'area di superficie delle API di dimensioni ridotte.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-154">They are necessarily complicated to provide a balance between supporting all the control structures available in the C# language and keeping the surface area of the APIs as small as reasonable.</span></span> <span data-ttu-id="4a4d5-155">Questo equilibrio fa sì che molte strutture di controllo siano rappresentate non dai propri costrutti in C#, ma da costrutti che rappresentano la logica sottostante generata dal compilatore a partire da quei costrutti di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-155">This balance means that many control structures are represented not by their C# constructs, but by constructs that represent the underlying logic that the compiler generates from these higher level constructs.</span></span>

<span data-ttu-id="4a4d5-156">Inoltre, attualmente sono disponibili espressioni in C# che non possono essere compilate direttamente usando metodi della classe `Expression`.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-156">Also, at this time, there are C# expressions that cannot be built directly using `Expression` class methods.</span></span> <span data-ttu-id="4a4d5-157">In generale, questi saranno gli operati e le espressioni più recenti aggiunte in C# 5 e C# 6.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-157">In general, these will be the newest operators and expressions added in C# 5 and C# 6.</span></span> <span data-ttu-id="4a4d5-158">Ad esempio, non è possibile compilare espressioni `async` e non è possibile creare direttamente il nuovo operatore `?.`.</span><span class="sxs-lookup"><span data-stu-id="4a4d5-158">(For example, `async` expressions cannot be built, and the new `?.` operator cannot be directly created.)</span></span>

[<span data-ttu-id="4a4d5-159">Successivo -- Conversione di espressioni</span><span class="sxs-lookup"><span data-stu-id="4a4d5-159">Next -- Translating Expressions</span></span>](expression-trees-translating.md)

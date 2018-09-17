---
title: Tipi di framework che supportano alberi delle espressioni
description: Informazioni sui tipi di framework che supportano gli alberi delle espressioni, sulla creazione di alberi delle espressioni e sulle tecniche per l'uso delle API degli alberi delle espressioni.
ms.date: 06/20/2016
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.openlocfilehash: 687b521c52c1ca380a12e18469b5f66000049d3c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45617967"
---
# <a name="framework-types-supporting-expression-trees"></a><span data-ttu-id="0f2f4-103">Tipi di framework che supportano alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="0f2f4-103">Framework Types Supporting Expression Trees</span></span>

[<span data-ttu-id="0f2f4-104">Precedente -- Expression Trees Explained (Nozioni di base sugli alberi delle espressioni)</span><span class="sxs-lookup"><span data-stu-id="0f2f4-104">Previous -- Expression Trees Explained</span></span>](expression-trees-explained.md)

<span data-ttu-id="0f2f4-105">In .NET Core Framework esiste un lungo elenco di classi che funzionano con gli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-105">There is a large list of classes in the .NET Core framework that work with Expression Trees.</span></span>
<span data-ttu-id="0f2f4-106">È possibile visualizzare l'elenco completo in <xref:System.Linq.Expressions>.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-106">You can see the full list at <xref:System.Linq.Expressions>.</span></span>
<span data-ttu-id="0f2f4-107">Anziché rivedere l'elenco completo, cerchiamo di comprendere come sono state progettate le classi del framework.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-107">Rather than run through the full list, let's understand how the framework classes have been designed.</span></span>

<span data-ttu-id="0f2f4-108">Nella progettazione del linguaggio, un'espressione è un corpo di codice che valuta e restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-108">In language design, an expression is a body of code that evaluates and returns a value.</span></span> <span data-ttu-id="0f2f4-109">Le espressioni possono essere molto semplici: l'espressione costante `1` restituisce il valore costante 1.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-109">Expressions may be very simple: the constant expression `1` returns the constant value of 1.</span></span> <span data-ttu-id="0f2f4-110">Possono essere più complicate: l'espressione `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` restituisce una radice di un'equazione quadratica (nel caso in cui l'equazione abbia una soluzione).</span><span class="sxs-lookup"><span data-stu-id="0f2f4-110">They may be more complicated: The expression `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` returns one root for a quadratic equation (in the case where the equation has a solution).</span></span>  

## <a name="it-all-starts-with-systemlinqexpression"></a><span data-ttu-id="0f2f4-111">Tutto inizia con System.Linq.Expression</span><span class="sxs-lookup"><span data-stu-id="0f2f4-111">It all starts with System.Linq.Expression</span></span>

<span data-ttu-id="0f2f4-112">Una delle difficoltà legate all'uso degli alberi delle espressioni è che molti tipi diversi di espressioni sono validi in molte posizioni nei programmi.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-112">One of the complexities of working with expression trees is that many different kinds of expressions are valid in many places in programs.</span></span> <span data-ttu-id="0f2f4-113">Si consideri un'espressione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-113">Consider an assignment expression.</span></span> <span data-ttu-id="0f2f4-114">Il lato destro di un'assegnazione può essere un valore costante, una variabile, un'espressione per chiamata al metodo o altro.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-114">The right hand side of an assignment could be a constant value, a variable, a method call expression, or others.</span></span> <span data-ttu-id="0f2f4-115">Tale flessibilità del linguaggio significa che possono insorgere molti tipi di espressioni diverse in qualsiasi punto nei nodi di un albero quando si attraversa un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-115">That language flexibility means that you may encounter many different expression types anywhere in the nodes of a tree when you traverse an expression tree.</span></span> <span data-ttu-id="0f2f4-116">Pertanto, quando è possibile usare il tipo di espressione di base questo è il modo più semplice per lavorare.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-116">Therefore, when you can work with the base expression type, that's the simplest way to work.</span></span> <span data-ttu-id="0f2f4-117">È talvolta necessario, tuttavia, ottenere maggiori informazioni.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-117">However, sometimes you need to know more.</span></span>
<span data-ttu-id="0f2f4-118">La classe Expression di base contiene una proprietà `NodeType` per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-118">The base Expression class contains a `NodeType` property for this purpose.</span></span>
<span data-ttu-id="0f2f4-119">Restituisce un `ExpressionType` che costituisce un'enumerazione dei tipi di espressioni possibili.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-119">It returns an `ExpressionType` which is an enumeration of possible expression types.</span></span>
<span data-ttu-id="0f2f4-120">Quando si conosce il tipo di nodo, è possibile eseguirne il cast al tipo ed eseguire azioni specifiche conoscendo il tipo del nodo dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-120">Once you know the type of the node, you can cast it to that type, and perform specific actions knowing the type of the expression node.</span></span> <span data-ttu-id="0f2f4-121">È possibile eseguire la ricerca di determinati tipi di nodo e quindi usare le proprietà specifiche di quel tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-121">You can search for certain node types, and then work with the specific properties of that kind of expression.</span></span>

<span data-ttu-id="0f2f4-122">Ad esempio, questo codice stamperà il nome di una variabile per un'espressione di accesso alle variabili.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-122">For example, this code will print the name of a variable for a variable access expression.</span></span> <span data-ttu-id="0f2f4-123">È stata seguita la procedura di verifica del tipo di nodo, quindi è stato eseguito il cast a un'espressione di accesso alle variabili e infine sono state verificate le proprietà del tipo di espressione specifica:</span><span class="sxs-lookup"><span data-stu-id="0f2f4-123">I've followed the practice of checking the node type, then casting to a variable access expression and then checking the properties of the specific expression type:</span></span>

```csharp
Expression<Func<int, int>> addFive = (num) => num + 5;

if (addFive.NodeType == ExpressionType.Lambda)
{
    var lambdaExp = (LambdaExpression)addFive;

    var parameter = lambdaExp.Parameters.First();

    Console.WriteLine(parameter.Name);
    Console.WriteLine(parameter.Type);
}
```

## <a name="creating-expression-trees"></a><span data-ttu-id="0f2f4-124">Creazione dell'albero delle espressioni</span><span class="sxs-lookup"><span data-stu-id="0f2f4-124">Creating Expression Trees</span></span>

<span data-ttu-id="0f2f4-125">La classe `System.Linq.Expression` contiene anche molti metodi statici per creare espressioni.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-125">The `System.Linq.Expression` class also contains many static methods to create expressions.</span></span> <span data-ttu-id="0f2f4-126">Questi metodi creano un nodo di espressione usando gli argomenti specificati per i relativi elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-126">These methods create an expression node using the arguments supplied for its children.</span></span> <span data-ttu-id="0f2f4-127">In questo modo, si compila un'espressione dai relativi nodi foglia.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-127">In this way, you build an expression up from its leaf nodes.</span></span> <span data-ttu-id="0f2f4-128">Ad esempio, questo codice compila un'espressione di aggiunta:</span><span class="sxs-lookup"><span data-stu-id="0f2f4-128">For example, this code builds an Add expression:</span></span>

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

<span data-ttu-id="0f2f4-129">In questo semplice esempio si vede che nella creazione e nell'uso degli alberi delle espressioni sono coinvolti molti tipi.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-129">You can see from this simple example that many types are involved in creating and working with expression trees.</span></span> <span data-ttu-id="0f2f4-130">Tale complessità è necessaria per offrire le funzionalità di vocabolario avanzate del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-130">That complexity is necessary to provide the capabilities of the rich vocabulary provided by the C# language.</span></span>

## <a name="navigating-the-apis"></a><span data-ttu-id="0f2f4-131">Esplorazione delle API</span><span class="sxs-lookup"><span data-stu-id="0f2f4-131">Navigating the APIs</span></span>
<span data-ttu-id="0f2f4-132">Sono disponibili tipi di nodo Expression che eseguono il mapping a quasi tutti gli elementi della sintassi del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-132">There are Expression node types that map to almost all of the syntax elements of the C# language.</span></span> <span data-ttu-id="0f2f4-133">Ogni tipo offre metodi specifici per il tipo di elemento di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-133">Each type has specific methods for that type of language element.</span></span> <span data-ttu-id="0f2f4-134">Vi sono molti elementi da tenere presenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-134">It's a lot to keep in your head at one time.</span></span> <span data-ttu-id="0f2f4-135">Anziché tentare di memorizzare tutti gli elementi, ecco le tecniche consigliate per lavorare con gli alberi delle espressioni:</span><span class="sxs-lookup"><span data-stu-id="0f2f4-135">Rather than try to memorize everything, here are the techniques I use to work with Expression trees:</span></span>
1. <span data-ttu-id="0f2f4-136">Esaminare i membri dell'enumerazione `ExpressionType` per determinare i possibili nodi da esaminare.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-136">Look at the members of the `ExpressionType` enum to determine possible nodes you should be examining.</span></span> <span data-ttu-id="0f2f4-137">Questo è estremamente utile quando si intende analizzare e comprendere un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-137">This really helps when you want to traverse and understand an expression tree.</span></span>
2. <span data-ttu-id="0f2f4-138">Esaminare i membri statici della classe `Expression` per compilare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-138">Look at the static members of the `Expression` class to build an expression.</span></span> <span data-ttu-id="0f2f4-139">Tali metodi possono compilare qualsiasi tipo di espressione da un set dei relativi nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-139">Those methods can build any expression type from a set of its child nodes.</span></span>
3. <span data-ttu-id="0f2f4-140">Esaminare la classe `ExpressionVisitor` per compilare un albero delle espressioni modificato.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-140">Look at the `ExpressionVisitor` class to build a modified expression tree.</span></span>

<span data-ttu-id="0f2f4-141">Esaminando ognuna di queste aree, si otterranno maggiori informazioni.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-141">You'll find more as you look at each of those three areas.</span></span> <span data-ttu-id="0f2f4-142">Si troverà quanto necessario iniziando con uno di questi tre passaggi.</span><span class="sxs-lookup"><span data-stu-id="0f2f4-142">Invariably, you will find what you need when you start with one of those three steps.</span></span>
 
 [<span data-ttu-id="0f2f4-143">Successivo -- Esecuzione di alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="0f2f4-143">Next -- Executing Expression Trees</span></span>](expression-trees-execution.md)
 

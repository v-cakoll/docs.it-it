---
title: Traduzione degli alberi delle espressioni
description: Informazioni su come visitare ogni nodo in un albero delle espressioni, creando una copia modificata di tale albero delle espressioni.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: b453c591-acc6-4e08-8175-97e5bc65958e
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 602a17591d27ebfd098516453b9028bca37ad5e3
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="translating-expression-trees"></a><span data-ttu-id="56129-104">Traduzione degli alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="56129-104">Translating Expression Trees</span></span>

[<span data-ttu-id="56129-105">Precedente -- Creazione di espressioni</span><span class="sxs-lookup"><span data-stu-id="56129-105">Previous -- Building Expressions</span></span>](expression-trees-building.md)

<span data-ttu-id="56129-106">In questa sezione finale si apprenderà come visitare ogni nodo in un albero delle espressioni, creando una copia modificata di tale albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="56129-106">In this final section, you'll learn how to visit each node in an expression tree while building a modified copy of that expression tree.</span></span> <span data-ttu-id="56129-107">Queste sono le tecniche che verranno usate in due scenari importanti.</span><span class="sxs-lookup"><span data-stu-id="56129-107">These are the techniques that you will use in two important scenarios.</span></span> <span data-ttu-id="56129-108">La prima consiste nel comprendere gli algoritmi espressi da un albero delle espressioni in modo che possa essere traslato in un altro ambiente.</span><span class="sxs-lookup"><span data-stu-id="56129-108">The first is to understand the algorithms expressed by an expression tree so that it can be translated into another environment.</span></span> <span data-ttu-id="56129-109">La seconda si applica quando si desidera modificare l'algoritmo creato.</span><span class="sxs-lookup"><span data-stu-id="56129-109">The second is when you want to change the algorithm that has been created.</span></span> <span data-ttu-id="56129-110">È possibile aggiungere la registrazione, intercettare chiamate al metodo e tenerne traccia, oltre ad altri scopi.</span><span class="sxs-lookup"><span data-stu-id="56129-110">This might be to add logging, intercept method calls and track them, or other purposes.</span></span>

## <a name="translating-is-visiting"></a><span data-ttu-id="56129-111">Traslare è sinonimo di visitare</span><span class="sxs-lookup"><span data-stu-id="56129-111">Translating is Visiting</span></span>

<span data-ttu-id="56129-112">Il codice compilato per traslare un albero delle espressioni è un'estensione di tutto questo, utile per visitare tutti i nodi in un albero.</span><span class="sxs-lookup"><span data-stu-id="56129-112">The code you build to translate an expression tree is an extension of what you've already seen to visit all the nodes in a tree.</span></span> <span data-ttu-id="56129-113">Quando si trasla un albero delle espressioni, tutti i nodi vengono visitati e durante la visita viene compilato il nuovo albero.</span><span class="sxs-lookup"><span data-stu-id="56129-113">When you translate an expression tree, you visit all the nodes, and while visiting them, build the new tree.</span></span> <span data-ttu-id="56129-114">Il nuovo albero può contenere riferimenti ai nodi originali o ai nuovi nodi posizionati nell'albero.</span><span class="sxs-lookup"><span data-stu-id="56129-114">The new tree may contain references to the original nodes, or new nodes that you have placed in the tree.</span></span>

<span data-ttu-id="56129-115">Vediamo questo aspetto praticamente visitando un albero delle espressioni e creando un nuovo albero con alcuni nodi di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="56129-115">Let's see this in action by visiting an expression tree, and creating a new tree with some replacement nodes.</span></span> <span data-ttu-id="56129-116">In questo esempio, sostituiamo qualsiasi costante con una costante dieci volte maggiore.</span><span class="sxs-lookup"><span data-stu-id="56129-116">In this example, let's replace any constant with a constant that is ten times larger.</span></span>
<span data-ttu-id="56129-117">In alternativa, possiamo lasciare l'albero delle espressioni intatto.</span><span class="sxs-lookup"><span data-stu-id="56129-117">Otherwise, we'll leave the expression tree intact.</span></span> <span data-ttu-id="56129-118">Invece di leggere il valore della costante e sostituirla con una nuova costante, eseguiremo una sostituzione del nodo della costante con un nuovo nodo che esegue la moltiplicazione.</span><span class="sxs-lookup"><span data-stu-id="56129-118">Rather than reading the value of the constant, and replacing it with a new constant, we'll make this replacement by replacing the constant node with a new node that performs the multiplication.</span></span>

<span data-ttu-id="56129-119">In questo caso, dopo aver trovato il nodo di una costante, creare un nuovo nodo di moltiplicazione i cui figli rappresentino la costante originale e la costante `10`:</span><span class="sxs-lookup"><span data-stu-id="56129-119">Here, once you find a constant node, you create a new multiplication node whose children are the original constant, and the constant `10`:</span></span>

```csharp
private static Expression ReplaceNodes(Expression original)
{
    if (original.NodeType == ExpressionType.Constant)
    {
        return Expression.Multiply(original, Expression.Constant(10));
    }
    else if (original.NodeType == ExpressionType.Add)
    {
        var binaryExpression = (BinaryExpression)original;
        return Expression.Add(
            ReplaceNodes(binaryExpression.Left),
            ReplaceNodes(binaryExpression.Right));
    }
    return original;
}
```

<span data-ttu-id="56129-120">Sostituendo il nodo originale con il sostituto, viene formato un nuovo albero che contiene le modifiche.</span><span class="sxs-lookup"><span data-stu-id="56129-120">By replacing the original node with the substitute, a new tree is formed that contains our modifications.</span></span> <span data-ttu-id="56129-121">Possiamo verificarlo tramite la compilazione e l'esecuzione dell'albero sostituito.</span><span class="sxs-lookup"><span data-stu-id="56129-121">We can verify that by compiling and executing the replaced tree.</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
var sum = ReplaceNodes(addition);
var executableFunc = Expression.Lambda(sum);

var func = (Func<int>)executableFunc.Compile();
var answer = func();
Console.WriteLine(answer);
```

<span data-ttu-id="56129-122">La creazione di un nuovo albero è una combinazione tra la visita ai nodi nell'albero esistente e la creazione e l'inserimento di nuovi nodi nell'albero.</span><span class="sxs-lookup"><span data-stu-id="56129-122">Building a new tree is a combination of visiting the nodes in the existing tree, and creating new nodes and inserting them into the tree.</span></span>

<span data-ttu-id="56129-123">Questo esempio illustra l'importanza dell'immutabilità degli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="56129-123">This example shows the importance of expression trees being immutable.</span></span> <span data-ttu-id="56129-124">Si noti che il nuovo albero creato in precedenza contiene una combinazione di nodi appena creati e nodi dall'albero esistente.</span><span class="sxs-lookup"><span data-stu-id="56129-124">Notice that the new tree created above contains a mixture of newly created nodes, and nodes from the existing tree.</span></span> <span data-ttu-id="56129-125">Questa combinazione è sicura, poiché i nodi dell'albero esistente non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="56129-125">That's safe, because the nodes in the existing tree cannot be modified.</span></span> <span data-ttu-id="56129-126">Ciò può comportare una notevole efficienza della memoria.</span><span class="sxs-lookup"><span data-stu-id="56129-126">This can result in significant memory efficiencies.</span></span>
<span data-ttu-id="56129-127">Gli stessi nodi possono essere usati in uno o più alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="56129-127">The same nodes can be used throughout a tree, or in multiple expression trees.</span></span> <span data-ttu-id="56129-128">Dal momento che i nodi non possono essere modificati, lo stesso nodo può essere riutilizzato secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="56129-128">Since nodes can't be modified, the same node can be reused whenever its needed.</span></span>

## <a name="traversing-and-executing-an-addition"></a><span data-ttu-id="56129-129">Attraversamento ed esecuzione di un'addizione</span><span class="sxs-lookup"><span data-stu-id="56129-129">Traversing and Executing an Addition</span></span>

<span data-ttu-id="56129-130">Esamineremo ora questi aspetti creando un secondo visitatore che percorre l'albero dei nodi di addizione e calcola il risultato.</span><span class="sxs-lookup"><span data-stu-id="56129-130">Let's verify this by building a second visitor that walks the tree of addition nodes and computes the result.</span></span> <span data-ttu-id="56129-131">È possibile realizzare tale operazione apportando un paio di modifiche al visitatore che abbiamo visto fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="56129-131">You can do this by making a couple modifications to the vistor that you've seen so far.</span></span> <span data-ttu-id="56129-132">In questa nuova versione, il visitatore restituisce la somma parziale dell'operazione di addizione fino a questo punto.</span><span class="sxs-lookup"><span data-stu-id="56129-132">In this new version, the visitor will return the partial sum of the addition operation up to this point.</span></span> <span data-ttu-id="56129-133">Per un'espressione costante, la somma corrisponde semplicemente al valore dell'espressione costante.</span><span class="sxs-lookup"><span data-stu-id="56129-133">For a constant expression, that is simply the value of the constant expression.</span></span> <span data-ttu-id="56129-134">Per un'espressione di addizione, il risultato è la somma degli operandi sinistro e destro, dopo l'attraversamento degli alberi.</span><span class="sxs-lookup"><span data-stu-id="56129-134">For an addition expression, the result is the sum of the left and right operands, once those trees have been traversed.</span></span>

```csharp
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var three= Expression.Constant(3, typeof(int));
var four = Expression.Constant(4, typeof(int));
var addition = Expression.Add(one, two);
var add2 = Expression.Add(three, four);
var sum = Expression.Add(addition, add2);

// Declare the delegate, so we can call it 
// from itself recursively:
Func<Expression, int> aggregate = null;
// Aggregate, return constants, or the sum of the left and right operand.
// Major simplification: Assume every binary expression is an addition.
aggregate = (exp) =>
    exp.NodeType == ExpressionType.Constant ?
    (int)((ConstantExpression)exp).Value :
    aggregate(((BinaryExpression)exp).Left) + aggregate(((BinaryExpression)exp).Right);

var theSum = aggregate(sum);
Console.WriteLine(theSum);
```

<span data-ttu-id="56129-135">Useremo qui il codice, ma i concetti sono molto intuitivi.</span><span class="sxs-lookup"><span data-stu-id="56129-135">There's quite a bit of code here, but the concepts are very approachable.</span></span>
<span data-ttu-id="56129-136">Questo codice visita gli elementi figlio in una prima ricerca profondità.</span><span class="sxs-lookup"><span data-stu-id="56129-136">This code visits children in a depth first search.</span></span> <span data-ttu-id="56129-137">Quando incontra un nodo della costante, il visitatore restituisce il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="56129-137">When it encounters a constant node, the visitor returns the value of the constant.</span></span> <span data-ttu-id="56129-138">Dopo che il visitatore ha visitato entrambi gli elementi figlio, verrà calcolata la somma per essi, per questo sottoalbero.</span><span class="sxs-lookup"><span data-stu-id="56129-138">After the visitor has visited both children, those children will have computed the sum computed for that sub-tree.</span></span> <span data-ttu-id="56129-139">A questo punto, il nodo di addizione può calcolare la somma.</span><span class="sxs-lookup"><span data-stu-id="56129-139">The addition node can now compute its sum.</span></span>
<span data-ttu-id="56129-140">Dopo aver visitato tutti i noti dell'albero delle espressioni, verrà calcolata la somma.</span><span class="sxs-lookup"><span data-stu-id="56129-140">Once all the nodes in the expression tree have been visited, the sum will have been computed.</span></span> <span data-ttu-id="56129-141">È possibile tracciare l'esecuzione eseguendo l'esempio nel debugger.</span><span class="sxs-lookup"><span data-stu-id="56129-141">You can trace the execution by running the sample in the debugger and tracing the execution.</span></span>

<span data-ttu-id="56129-142">Semplifichiamo il tracciamento dell'analisi dei nodi e delle modalità di calcolo della somma tramite l'attraversamento dell'albero.</span><span class="sxs-lookup"><span data-stu-id="56129-142">Let's make it easier to trace how the nodes are analyzed and how the sum is computed by travsersing the tree.</span></span> <span data-ttu-id="56129-143">Di seguito è riportata una versione aggiornata del metodo Aggregate che include una certa quantità di informazioni di tracciamento:</span><span class="sxs-lookup"><span data-stu-id="56129-143">Here's an updated version of the Aggregate method that includes quite a bit of tracing information:</span></span>

```csharp
private static int Aggregate(Expression exp)
{
    if (exp.NodeType == ExpressionType.Constant)
    {
        var constantExp = (ConstantExpression)exp;
        Console.Error.WriteLine($"Found Constant: {constantExp.Value}");
        return (int)constantExp.Value;
    }
    else if (exp.NodeType == ExpressionType.Add)
    {
        var addExp = (BinaryExpression)exp;
        Console.Error.WriteLine("Found Addition Expression");
        Console.Error.WriteLine("Computing Left node");
        var leftOperand = Aggregate(addExp.Left);
        Console.Error.WriteLine($"Left is: {leftOperand}");
        Console.Error.WriteLine("Computing Right node");
        var rightOperand = Aggregate(addExp.Right);
        Console.Error.WriteLine($"Right is: {rightOperand}");
        var sum = leftOperand + rightOperand;
        Console.Error.WriteLine($"Computed sum: {sum}");
        return sum;
    }
    else throw new NotSupportedException("Haven't written this yet");
}
```

<span data-ttu-id="56129-144">L'esecuzione del metodo sulla stessa espressione produce l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="56129-144">Running it on the same expression yields the following output:</span></span>

```
10
Found Addition Expression
Computing Left node
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Constant: 2
Right is: 2
Computed sum: 3
Left is: 3
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 10
10
```

<span data-ttu-id="56129-145">Tracciare l'output e procedere con il codice in alto.</span><span class="sxs-lookup"><span data-stu-id="56129-145">Trace the output and follow along in the code above.</span></span> <span data-ttu-id="56129-146">È possibile comprendere in che modo il codice visiti ogni nodo e calcoli la somma attraversando l'albero e trovando la somma.</span><span class="sxs-lookup"><span data-stu-id="56129-146">You should be able to work out how the code visits each node and computes the sum as it goes through the tree and finds the sum.</span></span>

<span data-ttu-id="56129-147">Esaminiamo ora un'esecuzione diversa, con l'espressione rappresentata da `sum1`:</span><span class="sxs-lookup"><span data-stu-id="56129-147">Now, let's look at a different run, with the expression given by `sum1`:</span></span>

```csharp
Expression<Func<int> sum1 = () => 1 + (2 + (3 + 4));
```

<span data-ttu-id="56129-148">Di seguito è riportato l'output dell'analisi di questa espressione:</span><span class="sxs-lookup"><span data-stu-id="56129-148">Here's the output from examining this expression:</span></span>

```
Found Addition Expression
Computing Left node
Found Constant: 1
Left is: 1
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 2
Left is: 2
Computing Right node
Found Addition Expression
Computing Left node
Found Constant: 3
Left is: 3
Computing Right node
Found Constant: 4
Right is: 4
Computed sum: 7
Right is: 7
Computed sum: 9
Right is: 9
Computed sum: 10
10
```

<span data-ttu-id="56129-149">Mentre la risposta finale è la stesso, l'attraversamento dell'albero è completamente diverso.</span><span class="sxs-lookup"><span data-stu-id="56129-149">While the final answer is the same, the tree traversal is completely different.</span></span> <span data-ttu-id="56129-150">I nodi vengono attraversati in un ordine diverso, perché l'albero è stato costruita con diverse operazioni che si verificano prima.</span><span class="sxs-lookup"><span data-stu-id="56129-150">The nodes are traveled in a different order, because the tree was constructed with different operations occurring first.</span></span>

## <a name="learning-more"></a><span data-ttu-id="56129-151">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="56129-151">Learning More</span></span>

<span data-ttu-id="56129-152">Questo esempio illustra un piccolo sottoinsieme del codice creato per attraversare e interpretare gli algoritmi rappresentati da un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="56129-152">This sample shows a small subset of the code you would build to traverse and interpret the algorithms represented by an expression tree.</span></span> <span data-ttu-id="56129-153">Per una descrizione completa di tutte le operazioni necessarie per compilare una libreria generica che trasla gli alberi delle espressioni in un'altra lingua, vedere [questa serie](http://blogs.msdn.com/b/mattwar/archive/2008/11/18/linq-links.aspx) di Matt Warren.</span><span class="sxs-lookup"><span data-stu-id="56129-153">For a complete discussion of all the work necessary to build a general purpose library that translates expression trees into another language, please read [this series](http://blogs.msdn.com/b/mattwar/archive/2008/11/18/linq-links.aspx) by Matt Warren.</span></span> <span data-ttu-id="56129-154">La serie spiega in dettaglio come traslare il codice di un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="56129-154">It goes into great detail on how to translate any of the code you might find in an expression tree.</span></span>

<span data-ttu-id="56129-155">Mi auguro che abbiamo percepito la vera potenza degli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="56129-155">I hope you've now seen the true power of expression trees.</span></span>
<span data-ttu-id="56129-156">È possibile esaminare un set di codice, apportare modifiche a tale codice ed eseguire la versione modificata.</span><span class="sxs-lookup"><span data-stu-id="56129-156">You can examine a set of code, make any changes you'd like to that code, and execute the changed version.</span></span> <span data-ttu-id="56129-157">Dal momento che gli alberi delle espressioni sono immutabili, è possibile creare nuovi alberi usando i componenti degli alberi esistenti.</span><span class="sxs-lookup"><span data-stu-id="56129-157">Because the expression trees are immutable, you can create new trees by using the components of existing trees.</span></span> <span data-ttu-id="56129-158">Questa operazione riduce la quantità di memoria necessaria per creare alberi delle espressioni modificati.</span><span class="sxs-lookup"><span data-stu-id="56129-158">This minimizes the amount of memory needed to create modified expression trees.</span></span>

[<span data-ttu-id="56129-159">Successivo -- Conclusioni</span><span class="sxs-lookup"><span data-stu-id="56129-159">Next -- Summing up</span></span>](expression-trees-summary.md)


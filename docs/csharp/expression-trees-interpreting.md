---
title: Interpretazione di espressioni
description: Informazioni su come scrivere codice per esaminare la struttura di un albero delle espressioni.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: adf73dde-1e52-4df3-9929-2e0670e28e16
ms.openlocfilehash: 1283d7d957c72558652b96cb428efd0f071f0184
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146008"
---
# <a name="interpreting-expressions"></a><span data-ttu-id="ae421-103">Interpretazione di espressioni</span><span class="sxs-lookup"><span data-stu-id="ae421-103">Interpreting Expressions</span></span>

[<span data-ttu-id="ae421-104">Precedente -- Esecuzione di espressioni</span><span class="sxs-lookup"><span data-stu-id="ae421-104">Previous -- Executing Expressions</span></span>](expression-trees-execution.md)

<span data-ttu-id="ae421-105">Scriviamo ora del codice per esaminare la struttura di un *albero delle espressioni*.</span><span class="sxs-lookup"><span data-stu-id="ae421-105">Now, let's write some code to examine the structure of an *expression tree*.</span></span> <span data-ttu-id="ae421-106">Ogni nodo in un albero delle espressioni sarà un oggetto di una classe derivata da `Expression`.</span><span class="sxs-lookup"><span data-stu-id="ae421-106">Every node in an expression tree will be an object of a class that is derived from `Expression`.</span></span>

<span data-ttu-id="ae421-107">Tale progettazione rende la visita di tutti i nodi in un albero delle espressioni un'operazione ricorsiva relativamente semplice.</span><span class="sxs-lookup"><span data-stu-id="ae421-107">That design makes visiting all the nodes in an expression tree a relatively straight forward recursive operation.</span></span> <span data-ttu-id="ae421-108">Come strategia generale, iniziare in corrispondenza del nodo radice e determinare di quale tipo di nodo si tratti.</span><span class="sxs-lookup"><span data-stu-id="ae421-108">The general strategy is to start at the root node and determine what kind of node it is.</span></span>

<span data-ttu-id="ae421-109">Se il tipo di nodo contiene elementi figlio, visitare in modo ricorsivo gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="ae421-109">If the node type has children, recursively visit the children.</span></span> <span data-ttu-id="ae421-110">In ogni nodo figlio, ripetere il processo usato in corrispondenza del nodo radice: determinare il tipo e, se il tipo contiene elementi figlio, visitare ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="ae421-110">At each child node, repeat the process used at the root node: determine the type, and if the type has children, visit each of the children.</span></span>

## <a name="examining-an-expression-with-no-children"></a><span data-ttu-id="ae421-111">Analisi di un'espressione senza elementi figlio</span><span class="sxs-lookup"><span data-stu-id="ae421-111">Examining an Expression with No Children</span></span>
<span data-ttu-id="ae421-112">Iniziare visitando ogni nodo in un albero delle espressioni molto semplice.</span><span class="sxs-lookup"><span data-stu-id="ae421-112">Let's start by visiting each node in a very simple expression tree.</span></span>
<span data-ttu-id="ae421-113">Ecco il codice che crea un'espressione costante e ne esamina quindi le proprietà:</span><span class="sxs-lookup"><span data-stu-id="ae421-113">Here's the code that creates a constant expression and then examines its properties:</span></span>

```csharp
var constant = Expression.Constant(24, typeof(int));

Console.WriteLine($"This is a/an {constant.NodeType} expression type");
Console.WriteLine($"The type of the constant value is {constant.Type}");
Console.WriteLine($"The value of the constant value is {constant.Value}");
```

<span data-ttu-id="ae421-114">Questo comporterà il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="ae421-114">This will print the following:</span></span>

```output
This is an Constant expression type
The type of the constant value is System.Int32
The value of the constant value is 24
```

<span data-ttu-id="ae421-115">A questo punto, iniziare a scrivere il codice che esamina l'espressione e scrivere alcune proprietà importanti su di esso.</span><span class="sxs-lookup"><span data-stu-id="ae421-115">Now, let's write the code that would examine this expression and write out some important properties about it.</span></span> <span data-ttu-id="ae421-116">Di seguito è riportato il codice:</span><span class="sxs-lookup"><span data-stu-id="ae421-116">Here's that code:</span></span>

## <a name="examining-a-simple-addition-expression"></a><span data-ttu-id="ae421-117">Analisi di un'espressione di addizione semplice</span><span class="sxs-lookup"><span data-stu-id="ae421-117">Examining a simple Addition Expression</span></span>

<span data-ttu-id="ae421-118">Iniziamo con l'esempio di addizione presentato nella parte introduttiva di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="ae421-118">Let's start with the addition sample from the introduction to this section.</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2;
```

> <span data-ttu-id="ae421-119">Non si usa `var` per dichiarare questo albero delle espressioni e ciò non è possibile perché il lato destro dell'assegnazione è tipizzato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="ae421-119">I'm not using `var` to declare this expression tree, as it is not possible because the right-hand side of the assignment is implicitly typed.</span></span> <span data-ttu-id="ae421-120">Per comprendere meglio questo meccanismo, leggere [qui](implicitly-typed-lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ae421-120">To understand this more deeply, read [here](implicitly-typed-lambda-expressions.md).</span></span>

<span data-ttu-id="ae421-121">Il nodo radice è una `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="ae421-121">The root node is a `LambdaExpression`.</span></span> <span data-ttu-id="ae421-122">Per ottenere la parte di codice di interesse a destra dell'operatore `=>`, è necessario trovare uno degli elementi figlio della `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="ae421-122">In order to get the interesting code on the right hand side of the `=>` operator, you need to find one of the children of the `LambdaExpression`.</span></span> <span data-ttu-id="ae421-123">È possibile farlo con tutte le espressioni in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="ae421-123">We'll do that with all the expressions in this section.</span></span> <span data-ttu-id="ae421-124">Il nodo padre consente di trovare il tipo restituito della `LambdaExpression`.</span><span class="sxs-lookup"><span data-stu-id="ae421-124">The parent node does help us find the return type of the `LambdaExpression`.</span></span>

<span data-ttu-id="ae421-125">Per esaminare ogni nodo in questa espressione, è necessario visitare in modo ricorsivo un certo numero di nodi.</span><span class="sxs-lookup"><span data-stu-id="ae421-125">To examine each node in this expression, we'll need to recursively visit a number of nodes.</span></span> <span data-ttu-id="ae421-126">Ecco una semplice prima implementazione:</span><span class="sxs-lookup"><span data-stu-id="ae421-126">Here's a simple first implementation:</span></span>

```csharp
Expression<Func<int, int, int>> addition = (a, b) => a + b;

Console.WriteLine($"This expression is a {addition.NodeType} expression type");
Console.WriteLine($"The name of the lambda is {((addition.Name == null) ? "<null>" : addition.Name)}");
Console.WriteLine($"The return type is {addition.ReturnType.ToString()}");
Console.WriteLine($"The expression has {addition.Parameters.Count} arguments. They are:");
foreach(var argumentExpression in addition.Parameters)
{
    Console.WriteLine($"\tParameter Type: {argumentExpression.Type.ToString()}, Name: {argumentExpression.Name}");
}

var additionBody = (BinaryExpression)addition.Body;
Console.WriteLine($"The body is a {additionBody.NodeType} expression");
Console.WriteLine($"The left side is a {additionBody.Left.NodeType} expression");
var left = (ParameterExpression)additionBody.Left;
Console.WriteLine($"\tParameter Type: {left.Type.ToString()}, Name: {left.Name}");
Console.WriteLine($"The right side is a {additionBody.Right.NodeType} expression");
var right= (ParameterExpression)additionBody.Right;
Console.WriteLine($"\tParameter Type: {right.Type.ToString()}, Name: {right.Name}");
```

<span data-ttu-id="ae421-127">Questo esempio dà l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="ae421-127">This sample prints the following output:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 arguments. They are:
        Parameter Type: System.Int32, Name: a
        Parameter Type: System.Int32, Name: b
The body is a/an Add expression
The left side is a Parameter expression
        Parameter Type: System.Int32, Name: a
The right side is a Parameter expression
        Parameter Type: System.Int32, Name: b
```

<span data-ttu-id="ae421-128">Nell'esempio di codice riportato sopra è possibile rilevare numerose ripetizioni.</span><span class="sxs-lookup"><span data-stu-id="ae421-128">You'll notice a lot of repetition in the code sample above.</span></span>
<span data-ttu-id="ae421-129">Procediamo alla pulizia e alla creazione di un visitatore del nodo dell'espressione per un utilizzo più generico.</span><span class="sxs-lookup"><span data-stu-id="ae421-129">Let's clean that up and build a more general purpose expression node visitor.</span></span> <span data-ttu-id="ae421-130">Questo richiederà la scrittura di un algoritmo ricorsivo.</span><span class="sxs-lookup"><span data-stu-id="ae421-130">That's going to require us to write a recursive algorithm.</span></span> <span data-ttu-id="ae421-131">Qualsiasi nodo potrebbe essere di un tipo con elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="ae421-131">Any node could be of a type that might have children.</span></span>
<span data-ttu-id="ae421-132">Qualsiasi nodo con elementi figlio richiede la visita di tali elementi figlio e la determinazione del tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="ae421-132">Any node that has children requires us to visit those children and determine what that node is.</span></span> <span data-ttu-id="ae421-133">Ecco la versione pulita che usa la ricorsione per visitare le operazioni di addizione:</span><span class="sxs-lookup"><span data-stu-id="ae421-133">Here's the cleaned up version that utilizes recursion to visit the addition operations:</span></span>

```csharp
// Base Visitor class:
public abstract class Visitor
{
    private readonly Expression node;

    protected Visitor(Expression node)
    {
        this.node = node;
    }

    public abstract void Visit(string prefix);

    public ExpressionType NodeType => this.node.NodeType;
    public static Visitor CreateFromExpression(Expression node)
    {
        switch(node.NodeType)
        {
            case ExpressionType.Constant:
                return new ConstantVisitor((ConstantExpression)node);
            case ExpressionType.Lambda:
                return new LambdaVisitor((LambdaExpression)node);
            case ExpressionType.Parameter:
                return new ParameterVisitor((ParameterExpression)node);
            case ExpressionType.Add:
                return new BinaryVisitor((BinaryExpression)node);
            default:
                Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
                return default(Visitor);
        }
    }
}

// Lambda Visitor
public class LambdaVisitor : Visitor
{
    private readonly LambdaExpression node;
    public LambdaVisitor(LambdaExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression type");
        Console.WriteLine($"{prefix}The name of the lambda is {((node.Name == null) ? "<null>" : node.Name)}");
        Console.WriteLine($"{prefix}The return type is {node.ReturnType.ToString()}");
        Console.WriteLine($"{prefix}The expression has {node.Parameters.Count} argument(s). They are:");
        // Visit each parameter:
        foreach (var argumentExpression in node.Parameters)
        {
            var argumentVisitor = Visitor.CreateFromExpression(argumentExpression);
            argumentVisitor.Visit(prefix + "\t");
        }
        Console.WriteLine($"{prefix}The expression body is:");
        // Visit the body:
        var bodyVisitor = Visitor.CreateFromExpression(node.Body);
        bodyVisitor.Visit(prefix + "\t");
    }
}

// Binary Expression Visitor:
public class BinaryVisitor : Visitor
{
    private readonly BinaryExpression node;
    public BinaryVisitor(BinaryExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This binary expression is a {NodeType} expression");
        var left = Visitor.CreateFromExpression(node.Left);
        Console.WriteLine($"{prefix}The Left argument is:");
        left.Visit(prefix + "\t");
        var right = Visitor.CreateFromExpression(node.Right);
        Console.WriteLine($"{prefix}The Right argument is:");
        right.Visit(prefix + "\t");
    }
}

// Parameter visitor:
public class ParameterVisitor : Visitor
{
    private readonly ParameterExpression node;
    public ParameterVisitor(ParameterExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}Type: {node.Type.ToString()}, Name: {node.Name}, ByRef: {node.IsByRef}");
    }
}

// Constant visitor:
public class ConstantVisitor : Visitor
{
    private readonly ConstantExpression node;
    public ConstantVisitor(ConstantExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This is an {NodeType} expression type");
        Console.WriteLine($"{prefix}The type of the constant value is {node.Type}");
        Console.WriteLine($"{prefix}The value of the constant value is {node.Value}");
    }
}
```

<span data-ttu-id="ae421-134">Questo algoritmo è la base di un algoritmo che può visitare qualsiasi `LambdaExpression` arbitraria.</span><span class="sxs-lookup"><span data-stu-id="ae421-134">This algorithm is the basis of an algorithm that can visit any arbitrary `LambdaExpression`.</span></span> <span data-ttu-id="ae421-135">Vi sono molte mancanze, in particolare perché il codice creato cerca soltanto un esempio molto ridotto dei possibili set di nodi dell'albero delle espressioni che potrebbe rilevare.</span><span class="sxs-lookup"><span data-stu-id="ae421-135">There are a lot of holes, namely that the code I created only looks for a very small sample of the possible sets of expression tree nodes that it may encounter.</span></span> <span data-ttu-id="ae421-136">È tuttavia possibile ricavare una certa quantità di informazioni utili dal risultato prodotto.</span><span class="sxs-lookup"><span data-stu-id="ae421-136">However, you can still learn quite a bit from what it produces.</span></span> <span data-ttu-id="ae421-137">Il caso predefinito nel metodo `Visitor.CreateFromExpression` visualizza un messaggio nella console di errore quando viene rilevato un nuovo tipo di nodo.</span><span class="sxs-lookup"><span data-stu-id="ae421-137">(The default case in the `Visitor.CreateFromExpression` method prints a message to the error console when a new node type is encountered.</span></span> <span data-ttu-id="ae421-138">In questo modo, si sa di dover aggiungere un nuovo tipo di espressione.</span><span class="sxs-lookup"><span data-stu-id="ae421-138">That way, you know to add a new expression type.)</span></span>

<span data-ttu-id="ae421-139">Quando si esegue questo visitatore nell'espressione di addizione precedente, si ottiene l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="ae421-139">When you run this visitor on the addition expression shown above, you get the following output:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This is an Parameter expression type
                Type: System.Int32, Name: b, ByRef: False
```

<span data-ttu-id="ae421-140">Ora che è stata creata un'implementazione del visitatore più generale, è possibile visitare ed elaborare più tipi diversi di espressioni.</span><span class="sxs-lookup"><span data-stu-id="ae421-140">Now that you've built a more general visitor implementation, you can visit and process many more different types of expressions.</span></span>

## <a name="examining-an-addition-expression-with-many-levels"></a><span data-ttu-id="ae421-141">Analisi di un'espressione di addizione con molti livelli</span><span class="sxs-lookup"><span data-stu-id="ae421-141">Examining an Addition Expression with Many Levels</span></span>

<span data-ttu-id="ae421-142">Procediamo con un esempio più complesso, limitando comunque i tipi di nodo alla sola addizione:</span><span class="sxs-lookup"><span data-stu-id="ae421-142">Let's try a more complicated example, yet still limit the node types to addition only:</span></span>

```csharp
Expression<Func<int>> sum = () => 1 + 2 + 3 + 4;
```

<span data-ttu-id="ae421-143">Prima di procedere all'esecuzione sull'algoritmo visitatore, provare a pensare quale potrebbe essere l'output.</span><span class="sxs-lookup"><span data-stu-id="ae421-143">Before you run this on the visitor algorithm, try a thought exercise to work out what the output might be.</span></span> <span data-ttu-id="ae421-144">Tenere presente che l'operatore `+` è un *operatore binario*: deve avere due figli, che rappresentano gli operandi sinistro e destro.</span><span class="sxs-lookup"><span data-stu-id="ae421-144">Remember that the `+` operator is a *binary operator*: it must have two children, representing the left and right operands.</span></span> <span data-ttu-id="ae421-145">Sono possibili diversi modi per costruire un albero che può essere corretto:</span><span class="sxs-lookup"><span data-stu-id="ae421-145">There are several possible ways to construct a tree that could be correct:</span></span>

```csharp
Expression<Func<int>> sum1 = () => 1 + (2 + (3 + 4));
Expression<Func<int>> sum2 = () => ((1 + 2) + 3) + 4;

Expression<Func<int>> sum3 = () => (1 + 2) + (3 + 4);
Expression<Func<int>> sum4 = () => 1 + ((2 + 3) + 4);
Expression<Func<int>> sum5 = () => (1 + (2 + 3)) + 4;
```

<span data-ttu-id="ae421-146">Si può visualizzare la separazione in due possibili risposte per evidenziare quella più efficace.</span><span class="sxs-lookup"><span data-stu-id="ae421-146">You can see the separation into two possible answers to highlight the most promising.</span></span> <span data-ttu-id="ae421-147">La prima possibilità rappresenta le espressioni *associative all'operando destro*.</span><span class="sxs-lookup"><span data-stu-id="ae421-147">The first represents *right associative* expressions.</span></span> <span data-ttu-id="ae421-148">La seconda rappresenta le espressioni *associative all'operando sinistro*.</span><span class="sxs-lookup"><span data-stu-id="ae421-148">The second represent *left associative* expressions.</span></span>
<span data-ttu-id="ae421-149">Il vantaggio di entrambi i formati è che il formato si adatta a qualsiasi numero arbitrario di espressioni di addizione.</span><span class="sxs-lookup"><span data-stu-id="ae421-149">The advantage of both of those two formats is that the format scales to any arbitrary number of addition expressions.</span></span>

<span data-ttu-id="ae421-150">Se si esegue questa espressione tramite il visitatore, verrà visualizzato questo output, che verifica che l'espressione di addizione semplice è *associativa all'operando sinistro*.</span><span class="sxs-lookup"><span data-stu-id="ae421-150">If you do run this expression through the visitor, you will see this this output, verifying that the simple addition expression is *left associative*.</span></span>

<span data-ttu-id="ae421-151">Per eseguire questo esempio e visualizzare l'albero delle espressioni completo, è stato necessario apportare una modifica all'albero delle espressioni di origine.</span><span class="sxs-lookup"><span data-stu-id="ae421-151">In order to run this sample, and see the full expression tree, I had to make one change to the source expression tree.</span></span> <span data-ttu-id="ae421-152">Quando l'albero delle espressioni contiene tutte le costanti, l'albero risultante contiene semplicemente il valore costante di `10`.</span><span class="sxs-lookup"><span data-stu-id="ae421-152">When the expression tree contains all constants, the resulting tree simply contains the constant value of `10`.</span></span> <span data-ttu-id="ae421-153">Il compilatore esegue tutta l'addizione e riduce l'espressione alla sua forma più semplice.</span><span class="sxs-lookup"><span data-stu-id="ae421-153">The compiler performs all the addition and reduces the expression to its simplest form.</span></span> <span data-ttu-id="ae421-154">La semplice aggiunta di una variabile nell'espressione è sufficiente per visualizzare l'albero originale:</span><span class="sxs-lookup"><span data-stu-id="ae421-154">Simply adding one variable in the expression is sufficient to see the original tree:</span></span>

```csharp
Expression<Func<int, int>> sum = (a) => 1 + a + 3 + 4;
```

<span data-ttu-id="ae421-155">Creare un visitatore per questa somma ed eseguire il visitatore per visualizzare l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="ae421-155">Create a visitor for this sum and run the visitor you'll see this output:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This binary expression is a Add expression
                        The Left argument is:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                        The Right argument is:
                                This is an Parameter expression type
                                Type: System.Int32, Name: a, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
        The Right argument is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 4
```

<span data-ttu-id="ae421-156">È anche possibile eseguire uno qualsiasi degli altri esempi tramite il codice del visitatore e vedere quali alberi rappresenta.</span><span class="sxs-lookup"><span data-stu-id="ae421-156">You can also run any of the other samples through the visitor code and see what tree it represents.</span></span> <span data-ttu-id="ae421-157">Di seguito è riportato un esempio dell'espressione `sum3` precedente (con un parametro aggiuntivo per impedire che il compilatore elabori la costante):</span><span class="sxs-lookup"><span data-stu-id="ae421-157">Here's an example of the `sum3` expression above (with an additional parameter to prevent the compiler from computing the constant):</span></span>

```csharp
Expression<Func<int, int, int>> sum3 = (a, b) => (1 + a) + (3 + b);
```

<span data-ttu-id="ae421-158">Di seguito è riportato l'output dal visitatore:</span><span class="sxs-lookup"><span data-stu-id="ae421-158">Here's the output from the visitor:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 2 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: a, ByRef: False
        This is an Parameter expression type
        Type: System.Int32, Name: b, ByRef: False
The expression body is:
        This binary expression is a Add expression
        The Left argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 1
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: a, ByRef: False
        The Right argument is:
                This binary expression is a Add expression
                The Left argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 3
                The Right argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: b, ByRef: False
```

<span data-ttu-id="ae421-159">Si noti che le parentesi non fanno parte dell'output.</span><span class="sxs-lookup"><span data-stu-id="ae421-159">Notice that the parentheses are not part of the output.</span></span> <span data-ttu-id="ae421-160">Non sono presenti nodi nell'albero delle espressioni che rappresentano le parentesi nell'espressione di input.</span><span class="sxs-lookup"><span data-stu-id="ae421-160">There are no nodes in the expression tree that represent the parentheses in the input expression.</span></span> <span data-ttu-id="ae421-161">La struttura dell'albero delle espressioni contiene tutte le informazioni necessarie per comunicare la precedenza.</span><span class="sxs-lookup"><span data-stu-id="ae421-161">The structure of the expression tree contains all the information necessary to communicate the precedence.</span></span>

## <a name="extending-from-this-sample"></a><span data-ttu-id="ae421-162">Estensione da questo esempio</span><span class="sxs-lookup"><span data-stu-id="ae421-162">Extending from this sample</span></span>

<span data-ttu-id="ae421-163">L'esempio riguarda solo gli alberi delle espressioni più elementari.</span><span class="sxs-lookup"><span data-stu-id="ae421-163">The sample deals with only the most rudimentary expression trees.</span></span> <span data-ttu-id="ae421-164">Il codice in questa sezione gestisce solo interi costanti e l'operatore `+` binario.</span><span class="sxs-lookup"><span data-stu-id="ae421-164">The code you've seen in this section only handles constant integers and the binary `+` operator.</span></span> <span data-ttu-id="ae421-165">Come esempio finale, aggiorniamo il visitatore per gestire un'espressione più complessa.</span><span class="sxs-lookup"><span data-stu-id="ae421-165">As a final sample, let's update the visitor to handle a more complicated expression.</span></span> <span data-ttu-id="ae421-166">Facciamolo funzionare in questo modo:</span><span class="sxs-lookup"><span data-stu-id="ae421-166">Let's make it work for this:</span></span>

```csharp
Expression<Func<int, int>> factorial = (n) =>
    n == 0 ?
    1 :
    Enumerable.Range(1, n).Aggregate((product, factor) => product * factor);
```

<span data-ttu-id="ae421-167">Questo codice rappresenta una possibile implementazione per funzione matematica *fattoriale*.</span><span class="sxs-lookup"><span data-stu-id="ae421-167">This code represents one possible implementation for the mathematical *factorial* function.</span></span> <span data-ttu-id="ae421-168">Il modo in cui è stato scritto questo codice consente di evidenziare due limitazioni della creazione degli alberi delle espressioni tramite l'assegnazione di espressioni lambda alle espressioni.</span><span class="sxs-lookup"><span data-stu-id="ae421-168">The way I've written this code highlights two limitations of building expression trees by assigning lambda expressions to Expressions.</span></span> <span data-ttu-id="ae421-169">In primo luogo, non sono consentite espressioni lambda dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="ae421-169">First, statement lambdas are not allowed.</span></span> <span data-ttu-id="ae421-170">Non è quindi possibile usare cicli, blocchi, istruzioni if / else e altre strutture di controllo comuni in C#.</span><span class="sxs-lookup"><span data-stu-id="ae421-170">That means I can't use loops, blocks, if / else statements, and other control structures common in C#.</span></span> <span data-ttu-id="ae421-171">Si è limitati all'uso delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="ae421-171">I'm limited to using expressions.</span></span> <span data-ttu-id="ae421-172">In secondo luogo, non è possibile chiamare in modo ricorsivo la stessa espressione.</span><span class="sxs-lookup"><span data-stu-id="ae421-172">Second, I can't recursively call the same expression.</span></span>
<span data-ttu-id="ae421-173">Ciò sarebbe possibile se fosse già un delegato, ma non può essere chiamata nella sua forma di albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="ae421-173">I could if it were already a delegate, but I can't call it in its expression tree form.</span></span> <span data-ttu-id="ae421-174">Nella sezione relativa alla [creazione di alberi delle espressioni](expression-trees-building.md) verranno illustrate le tecniche per superare queste limitazioni.</span><span class="sxs-lookup"><span data-stu-id="ae421-174">In the section on [building expression trees](expression-trees-building.md) you'll learn techniques to overcome these limitations.</span></span>

<span data-ttu-id="ae421-175">In questa espressione si incontrano i nodi di tutti questi tipi:</span><span class="sxs-lookup"><span data-stu-id="ae421-175">In this expression, you'll encounter nodes of all these types:</span></span>

1. <span data-ttu-id="ae421-176">Uguale (espressione binaria)</span><span class="sxs-lookup"><span data-stu-id="ae421-176">Equal (binary expression)</span></span>
2. <span data-ttu-id="ae421-177">Per (espressione binaria)</span><span class="sxs-lookup"><span data-stu-id="ae421-177">Multiply (binary expression)</span></span>
3. <span data-ttu-id="ae421-178">Condizionale (l'espressione ?</span><span class="sxs-lookup"><span data-stu-id="ae421-178">Conditional (the ?</span></span> <span data-ttu-id="ae421-179">: )</span><span class="sxs-lookup"><span data-stu-id="ae421-179">: expression)</span></span>
4. <span data-ttu-id="ae421-180">Espressione per chiamata al metodo (chiamata `Range()` e `Aggregate()`)</span><span class="sxs-lookup"><span data-stu-id="ae421-180">Method Call Expression (calling `Range()` and `Aggregate()`)</span></span>

<span data-ttu-id="ae421-181">Un modo per modificare l'algoritmo visitatore consiste nel continuare a eseguirlo e scrivere il tipo di nodo ogni volta che si raggiunge la clausola `default`.</span><span class="sxs-lookup"><span data-stu-id="ae421-181">One way to modify the visitor algorithm is to keep executing it, and write the node type every time you reach your `default` clause.</span></span> <span data-ttu-id="ae421-182">Dopo alcune iterazioni, si osserverà ognuno dei nodi potenziali.</span><span class="sxs-lookup"><span data-stu-id="ae421-182">After a few iterations, you'll have seen each of the potential nodes.</span></span> <span data-ttu-id="ae421-183">Si dispone quindi di tutto il necessario.</span><span class="sxs-lookup"><span data-stu-id="ae421-183">Then, you have all you need.</span></span> <span data-ttu-id="ae421-184">Il risultato è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ae421-184">The result would be something like this:</span></span>

```csharp
public static Visitor CreateFromExpression(Expression node)
{
    switch(node.NodeType)
    {
        case ExpressionType.Constant:
            return new ConstantVisitor((ConstantExpression)node);
        case ExpressionType.Lambda:
            return new LambdaVisitor((LambdaExpression)node);
        case ExpressionType.Parameter:
            return new ParameterVisitor((ParameterExpression)node);
        case ExpressionType.Add:
        case ExpressionType.Equal:
        case ExpressionType.Multiply:
            return new BinaryVisitor((BinaryExpression)node);
        case ExpressionType.Conditional:
            return new ConditionalVisitor((ConditionalExpression)node);
        case ExpressionType.Call:
            return new MethodCallVisitor((MethodCallExpression)node);
        default:
            Console.Error.WriteLine($"Node not processed yet: {node.NodeType}");
            return default(Visitor);
    }
}
```

<span data-ttu-id="ae421-185">Il ConditionalVisitor e il MethodCallVisitor elaborano questi due nodi:</span><span class="sxs-lookup"><span data-stu-id="ae421-185">The ConditionalVisitor and MethodCallVisitor process those two nodes:</span></span>

```csharp
public class ConditionalVisitor : Visitor
{
    private readonly ConditionalExpression node;
    public ConditionalVisitor(ConditionalExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        var testVisitor = Visitor.CreateFromExpression(node.Test);
        Console.WriteLine($"{prefix}The Test for this expression is:");
        testVisitor.Visit(prefix + "\t");
        var trueVisitor = Visitor.CreateFromExpression(node.IfTrue);
        Console.WriteLine($"{prefix}The True clause for this expression is:");
        trueVisitor.Visit(prefix + "\t");
        var falseVisitor = Visitor.CreateFromExpression(node.IfFalse);
        Console.WriteLine($"{prefix}The False clause for this expression is:");
        falseVisitor.Visit(prefix + "\t");
    }
}

public class MethodCallVisitor : Visitor
{
    private readonly MethodCallExpression node;
    public MethodCallVisitor(MethodCallExpression node) : base(node)
    {
        this.node = node;
    }

    public override void Visit(string prefix)
    {
        Console.WriteLine($"{prefix}This expression is a {NodeType} expression");
        if (node.Object == null)
            Console.WriteLine($"{prefix}This is a static method call");
        else
        {
            Console.WriteLine($"{prefix}The receiver (this) is:");
            var receiverVisitor = Visitor.CreateFromExpression(node.Object);
            receiverVisitor.Visit(prefix + "\t");
        }

        var methodInfo = node.Method;
        Console.WriteLine($"{prefix}The method name is {methodInfo.DeclaringType}.{methodInfo.Name}");
        // There is more here, like generic arguments, and so on.
        Console.WriteLine($"{prefix}The Arguments are:");
        foreach(var arg in node.Arguments)
        {
            var argVisitor = Visitor.CreateFromExpression(arg);
            argVisitor.Visit(prefix + "\t");
        }
    }
}
```

<span data-ttu-id="ae421-186">L'output per l'albero delle espressioni sarà:</span><span class="sxs-lookup"><span data-stu-id="ae421-186">And the output for the expression tree would be:</span></span>

```output
This expression is a/an Lambda expression type
The name of the lambda is <null>
The return type is System.Int32
The expression has 1 argument(s). They are:
        This is an Parameter expression type
        Type: System.Int32, Name: n, ByRef: False
The expression body is:
        This expression is a Conditional expression
        The Test for this expression is:
                This binary expression is a Equal expression
                The Left argument is:
                        This is an Parameter expression type
                        Type: System.Int32, Name: n, ByRef: False
                The Right argument is:
                        This is an Constant expression type
                        The type of the constant value is System.Int32
                        The value of the constant value is 0
        The True clause for this expression is:
                This is an Constant expression type
                The type of the constant value is System.Int32
                The value of the constant value is 1
        The False clause for this expression is:
                This expression is a Call expression
                This is a static method call
                The method name is System.Linq.Enumerable.Aggregate
                The Arguments are:
                        This expression is a Call expression
                        This is a static method call
                        The method name is System.Linq.Enumerable.Range
                        The Arguments are:
                                This is an Constant expression type
                                The type of the constant value is System.Int32
                                The value of the constant value is 1
                                This is an Parameter expression type
                                Type: System.Int32, Name: n, ByRef: False
                        This expression is a Lambda expression type
                        The name of the lambda is <null>
                        The return type is System.Int32
                        The expression has 2 arguments. They are:
                                This is an Parameter expression type
                                Type: System.Int32, Name: product, ByRef: False
                                This is an Parameter expression type
                                Type: System.Int32, Name: factor, ByRef: False
                        The expression body is:
                                This binary expression is a Multiply expression
                                The Left argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: product, ByRef: False
                                The Right argument is:
                                        This is an Parameter expression type
                                        Type: System.Int32, Name: factor, ByRef: False
```

## <a name="extending-the-sample-library"></a><span data-ttu-id="ae421-187">Estensione della libreria degli esempi</span><span class="sxs-lookup"><span data-stu-id="ae421-187">Extending the Sample Library</span></span>

<span data-ttu-id="ae421-188">Gli esempi in questa sezione illustrano le tecniche principali per visitare ed esaminare i nodi in un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="ae421-188">The samples in this section show the core techniques to visit and examine nodes in an expression tree.</span></span> <span data-ttu-id="ae421-189">Sono state tralasciate molte azioni che potrebbero essere necessarie in modo da concentrarsi sulle attività di base relative alla visita e all'accesso ai nodi in un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="ae421-189">I glossed over many actions you might need in order to concentrate on the core tasks of visiting and accessing nodes in an expression tree.</span></span>

<span data-ttu-id="ae421-190">In primo luogo, i visitatori gestiscono solo le costanti che sono valori interi.</span><span class="sxs-lookup"><span data-stu-id="ae421-190">First, the visitors only handle constants that are integers.</span></span> <span data-ttu-id="ae421-191">I valori costanti potrebbero essere di qualsiasi altro tipo numerico e il linguaggio C# supporta le conversioni e le promozioni tra tali tipi.</span><span class="sxs-lookup"><span data-stu-id="ae421-191">Constant values could be any other numeric type, and the C# language supports conversions and promotions between those types.</span></span> <span data-ttu-id="ae421-192">Una versione più affidabile di questo codice rispecchierebbe tutte queste funzionalità.</span><span class="sxs-lookup"><span data-stu-id="ae421-192">A more robust version of this code would mirror all those capabilities.</span></span>

<span data-ttu-id="ae421-193">Anche nell'ultimo esempio viene riconosciuto un sottoinsieme dei possibili tipi di nodo.</span><span class="sxs-lookup"><span data-stu-id="ae421-193">Even the last example recognizes a subset of the possible node types.</span></span>
<span data-ttu-id="ae421-194">È comunque possibile inserire molte espressioni che ne determinerebbero l'esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ae421-194">You can still feed it many expressions that will cause it to fail.</span></span>
<span data-ttu-id="ae421-195">Un'implementazione completa è inclusa in .NET Standard con il nome <xref:System.Linq.Expressions.ExpressionVisitor> e consente di gestire tutti i possibili tipi di nodo.</span><span class="sxs-lookup"><span data-stu-id="ae421-195">A full implementation is included in the .NET Standard under the name <xref:System.Linq.Expressions.ExpressionVisitor> and can handle all the possible node types.</span></span>

<span data-ttu-id="ae421-196">Infine, la libreria usata in questo articolo è stata creata per la formazione e dimostrazione.</span><span class="sxs-lookup"><span data-stu-id="ae421-196">Finally, the library I used in this article was built for demonstration and learning.</span></span> <span data-ttu-id="ae421-197">Non è ottimizzata.</span><span class="sxs-lookup"><span data-stu-id="ae421-197">It's not optimized.</span></span> <span data-ttu-id="ae421-198">È stata scritta per rendere le strutture usate molto chiare e per evidenziare le tecniche applicate per visitare i nodi e analizzarne il contenuto.</span><span class="sxs-lookup"><span data-stu-id="ae421-198">I wrote it to make the structures used very clear, and to highlight the techniques used to visit the nodes and analyze what's there.</span></span> <span data-ttu-id="ae421-199">Un'implementazione di produzione presterebbe maggiore attenzione alle prestazioni di quanto è stato fatto qui.</span><span class="sxs-lookup"><span data-stu-id="ae421-199">A production implementation would pay more attention to performance than I have.</span></span>

<span data-ttu-id="ae421-200">Anche con queste limitazioni, sarà possibile iniziare a scrivere algoritmi e leggere e comprendere gli alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="ae421-200">Even with those limitations, you should be well on your way to writing algorithms that read and understand expression trees.</span></span>

[<span data-ttu-id="ae421-201">Successivo -- Creazione di espressioni</span><span class="sxs-lookup"><span data-stu-id="ae421-201">Next -- Building Expressions</span></span>](expression-trees-building.md)

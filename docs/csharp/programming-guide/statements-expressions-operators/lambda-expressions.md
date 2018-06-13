---
title: Espressioni lambda (Guida per programmatori C#)
ms.date: 03/03/2017
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: f20ba6845a6a84a57fa7636355d08b2f4e5cea2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340645"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="c092c-102">Espressioni lambda (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c092c-102">Lambda Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="c092c-103">Un'espressione lambda è una [funzione anonima](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) che è possibile utilizzare per creare [delegati](../../../csharp/programming-guide/delegates/using-delegates.md) o tipi di [alberi delle espressioni](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) .</span><span class="sxs-lookup"><span data-stu-id="c092c-103">A lambda expression is an [anonymous function](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) that you can use to create [delegates](../../../csharp/programming-guide/delegates/using-delegates.md) or [expression tree](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) types.</span></span> <span data-ttu-id="c092c-104">Mediante le espressioni lambda è possibile scrivere funzioni locali che possono essere passate come argomenti o restituite come valore delle chiamate di funzione.</span><span class="sxs-lookup"><span data-stu-id="c092c-104">By using lambda expressions, you can write local functions that can be passed as arguments or returned as the value of function calls.</span></span> <span data-ttu-id="c092c-105">Le espressioni lambda sono particolarmente utili per la scrittura delle espressioni di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="c092c-105">Lambda expressions are particularly helpful for writing LINQ query expressions.</span></span>  
  
 <span data-ttu-id="c092c-106">Per creare un'espressione lambda, specificare gli eventuali parametri di input a sinistra dell'operatore lambda [=>](../../../csharp/language-reference/operators/lambda-operator.md)e inserire l'espressione o il blocco di istruzioni dall'altra parte.</span><span class="sxs-lookup"><span data-stu-id="c092c-106">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator [=>](../../../csharp/language-reference/operators/lambda-operator.md), and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="c092c-107">Ad esempio, l'espressione lambda `x => x * x` specifica un parametro denominato `x` e restituisce il valore di `x` al quadrato.</span><span class="sxs-lookup"><span data-stu-id="c092c-107">For example, the lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="c092c-108">È possibile assegnare questa espressione a un tipo di delegato, come illustrato nell'esempio riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c092c-108">You can assign this expression to a delegate type, as the following example shows:</span></span>  
  
```csharp  
delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```  
  
 <span data-ttu-id="c092c-109">Per creare un tipo di albero delle espressioni:</span><span class="sxs-lookup"><span data-stu-id="c092c-109">To create an expression tree type:</span></span>  
  
```csharp  
using System.Linq.Expressions;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Expression<del> myET = x => x * x;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="c092c-110">L'operatore `=>` ha la stessa precedenza dell'assegnazione (`=`) e [prevede l'associazione all'operando di destra](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (vedere la sezione "Associazione" dell'articolo sugli operatori).</span><span class="sxs-lookup"><span data-stu-id="c092c-110">The `=>` operator has the same precedence as assignment (`=`) and is [right associative](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (see "Associativity" section of the Operators article).</span></span>  
  
 <span data-ttu-id="c092c-111">Le espressioni lambda vengono utilizzate nelle query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] basate sul metodo come argomenti dei metodi di operatori di query standard, quali <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="c092c-111">Lambdas are used in method-based [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries as arguments to standard query operator methods such as <xref:System.Linq.Enumerable.Where%2A>.</span></span>  
  
 <span data-ttu-id="c092c-112">Quando si utilizza la sintassi basata sul metodo per chiamare il metodo <xref:System.Linq.Enumerable.Where%2A> nella classe <xref:System.Linq.Enumerable> , come in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects e [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], il parametro è un tipo <xref:System.Func%602?displayProperty=nameWithType>delegato.</span><span class="sxs-lookup"><span data-stu-id="c092c-112">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Where%2A> method in the <xref:System.Linq.Enumerable> class (as you do in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c092c-113">Un'espressione lambda è il modo più pratico per creare tale delegato.</span><span class="sxs-lookup"><span data-stu-id="c092c-113">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="c092c-114">Quando, ad esempio, si chiama lo stesso metodo nella classe <xref:System.Linq.Queryable?displayProperty=nameWithType>, come in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], il tipo di parametro è <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\>, dove Func è un qualsiasi delegato Func con un massimo di sedici parametri di input.</span><span class="sxs-lookup"><span data-stu-id="c092c-114">When you call the same method in, for example, the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) then the parameter type is an <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\> where Func is any of the Func delegates with up to sixteen input parameters.</span></span> <span data-ttu-id="c092c-115">Un'espressione lambda rappresenta quindi un modo rapido per costruire tale albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="c092c-115">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="c092c-116">Mediante le espressioni lambda, le chiamate `Where` risultano simili anche se in realtà il tipo di oggetto creato dall'espressione lambda è diverso.</span><span class="sxs-lookup"><span data-stu-id="c092c-116">The lambdas allow the `Where` calls to look similar although in fact the type of object created from the lambda is different.</span></span>  
  
 <span data-ttu-id="c092c-117">Nell'esempio precedente si noti che la firma del delegato ha un parametro di input tipizzato in modo implicito di tipo `int`e restituisce un oggetto `int`.</span><span class="sxs-lookup"><span data-stu-id="c092c-117">In the previous example, notice that the delegate signature has one implicitly-typed input parameter of type `int`, and returns an `int`.</span></span> <span data-ttu-id="c092c-118">L'espressione lambda può essere convertita in un delegato di tale tipo poiché dispone anche di un parametro di input (`x`) e di un valore restituito che il compilatore può convertire in modo implicito nel tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="c092c-118">The lambda expression can be converted to a delegate of that type because it also has one input parameter (`x`) and a return value that the compiler can implicitly convert to type `int`.</span></span> <span data-ttu-id="c092c-119">L'inferenza dei tipi viene illustrata più dettagliatamente nelle sezioni seguenti. Quando il delegato viene richiamato tramite un parametro di input pari a 5, restituisce un risultato di 25.</span><span class="sxs-lookup"><span data-stu-id="c092c-119">(Type inference is discussed in more detail in the following sections.) When the delegate is invoked by using an input parameter of 5, it returns a result of 25.</span></span>  
  
 <span data-ttu-id="c092c-120">Non è possibile usare le espressioni lambda a sinistra dell'operatore [is](../../../csharp/language-reference/keywords/is.md) o [as](../../../csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="c092c-120">Lambdas are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) or [as](../../../csharp/language-reference/keywords/as.md) operator.</span></span>  
  
 <span data-ttu-id="c092c-121">Tutte le restrizioni che si applicano ai metodi anonimi si applicano anche alle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="c092c-121">All restrictions that apply to anonymous methods also apply to lambda expressions.</span></span> <span data-ttu-id="c092c-122">Per altre informazioni, vedere [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="c092c-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
## <a name="expression-lambdas"></a><span data-ttu-id="c092c-123">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="c092c-123">Expression Lambdas</span></span>  
 <span data-ttu-id="c092c-124">Un'espressione lambda con un'espressione a destra dell'operatore => è denominata *espressione lambda*.</span><span class="sxs-lookup"><span data-stu-id="c092c-124">A lambda expression with an expression on the right side of the => operator is called an *expression lambda*.</span></span> <span data-ttu-id="c092c-125">Queste espressioni vengono usate spesso nella costruzione di [alberi delle espressioni](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b).</span><span class="sxs-lookup"><span data-stu-id="c092c-125">Expression lambdas are used extensively in the construction of [Expression Trees](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b).</span></span> <span data-ttu-id="c092c-126">Un'espressione lambda dell'espressione restituisce il risultato dell'espressione e ha il formato di base seguente:</span><span class="sxs-lookup"><span data-stu-id="c092c-126">An expression lambda returns the result of the expression and takes the following basic form:</span></span>  
  
```csharp
(input-parameters) => expression
```

 <span data-ttu-id="c092c-127">Le parentesi sono facoltative solo se l'espressione lambda ha un parametro di input; in caso contrario sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="c092c-127">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span> <span data-ttu-id="c092c-128">Due o più parametri di input vengono separati da virgole e racchiusi tra parentesi:</span><span class="sxs-lookup"><span data-stu-id="c092c-128">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>  
  
```csharp
(x, y) => x == y
```

 <span data-ttu-id="c092c-129">Talvolta è difficile o impossibile che il compilatore deduca i tipi di input.</span><span class="sxs-lookup"><span data-stu-id="c092c-129">Sometimes it is difficult or impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="c092c-130">In tal caso, è possibile specificare i tipi in modo esplicito come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c092c-130">When this occurs, you can specify the types explicitly as shown in the following example:</span></span>  
  
```csharp
(int x, string s) => s.Length > x
```

 <span data-ttu-id="c092c-131">Specificare zero parametri di input con parentesi vuote:</span><span class="sxs-lookup"><span data-stu-id="c092c-131">Specify zero input parameters with empty parentheses:</span></span>  
  
```csharp
() => SomeMethod()
```

 <span data-ttu-id="c092c-132">Si noti che nell'esempio precedente il corpo di un'espressione lambda dell'espressione può essere costituito da una chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="c092c-132">Note in the previous example that the body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="c092c-133">Tuttavia, se si creano alberi delle espressioni valutati al di fuori di .NET Framework, ad esempio in SQL Server, non è consigliabile utilizzare chiamate al metodo nelle espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="c092c-133">However, if you are creating expression trees that are evaluated outside of the .NET Framework, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="c092c-134">I metodi non avranno alcun significato all'esterno del contesto di .NET Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c092c-134">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>  
  
## <a name="statement-lambdas"></a><span data-ttu-id="c092c-135">Espressioni lambda dell'istruzione</span><span class="sxs-lookup"><span data-stu-id="c092c-135">Statement Lambdas</span></span>  
 <span data-ttu-id="c092c-136">Un'espressione lambda dell'istruzione è simile a un'espressione lambda dell'espressione con la differenza che l'istruzione o le istruzioni sono racchiuse tra parentesi graffe:</span><span class="sxs-lookup"><span data-stu-id="c092c-136">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>  
  
<span data-ttu-id="c092c-137">(input-parameters) => { statement; }</span><span class="sxs-lookup"><span data-stu-id="c092c-137">(input-parameters) => { statement; }</span></span>

 <span data-ttu-id="c092c-138">Il corpo di un'espressione lambda dell'istruzione può essere costituito da un numero qualsiasi di istruzioni, sebbene in pratica generalmente non ce ne siano più di due o tre.</span><span class="sxs-lookup"><span data-stu-id="c092c-138">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>  
  
[!code-csharp[StatementLamba#1](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#1)]

[!code-csharp[StatementLamba#2](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#2)]

 <span data-ttu-id="c092c-139">Le espressioni lambda dell'istruzione, come i metodi anonimi, non possono essere utilizzate per creare alberi delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="c092c-139">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="c092c-140">Espressioni lambda asincrone</span><span class="sxs-lookup"><span data-stu-id="c092c-140">Async Lambdas</span></span>  
 <span data-ttu-id="c092c-141">È facile creare istruzioni ed espressioni lambda che includono l'elaborazione asincrona utilizzando le parole chiave [async](../../../csharp/language-reference/keywords/async.md) e [await](../../../csharp/language-reference/keywords/await.md) .</span><span class="sxs-lookup"><span data-stu-id="c092c-141">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../../csharp/language-reference/keywords/async.md) and [await](../../../csharp/language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="c092c-142">Nell'esempio seguente di Windows Form è presente un gestore eventi che chiama e attende un metodo asincrono, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="c092c-142">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```csharp
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
    }  
  
    private async void button1_Click(object sender, EventArgs e)  
    {  
        // ExampleMethodAsync returns a Task.  
        await ExampleMethodAsync();  
        textBox1.Text += "\r\nControl returned to Click event handler.\n";  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```

 <span data-ttu-id="c092c-143">È possibile aggiungere lo stesso gestore eventi utilizzando un'espressione lambda asincrona.</span><span class="sxs-lookup"><span data-stu-id="c092c-143">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="c092c-144">Per aggiungere il gestore, aggiungere un modificatore `async` prima dell'elenco di parametri lambda, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c092c-144">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        button1.Click += async (sender, e) =>  
        {  
            // ExampleMethodAsync returns a Task.  
            await ExampleMethodAsync();  
            textBox1.Text += "\nControl returned to Click event handler.\n";  
        };  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```  

 <span data-ttu-id="c092c-145">Per altre informazioni su come creare e usare i metodi asincroni, vedere [Programmazione asincrona con async e await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="c092c-145">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="c092c-146">Espressioni lambda con operatori di query standard</span><span class="sxs-lookup"><span data-stu-id="c092c-146">Lambdas with the Standard Query Operators</span></span>  
 <span data-ttu-id="c092c-147">Molti operatori di query standard hanno un parametro di input il cui tipo è uno della famiglia <xref:System.Func%602> di delegati generici.</span><span class="sxs-lookup"><span data-stu-id="c092c-147">Many Standard query operators have an input parameter whose type is one of the <xref:System.Func%602> family of generic delegates.</span></span> <span data-ttu-id="c092c-148">Questi delegati utilizzano parametri di tipo per definire il numero e i tipi di parametri di input e il tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="c092c-148">These delegates use type parameters to define the number and types of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="c092c-149">I delegati`Func` sono molto utili per incapsulare le espressioni definite dall'utente applicate a ogni elemento in un set di dati di origine.</span><span class="sxs-lookup"><span data-stu-id="c092c-149">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="c092c-150">Considerare ad esempio il seguente tipo delegato:</span><span class="sxs-lookup"><span data-stu-id="c092c-150">For example, consider the following delegate type:</span></span>  
  
```csharp  
public delegate TResult Func<TArg0, TResult>(TArg0 arg0)  
```  
  
 <span data-ttu-id="c092c-151">È possibile creare un'istanza del delegato come `Func<int,bool> myFunc` dove `int` è un parametro di input e `bool` è il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="c092c-151">The delegate can be instantiated as `Func<int,bool> myFunc` where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="c092c-152">Il valore restituito è sempre specificato nell'ultimo parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="c092c-152">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="c092c-153">`Func<int, string, bool>` definisce un delegato con due parametri di input, `int` e `string`, e un tipo restituito `bool`.</span><span class="sxs-lookup"><span data-stu-id="c092c-153">`Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="c092c-154">Quando viene richiamato, il delegato `Func` seguente restituisce true o false per indicare se il parametro di input è uguale a 5:</span><span class="sxs-lookup"><span data-stu-id="c092c-154">The following `Func` delegate, when it is invoked, will return true or false to indicate whether the input parameter is equal to 5:</span></span>  
  
```csharp  
Func<int, bool> myFunc = x => x == 5;  
bool result = myFunc(4); // returns false of course  
```  
  
 <span data-ttu-id="c092c-155">È inoltre possibile fornire un'espressione lambda quando il tipo di argomento è `Expression<Func>`, ad esempio negli operatori di query standard definiti in System.Linq.Queryable.</span><span class="sxs-lookup"><span data-stu-id="c092c-155">You can also supply a lambda expression when the argument type is an `Expression<Func>`, for example in the standard query operators that are defined in System.Linq.Queryable.</span></span> <span data-ttu-id="c092c-156">Quando si specifica un argomento `Expression<Func>` , l'espressione lambda viene compilata in un albero delle espressioni.</span><span class="sxs-lookup"><span data-stu-id="c092c-156">When you specify an `Expression<Func>` argument, the lambda will be compiled to an expression tree.</span></span>  
  
 <span data-ttu-id="c092c-157">Di seguito viene illustrato un operatore di query standard, il metodo <xref:System.Linq.Enumerable.Count%2A> :</span><span class="sxs-lookup"><span data-stu-id="c092c-157">A standard query operator, the <xref:System.Linq.Enumerable.Count%2A> method, is shown here:</span></span>  
  
```csharp  
int[] numbers = { 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };  
int oddNumbers = numbers.Count(n => n % 2 == 1);  
```  
  
 <span data-ttu-id="c092c-158">Il compilatore è in grado di dedurre il tipo del parametro di input oppure è possibile specificarlo in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="c092c-158">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="c092c-159">Questa espressione lambda particolare conta i numeri interi (`n`) che divisi per due danno il resto di 1.</span><span class="sxs-lookup"><span data-stu-id="c092c-159">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>  
  
 <span data-ttu-id="c092c-160">La seguente riga di codice produce una sequenza che contiene tutti gli elementi presenti nella matrice `numbers` che si trovano a sinistra di 9, che rappresenta il primo numero della sequenza che non soddisfa la condizione:</span><span class="sxs-lookup"><span data-stu-id="c092c-160">The following line of code produces a sequence that contains all elements in the `numbers` array that are to the left side of the 9 because that's the first number in the sequence that doesn't meet the condition:</span></span>  
  
```csharp  
var firstNumbersLessThan6 = numbers.TakeWhile(n => n < 6);  
```  
  
 <span data-ttu-id="c092c-161">In questo esempio viene illustrato come specificare più parametri di input racchiudendoli tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="c092c-161">This example shows how to specify multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="c092c-162">Il metodo restituisce tutti gli elementi presenti nella matrice di numeri finché non viene rilevato un numero il cui valore è inferiore alla relativa posizione.</span><span class="sxs-lookup"><span data-stu-id="c092c-162">The method returns all the elements in the numbers array until a number is encountered whose value is less than its position.</span></span> <span data-ttu-id="c092c-163">Non confondere l'operatore lambda (`=>`) con l'operatore Greater Than o Equals (`>=`).</span><span class="sxs-lookup"><span data-stu-id="c092c-163">Do not confuse the lambda operator (`=>`) with the greater than or equal operator (`>=`).</span></span>  
  
```csharp  
var firstSmallNumbers = numbers.TakeWhile((n, index) => n >= index);  
```  
  
## <a name="type-inference-in-lambdas"></a><span data-ttu-id="c092c-164">Inferenza dei tipi nelle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="c092c-164">Type Inference in Lambdas</span></span>  
 <span data-ttu-id="c092c-165">Quando si scrivono le espressioni lambda, spesso non occorre specificare un tipo per i parametri di input in quanto il compilatore è in grado di dedurlo in base al corpo dell'espressione lambda, al tipo delegato del parametro e ad altri fattori, come descritto nella specifica del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="c092c-165">When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter’s delegate type, and other factors as described in the C# Language Specification.</span></span> <span data-ttu-id="c092c-166">Per la maggior parte degli operatori di query standard, il primo input è il tipo degli elementi nella sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="c092c-166">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="c092c-167">Pertanto se si esegue una query su un oggetto `IEnumerable<Customer>`, si deduce che la variabile di input sia un oggetto `Customer` , ovvero che si dispone dell'accesso ai relativi metodi e proprietà:</span><span class="sxs-lookup"><span data-stu-id="c092c-167">So if you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  
  
```csharp  
customers.Where(c => c.City == "London");  
```  
  
 <span data-ttu-id="c092c-168">Di seguito sono riportate le regole generali per le espressioni lambda:</span><span class="sxs-lookup"><span data-stu-id="c092c-168">The general rules for lambdas are as follows:</span></span>  
  
-   <span data-ttu-id="c092c-169">L'espressione lambda deve contenere lo stesso numero di parametri del tipo delegato.</span><span class="sxs-lookup"><span data-stu-id="c092c-169">The lambda must contain the same number of parameters as the delegate type.</span></span>  
  
-   <span data-ttu-id="c092c-170">Ogni parametro di input nell'espressione lambda deve essere convertibile in modo implicito nel parametro del delegato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c092c-170">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>  
  
-   <span data-ttu-id="c092c-171">Il valore restituito dell'espressione lambda, se presente, deve essere convertibile in modo implicito nel tipo restituito del delegato.</span><span class="sxs-lookup"><span data-stu-id="c092c-171">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>  
  
 <span data-ttu-id="c092c-172">Si noti che le espressioni lambda non hanno un tipo poiché Common Type System non ha alcun concetto intrinseco di "espressione lambda".</span><span class="sxs-lookup"><span data-stu-id="c092c-172">Note that lambda expressions in themselves do not have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="c092c-173">In alcuni casi, tuttavia, può essere utile fare riferimento in modo informale al "tipo" di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="c092c-173">However, it is sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="c092c-174">In questi casi, per tipo si intende il tipo delegato o il tipo <xref:System.Linq.Expressions.Expression> in cui viene convertita l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="c092c-174">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>  
  
## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="c092c-175">Ambito delle variabili nelle espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="c092c-175">Variable Scope in Lambda Expressions</span></span>  
 <span data-ttu-id="c092c-176">Le espressioni lambda possono fare riferimento alle *variabili esterne* (vedere [Metodi anonimi](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) presenti nell'ambito del metodo che definisce la funzione lambda oppure nell'ambito del tipo che contiene l'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="c092c-176">Lambdas can refer to *outer variables* (see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) that are in scope in the method that defines the lambda function, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="c092c-177">Le variabili acquisite in questo modo vengono archiviate per poter essere utilizzate nell'espressione lambda anche se le variabili diventano esterne all'ambito e vengono sottoposte a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c092c-177">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="c092c-178">Una variabile esterna deve essere assegnata prima di poter essere utilizzata in un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="c092c-178">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="c092c-179">Nell'esempio seguente vengono illustrate queste regole:</span><span class="sxs-lookup"><span data-stu-id="c092c-179">The following example demonstrates these rules:</span></span>  
  
```csharp  
delegate bool D();  
delegate bool D2(int i);  
  
class Test  
{  
    D del;  
    D2 del2;  
    public void TestMethod(int input)  
    {  
        int j = 0;  
        // Initialize the delegates with lambda expressions.  
        // Note access to 2 outer variables.  
        // del will be invoked within this method.  
        del = () => { j = 10;  return j > input; };  
  
        // del2 will be invoked after TestMethod goes out of scope.  
        del2 = (x) => {return x == j; };  
  
        // Demonstrate value of j:  
        // Output: j = 0   
        // The delegate has not been invoked yet.  
        Console.WriteLine("j = {0}", j);        // Invoke the delegate.  
        bool boolResult = del();  
  
        // Output: j = 10 b = True  
        Console.WriteLine("j = {0}. b = {1}", j, boolResult);  
    }  
  
    static void Main()  
    {  
        Test test = new Test();  
        test.TestMethod(5);  
  
        // Prove that del2 still has a copy of  
        // local variable j from TestMethod.  
        bool result = test.del2(10);  
  
        // Output: True  
        Console.WriteLine(result);  
  
        Console.ReadKey();  
    }  
}  
```  
  
 <span data-ttu-id="c092c-180">Le regole seguenti si applicano all'ambito delle variabili nelle espressioni lambda:</span><span class="sxs-lookup"><span data-stu-id="c092c-180">The following rules apply to variable scope in lambda expressions:</span></span>  
  
-   <span data-ttu-id="c092c-181">Una variabile acquisita non sarà sottoposta a Garbage Collection finché il delegato a cui fa riferimento non diventa idoneo per il Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c092c-181">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>  
  
-   <span data-ttu-id="c092c-182">Le variabili introdotte all'interno di un'espressione lambda non sono visibili nel metodo esterno.</span><span class="sxs-lookup"><span data-stu-id="c092c-182">Variables introduced within a lambda expression are not visible in the outer method.</span></span>  
  
-   <span data-ttu-id="c092c-183">Un'espressione lambda non può acquisire direttamente un parametro `in`, `ref` o `out` da un metodo contenitore.</span><span class="sxs-lookup"><span data-stu-id="c092c-183">A lambda expression cannot directly capture an `in`, `ref`, or `out` parameter from an enclosing method.</span></span>  
  
-   <span data-ttu-id="c092c-184">Un'istruzione return in un'espressione lambda non causa la restituzione del metodo contenitore.</span><span class="sxs-lookup"><span data-stu-id="c092c-184">A return statement in a lambda expression does not cause the enclosing method to return.</span></span>  
  
-   <span data-ttu-id="c092c-185">Un'espressione lambda non può contenere un'istruzione `goto` , `break` o `continue` , inclusa nella funzione lambda se la destinazione dell'istruzione jump è esterna al blocco.</span><span class="sxs-lookup"><span data-stu-id="c092c-185">A lambda expression cannot contain a `goto` statement, `break` statement, or `continue` statement that is inside the lambda function if the jump statement’s target is outside the block.</span></span> <span data-ttu-id="c092c-186">È altresì errato inserire all'esterno del blocco della funzione lambda un'istruzione jump se la destinazione è interna al blocco.</span><span class="sxs-lookup"><span data-stu-id="c092c-186">It is also an error to have a jump statement outside the lambda function block if the target is inside the block.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c092c-187">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c092c-187">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="c092c-188">Capitoli del libro rappresentati</span><span class="sxs-lookup"><span data-stu-id="c092c-188">Featured Book Chapter</span></span>  
 <span data-ttu-id="c092c-189">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) (Delegati, eventi ed espressioni lambda) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="c092c-189">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c092c-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c092c-190">See Also</span></span>  
 [<span data-ttu-id="c092c-191">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c092c-191">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c092c-192">LINQ (Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="c092c-192">LINQ (Language-Integrated Query)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="c092c-193">Metodi anonimi</span><span class="sxs-lookup"><span data-stu-id="c092c-193">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [<span data-ttu-id="c092c-194">is</span><span class="sxs-lookup"><span data-stu-id="c092c-194">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="c092c-195">Alberi delle espressioni</span><span class="sxs-lookup"><span data-stu-id="c092c-195">Expression Trees</span></span>](../../../csharp/programming-guide/concepts/expression-trees/index.md)  
 [<span data-ttu-id="c092c-196">Esempi C# di Visual Studio 2008 (vedere i file di query di esempio LINQ e il programma XQuery)</span><span class="sxs-lookup"><span data-stu-id="c092c-196">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](http://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)  
 [<span data-ttu-id="c092c-197">Recursive lambda expressions (Espressioni lambda ricorsive)</span><span class="sxs-lookup"><span data-stu-id="c092c-197">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)

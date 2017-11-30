---
title: =&gt; Operatore (Riferimenti per C#)
ms.date: 10/02/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44cb0485aefa8b0ab10a00ae0525180020ce436d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="4cfef-102">=&gt; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4cfef-102">=&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="4cfef-103">Il `=>` operatore può essere utilizzato in due modi in c#:</span><span class="sxs-lookup"><span data-stu-id="4cfef-103">The `=>` operator can be used in two ways in C#:</span></span>

- <span data-ttu-id="4cfef-104">Come il [operatore lambda](#lamba-operator) in un [espressione lambda](../../lambda-expressions.md), separa le variabili di input dal corpo dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="4cfef-104">As the [lambda operator](#lamba-operator) in a [lambda expression](../../lambda-expressions.md), it separates the input variables from the lambda body.</span></span>
 
- <span data-ttu-id="4cfef-105">In un [Definizione corpo dell'espressione](#expression-body-definition), l'implementazione del membro separa un nome di membro.</span><span class="sxs-lookup"><span data-stu-id="4cfef-105">In an [expression body definition](#expression-body-definition), it separates a member name from the member implementation.</span></span> 

## <a name="lambda-operator"></a><span data-ttu-id="4cfef-106">Lambda (operatore)</span><span class="sxs-lookup"><span data-stu-id="4cfef-106">Lambda operator</span></span>

<span data-ttu-id="4cfef-107">Il token `=>` viene chiamato operatore lambda.</span><span class="sxs-lookup"><span data-stu-id="4cfef-107">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="4cfef-108">Viene usato nelle *espressioni lambda* per separare le variabili di input sul lato sinistro dal corpo dell'espressione lambda da quelle sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="4cfef-108">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="4cfef-109">Le espressioni lambda sono espressioni inline simili ai metodi anonimi ma più flessibili. Vengono usate ampiamente nelle query LINQ espresse nella sintassi del metodo.</span><span class="sxs-lookup"><span data-stu-id="4cfef-109">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="4cfef-110">Per altre informazioni, vedere [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4cfef-110">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="4cfef-111">Nell'esempio seguente vengono illustrate due modalità per individuare e visualizzare la lunghezza della stringa più breve in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="4cfef-111">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="4cfef-112">La prima parte dell'esempio applica un'espressione lambda (`w => w.Length`) a ogni elemento della matrice `words` e usa quindi il metodo <xref:System.Linq.Enumerable.Min%2A> per individuare la lunghezza minima.</span><span class="sxs-lookup"><span data-stu-id="4cfef-112">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="4cfef-113">La seconda parte dell'esempio mostra invece una soluzione più lunga che usa la sintassi della query per eseguire la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="4cfef-113">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
```csharp  
string[] words = { "cherry", "apple", "blueberry" };  
  
// Use method syntax to apply a lambda expression to each element  
// of the words array.   
int shortestWordLength = words.Min(w => w.Length);  
Console.WriteLine(shortestWordLength);  
  
// Compare the following code that uses query syntax.  
// Get the lengths of each word in the words array.  
var query = from w in words  
            select w.Length;  
// Apply the Min method to execute the query and get the shortest length.  
int shortestWordLength2 = query.Min();  
Console.WriteLine(shortestWordLength2);  
  
// Output:   
// 5  
// 5  
```  
  
### <a name="remarks"></a><span data-ttu-id="4cfef-114">Note</span><span class="sxs-lookup"><span data-stu-id="4cfef-114">Remarks</span></span>  
 <span data-ttu-id="4cfef-115">L'operatore `=>` ha la stessa priorità dell'operatore di assegnazione (`=`) e si associa all'operando a destra.</span><span class="sxs-lookup"><span data-stu-id="4cfef-115">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="4cfef-116">È possibile specificare il tipo di variabile di input in modo esplicito o consentendo al compilatore di dedurlo; in entrambi i casi, la variabile è fortemente tipizzata in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4cfef-116">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="4cfef-117">Quando si specifica un tipo, è necessario racchiudere tra parentesi il nome del tipo e il nome della variabile, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="4cfef-117">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a><span data-ttu-id="4cfef-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="4cfef-118">Example</span></span>  
 <span data-ttu-id="4cfef-119">Nell'esempio seguente viene illustrato come scrivere un'espressione lambda per eseguire l'overload dell'operatore query standard <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> che accetta due argomenti.</span><span class="sxs-lookup"><span data-stu-id="4cfef-119">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> that takes two arguments.</span></span> <span data-ttu-id="4cfef-120">Poiché l'espressione lambda contiene più di un parametro, i parametri devono essere racchiusi tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="4cfef-120">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="4cfef-121">Il secondo parametro, `index`, rappresenta l'indice dell'elemento corrente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="4cfef-121">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="4cfef-122">L'espressione `Where` restituisce tutte le stringhe la cui lunghezza è minore rispetto alla loro posizione nell'indice nella matrice.</span><span class="sxs-lookup"><span data-stu-id="4cfef-122">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
```csharp  
static void Main(string[] args)  
{  
    string[] digits = { "zero", "one", "two", "three", "four", "five",   
            "six", "seven", "eight", "nine" };  
  
    Console.WriteLine("Example that uses a lambda expression:");  
    var shortDigits = digits.Where((digit, index) => digit.Length < index);  
    foreach (var sD in shortDigits)  
    {  
        Console.WriteLine(sD);  
    }  
  
    // Output:  
    // Example that uses a lambda expression:  
    // five  
    // six  
    // seven  
    // eight  
    // nine  
}  
```  
## <a name="expression-body-definition"></a><span data-ttu-id="4cfef-123">Definizione del corpo dell'espressione</span><span class="sxs-lookup"><span data-stu-id="4cfef-123">Expression body definition</span></span>

<span data-ttu-id="4cfef-124">Una definizione di espressioni corpo fornisce l'implementazione di un membro in un formato leggibile, estremamente ridotto.</span><span class="sxs-lookup"><span data-stu-id="4cfef-124">An expression body definition provides a member's implementation in a highly condensed, readable form.</span></span> <span data-ttu-id="4cfef-125">Contiene la sintassi generale seguente:</span><span class="sxs-lookup"><span data-stu-id="4cfef-125">It has the following general syntax:</span></span>

```csharp
member => expression;
```
<span data-ttu-id="4cfef-126">dove *expression* è un'espressione valida.</span><span class="sxs-lookup"><span data-stu-id="4cfef-126">where *expression* is a valid expression.</span></span> <span data-ttu-id="4cfef-127">Si noti che *espressione* può essere un *espressione di istruzione* solo se il membro restituito del tipo è `void`, o se il membro è un costruttore o un finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="4cfef-127">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor or a finalizer.</span></span>

<span data-ttu-id="4cfef-128">Definizioni di espressioni corpo per i metodi e le istruzioni get di proprietà sono supportate a partire da c# 6.</span><span class="sxs-lookup"><span data-stu-id="4cfef-128">Expression body definitions for methods and property get statements are supported starting with C# 6.</span></span> <span data-ttu-id="4cfef-129">Definizioni di espressioni corpo per i costruttori, finalizzatori, istruzioni di set di proprietà e gli indicizzatori sono supportati a partire da C# 7.</span><span class="sxs-lookup"><span data-stu-id="4cfef-129">Expression body definitions for constructors, finalizers, property set statements, and indexers are supported starting with C# 7.</span></span>

<span data-ttu-id="4cfef-130">Di seguito è una definizione del corpo di espressione per un `Person.ToString` metodo:</span><span class="sxs-lookup"><span data-stu-id="4cfef-130">The following is an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="4cfef-131">È una versione abbreviata di definizione di metodo seguenti:</span><span class="sxs-lookup"><span data-stu-id="4cfef-131">It is a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
<span data-ttu-id="4cfef-132">Per ulteriori informazioni sulle definizioni di espressioni corpo, vedere [densi espressione membri](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="4cfef-132">For more detailed information on expression body definitions, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4cfef-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cfef-133">See Also</span></span>  
<span data-ttu-id="4cfef-134">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4cfef-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="4cfef-135">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4cfef-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
<span data-ttu-id="4cfef-136">[Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="4cfef-136">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
<span data-ttu-id="4cfef-137">[I membri con corpo espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="4cfef-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>
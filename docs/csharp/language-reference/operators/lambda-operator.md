---
title: =&gt; Operatore (Riferimenti per C#)
ms.date: 10/02/2017
f1_keywords:
- =>_CSharpKeyword
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.openlocfilehash: d1565e262fbd3ebcee2d1576a2a0c8ed3ba8ce38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288226"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="5c926-102">=&gt; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="5c926-102">=&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="5c926-103">L'operatore `=>` può essere usato in due modi in C#:</span><span class="sxs-lookup"><span data-stu-id="5c926-103">The `=>` operator can be used in two ways in C#:</span></span>

- <span data-ttu-id="5c926-104">Come l'[operatore lambda](#lamba-operator) in un'[espressione lambda](../../lambda-expressions.md), separa le variabili di input dal corpo dell'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="5c926-104">As the [lambda operator](#lamba-operator) in a [lambda expression](../../lambda-expressions.md), it separates the input variables from the lambda body.</span></span>
 
- <span data-ttu-id="5c926-105">In una [definizione del corpo dell'espressione](#expression-body-definition), separa un nome membro dall'implementazione membro.</span><span class="sxs-lookup"><span data-stu-id="5c926-105">In an [expression body definition](#expression-body-definition), it separates a member name from the member implementation.</span></span> 

## <a name="lambda-operator"></a><span data-ttu-id="5c926-106">Operatore lambda</span><span class="sxs-lookup"><span data-stu-id="5c926-106">Lambda operator</span></span>

<span data-ttu-id="5c926-107">Il token `=>` viene chiamato operatore lambda.</span><span class="sxs-lookup"><span data-stu-id="5c926-107">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="5c926-108">Viene usato nelle *espressioni lambda* per separare le variabili di input sul lato sinistro dal corpo dell'espressione lambda da quelle sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="5c926-108">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="5c926-109">Le espressioni lambda sono espressioni inline simili ai metodi anonimi ma più flessibili. Vengono usate ampiamente nelle query LINQ espresse nella sintassi del metodo.</span><span class="sxs-lookup"><span data-stu-id="5c926-109">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="5c926-110">Per altre informazioni, vedere [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5c926-110">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="5c926-111">Nell'esempio seguente vengono illustrate due modalità per individuare e visualizzare la lunghezza della stringa più breve in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="5c926-111">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="5c926-112">La prima parte dell'esempio applica un'espressione lambda (`w => w.Length`) a ogni elemento della matrice `words` e usa quindi il metodo <xref:System.Linq.Enumerable.Min%2A> per individuare la lunghezza minima.</span><span class="sxs-lookup"><span data-stu-id="5c926-112">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="5c926-113">La seconda parte dell'esempio mostra invece una soluzione più lunga che usa la sintassi della query per eseguire la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="5c926-113">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
### <a name="remarks"></a><span data-ttu-id="5c926-114">Note</span><span class="sxs-lookup"><span data-stu-id="5c926-114">Remarks</span></span>  
 <span data-ttu-id="5c926-115">L'operatore `=>` ha la stessa priorità dell'operatore di assegnazione (`=`) e si associa all'operando a destra.</span><span class="sxs-lookup"><span data-stu-id="5c926-115">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="5c926-116">È possibile specificare il tipo di variabile di input in modo esplicito o consentendo al compilatore di dedurlo; in entrambi i casi, la variabile è fortemente tipizzata in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="5c926-116">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="5c926-117">Quando si specifica un tipo, è necessario racchiudere tra parentesi il nome del tipo e il nome della variabile, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5c926-117">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a><span data-ttu-id="5c926-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="5c926-118">Example</span></span>  
 <span data-ttu-id="5c926-119">Nell'esempio seguente viene illustrato come scrivere un'espressione lambda per eseguire l'overload dell'operatore query standard <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> che accetta due argomenti.</span><span class="sxs-lookup"><span data-stu-id="5c926-119">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> that takes two arguments.</span></span> <span data-ttu-id="5c926-120">Poiché l'espressione lambda contiene più di un parametro, i parametri devono essere racchiusi tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="5c926-120">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="5c926-121">Il secondo parametro, `index`, rappresenta l'indice dell'elemento corrente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="5c926-121">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="5c926-122">L'espressione `Where` restituisce tutte le stringhe la cui lunghezza è minore rispetto alla loro posizione nell'indice nella matrice.</span><span class="sxs-lookup"><span data-stu-id="5c926-122">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
## <a name="expression-body-definition"></a><span data-ttu-id="5c926-123">Definizione del corpo dell'espressione</span><span class="sxs-lookup"><span data-stu-id="5c926-123">Expression body definition</span></span>

<span data-ttu-id="5c926-124">Una definizione del corpo dell'espressione offre l'implementazione di un membro in un modulo molto conciso e leggibile.</span><span class="sxs-lookup"><span data-stu-id="5c926-124">An expression body definition provides a member's implementation in a highly condensed, readable form.</span></span> <span data-ttu-id="5c926-125">Contiene la sintassi generale seguente:</span><span class="sxs-lookup"><span data-stu-id="5c926-125">It has the following general syntax:</span></span>

```csharp
member => expression;
```
<span data-ttu-id="5c926-126">dove *expression* è un'espressione valida.</span><span class="sxs-lookup"><span data-stu-id="5c926-126">where *expression* is a valid expression.</span></span> <span data-ttu-id="5c926-127">Si noti che *expression* può essere un'*espressione di istruzione* solo se il membro restituito del tipo è `void` o se il membro è un costruttore o un finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="5c926-127">Note that *expression* can be a *statement expression* only if the member's return type is `void`, or if the member is a constructor or a finalizer.</span></span>

<span data-ttu-id="5c926-128">Le definizioni del corpo dell'espressione per i metodi e le istruzioni Property Get sono supportate a partire da C# 6.</span><span class="sxs-lookup"><span data-stu-id="5c926-128">Expression body definitions for methods and property get statements are supported starting with C# 6.</span></span> <span data-ttu-id="5c926-129">Le definizioni del corpo dell'espressione per costruttori, finalizzatori, istruzioni Property Set e indicizzatori sono supportate a partire da C# 7.</span><span class="sxs-lookup"><span data-stu-id="5c926-129">Expression body definitions for constructors, finalizers, property set statements, and indexers are supported starting with C# 7.</span></span>

<span data-ttu-id="5c926-130">Di seguito è riportata una definizione del corpo dell'espressione per un metodo `Person.ToString`:</span><span class="sxs-lookup"><span data-stu-id="5c926-130">The following is an expression body definition for a `Person.ToString` method:</span></span>

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

<span data-ttu-id="5c926-131">È una versione abbreviata della definizione di metodo seguente:</span><span class="sxs-lookup"><span data-stu-id="5c926-131">It is a shorthand version of the following method definition:</span></span>

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
<span data-ttu-id="5c926-132">Per altre informazioni dettagliate sulle definizioni del corpo dell'espressione, vedere [Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="5c926-132">For more detailed information on expression body definitions, see [Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c926-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c926-133">See Also</span></span>  
<span data-ttu-id="5c926-134">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c926-134">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="5c926-135">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5c926-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
<span data-ttu-id="5c926-136">[Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="5c926-136">[Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md) </span></span>  
<span data-ttu-id="5c926-137">[Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span><span class="sxs-lookup"><span data-stu-id="5c926-137">[Expression-bodied members](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).</span></span>
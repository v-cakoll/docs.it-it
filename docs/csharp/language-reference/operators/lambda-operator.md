---
title: =&gt; Operatore (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- lambda operator [C#]
- => operator [C#]
- lambda expressions [C#], => operator
ms.assetid: 8c899251-dafa-4594-bec7-243b39072880
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 45d4753724ed094408e8cbc5353998a67071b0e4
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="e39ab-102">=&gt; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e39ab-102">=&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="e39ab-103">Il token `=>` viene chiamato operatore lambda.</span><span class="sxs-lookup"><span data-stu-id="e39ab-103">The `=>` token is called the lambda operator.</span></span> <span data-ttu-id="e39ab-104">Viene usato nelle *espressioni lambda* per separare le variabili di input sul lato sinistro dal corpo dell'espressione lambda da quelle sul lato destro.</span><span class="sxs-lookup"><span data-stu-id="e39ab-104">It is used in *lambda expressions* to separate the input variables on the left side from the lambda body on the right side.</span></span> <span data-ttu-id="e39ab-105">Le espressioni lambda sono espressioni inline simili ai metodi anonimi ma più flessibili. Vengono usate ampiamente nelle query LINQ espresse nella sintassi del metodo.</span><span class="sxs-lookup"><span data-stu-id="e39ab-105">Lambda expressions are inline expressions similar to anonymous methods but more flexible; they are used extensively in LINQ queries that are expressed in method syntax.</span></span> <span data-ttu-id="e39ab-106">Per altre informazioni, vedere [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e39ab-106">For more information, see [Lambda Expressions](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="e39ab-107">Nell'esempio seguente vengono illustrate due modalità per individuare e visualizzare la lunghezza della stringa più breve in una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="e39ab-107">The following example shows two ways to find and display the length of the shortest string in an array of strings.</span></span> <span data-ttu-id="e39ab-108">La prima parte dell'esempio applica un'espressione lambda (`w => w.Length`) a ogni elemento della matrice `words` e usa quindi il metodo <xref:System.Linq.Enumerable.Min%2A> per individuare la lunghezza minima.</span><span class="sxs-lookup"><span data-stu-id="e39ab-108">The first part of the example applies a lambda expression (`w => w.Length`) to each element of the `words` array and then uses the <xref:System.Linq.Enumerable.Min%2A> method to find the smallest length.</span></span> <span data-ttu-id="e39ab-109">La seconda parte dell'esempio mostra invece una soluzione più lunga che usa la sintassi della query per eseguire la stessa operazione.</span><span class="sxs-lookup"><span data-stu-id="e39ab-109">For comparison, the second part of the example shows a longer solution that uses query syntax to do the same thing.</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="e39ab-110">Note</span><span class="sxs-lookup"><span data-stu-id="e39ab-110">Remarks</span></span>  
 <span data-ttu-id="e39ab-111">L'operatore `=>` ha la stessa priorità dell'operatore di assegnazione (`=`) e si associa all'operando a destra.</span><span class="sxs-lookup"><span data-stu-id="e39ab-111">The `=>` operator has the same precedence as the assignment operator (`=`) and is right-associative.</span></span>  
  
 <span data-ttu-id="e39ab-112">È possibile specificare il tipo di variabile di input in modo esplicito o consentendo al compilatore di dedurlo; in entrambi i casi, la variabile è fortemente tipizzata in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e39ab-112">You can specify the type of the input variable explicitly or let the compiler infer it; in either case, the variable is strongly typed at compile time.</span></span> <span data-ttu-id="e39ab-113">Quando si specifica un tipo, è necessario racchiudere tra parentesi il nome del tipo e il nome della variabile, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="e39ab-113">When you specify a type, you must enclose the type name and the variable name in parentheses, as the following example shows.</span></span>  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
## <a name="example"></a><span data-ttu-id="e39ab-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="e39ab-114">Example</span></span>  
 <span data-ttu-id="e39ab-115">Nell'esempio seguente viene illustrato come scrivere un'espressione lambda per eseguire l'overload dell'operatore query standard <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> che accetta due argomenti.</span><span class="sxs-lookup"><span data-stu-id="e39ab-115">The following example shows how to write a lambda expression for the overload of the standard query operator <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName> that takes two arguments.</span></span> <span data-ttu-id="e39ab-116">Poiché l'espressione lambda contiene più di un parametro, i parametri devono essere racchiusi tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="e39ab-116">Because the lambda expression has more than one parameter, the parameters must be enclosed in parentheses.</span></span> <span data-ttu-id="e39ab-117">Il secondo parametro, `index`, rappresenta l'indice dell'elemento corrente nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="e39ab-117">The second parameter, `index`, represents the index of the current element in the collection.</span></span> <span data-ttu-id="e39ab-118">L'espressione `Where` restituisce tutte le stringhe la cui lunghezza è minore rispetto alla loro posizione nell'indice nella matrice.</span><span class="sxs-lookup"><span data-stu-id="e39ab-118">The `Where` expression returns all the strings whose lengths are less than their index positions in the array.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e39ab-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e39ab-119">See Also</span></span>  
 <span data-ttu-id="e39ab-120">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e39ab-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e39ab-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e39ab-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e39ab-122">Espressioni lambda</span><span class="sxs-lookup"><span data-stu-id="e39ab-122">Lambda Expressions</span></span>](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)


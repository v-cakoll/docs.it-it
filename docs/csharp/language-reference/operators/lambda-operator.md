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
---
# <a name="gt-operator-c-reference"></a>=&gt; Operatore (Riferimenti per C#)

L'operatore `=>` può essere usato in due modi in C#:

- Come l'[operatore lambda](#lamba-operator) in un'[espressione lambda](../../lambda-expressions.md), separa le variabili di input dal corpo dell'espressione lambda.
 
- In una [definizione del corpo dell'espressione](#expression-body-definition), separa un nome membro dall'implementazione membro. 

## <a name="lambda-operator"></a>Operatore lambda

Il token `=>` viene chiamato operatore lambda. Viene usato nelle *espressioni lambda* per separare le variabili di input sul lato sinistro dal corpo dell'espressione lambda da quelle sul lato destro. Le espressioni lambda sono espressioni inline simili ai metodi anonimi ma più flessibili. Vengono usate ampiamente nelle query LINQ espresse nella sintassi del metodo. Per altre informazioni, vedere [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Nell'esempio seguente vengono illustrate due modalità per individuare e visualizzare la lunghezza della stringa più breve in una matrice di stringhe. La prima parte dell'esempio applica un'espressione lambda (`w => w.Length`) a ogni elemento della matrice `words` e usa quindi il metodo <xref:System.Linq.Enumerable.Min%2A> per individuare la lunghezza minima. La seconda parte dell'esempio mostra invece una soluzione più lunga che usa la sintassi della query per eseguire la stessa operazione.  
  
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
  
### <a name="remarks"></a>Note  
 L'operatore `=>` ha la stessa priorità dell'operatore di assegnazione (`=`) e si associa all'operando a destra.  
  
 È possibile specificare il tipo di variabile di input in modo esplicito o consentendo al compilatore di dedurlo; in entrambi i casi, la variabile è fortemente tipizzata in fase di compilazione. Quando si specifica un tipo, è necessario racchiudere tra parentesi il nome del tipo e il nome della variabile, come illustrato nell'esempio seguente.  
  
```csharp  
int shortestWordLength = words.Min((string w) => w.Length);  
```  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come scrivere un'espressione lambda per eseguire l'overload dell'operatore query standard <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> che accetta due argomenti. Poiché l'espressione lambda contiene più di un parametro, i parametri devono essere racchiusi tra parentesi. Il secondo parametro, `index`, rappresenta l'indice dell'elemento corrente nella raccolta. L'espressione `Where` restituisce tutte le stringhe la cui lunghezza è minore rispetto alla loro posizione nell'indice nella matrice.  
  
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
## <a name="expression-body-definition"></a>Definizione del corpo dell'espressione

Una definizione del corpo dell'espressione offre l'implementazione di un membro in un modulo molto conciso e leggibile. Contiene la sintassi generale seguente:

```csharp
member => expression;
```
dove *expression* è un'espressione valida. Si noti che *expression* può essere un'*espressione di istruzione* solo se il membro restituito del tipo è `void` o se il membro è un costruttore o un finalizzatore.

Le definizioni del corpo dell'espressione per i metodi e le istruzioni Property Get sono supportate a partire da C# 6. Le definizioni del corpo dell'espressione per costruttori, finalizzatori, istruzioni Property Set e indicizzatori sono supportate a partire da C# 7.

Di seguito è riportata una definizione del corpo dell'espressione per un metodo `Person.ToString`:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

È una versione abbreviata della definizione di metodo seguente:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
Per altre informazioni dettagliate sulle definizioni del corpo dell'espressione, vedere [Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="see-also"></a>Vedere anche  
[Riferimenti per C#](../../../csharp/language-reference/index.md)   
[Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
[Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
[Membri con corpo di espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).
---
title: =&gt; Operatore (Riferimenti per C#)
ms.date: 10/02/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =>_CSharpKeyword
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
# <a name="gt-operator-c-reference"></a>=&gt; Operatore (Riferimenti per C#)

Il `=>` operatore può essere utilizzato in due modi in c#:

- Come il [operatore lambda](#lamba-operator) in un [espressione lambda](../../lambda-expressions.md), separa le variabili di input dal corpo dell'espressione lambda.
 
- In un [Definizione corpo dell'espressione](#expression-body-definition), l'implementazione del membro separa un nome di membro. 

## <a name="lambda-operator"></a>Lambda (operatore)

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

Una definizione di espressioni corpo fornisce l'implementazione di un membro in un formato leggibile, estremamente ridotto. Contiene la sintassi generale seguente:

```csharp
member => expression;
```
dove *expression* è un'espressione valida. Si noti che *espressione* può essere un *espressione di istruzione* solo se il membro restituito del tipo è `void`, o se il membro è un costruttore o un finalizzatore.

Definizioni di espressioni corpo per i metodi e le istruzioni get di proprietà sono supportate a partire da c# 6. Definizioni di espressioni corpo per i costruttori, finalizzatori, istruzioni di set di proprietà e gli indicizzatori sono supportati a partire da C# 7.

Di seguito è una definizione del corpo di espressione per un `Person.ToString` metodo:

```csharp
public override string ToString() => $"{fname} {lname}".Trim();
```

È una versione abbreviata di definizione di metodo seguenti:

```csharp
public override string ToString()
{
   return $"{fname} {lname}".Trim();
}
```
Per ulteriori informazioni sulle definizioni di espressioni corpo, vedere [densi espressione membri](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="see-also"></a>Vedere anche  
[Riferimenti per C#](../../../csharp/language-reference/index.md)   
[Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
[Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
[I membri con corpo espressione](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).
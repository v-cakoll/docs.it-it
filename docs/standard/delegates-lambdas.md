---
title: Delegati e lambda
description: Informazioni sul modo in cui i delegati definiscono un tipo, che specifica una firma del metodo particolare, che può essere chiamato direttamente o passato a un altro metodo e chiamato.
author: richlander
ms.author: wiwagn
ms.date: 06/20/2016
ms.technology: dotnet-standard
ms.assetid: fe2e4b4c-6483-4106-a4b4-a33e2e306591
ms.openlocfilehash: 34bfa4c6007ec771f784e927675f4e24d52e194f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391234"
---
# <a name="delegates-and-lambdas"></a>Delegati e lambda

I delegati definiscono un tipo che specifica una firma di metodo specifica. Un metodo (statico o istanza) che soddisfa questa firma può essere assegnato a una variabile del tipo, quindi chiamato direttamente (con gli argomenti appropriati) o passato come argomento a un altro metodo e quindi chiamato. L'esempio seguente mostra l'uso dei delegati.

```csharp
using System;
using System.Linq;

public class Program
{
    public delegate string Reverse(string s);

    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Reverse rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

* La riga `public delegate string Reverse(string s);` crea un tipo delegato di una determinata firma, in questo caso un metodo che accetta un parametro di stringa e quindi restituisce un parametro di stringa.
* Il metodo `static string ReverseString(string s)`, che ha esattamente la stessa firma del tipo delegato definito, implementa il delegato.
* La riga `Reverse rev = ReverseString;` indica che si può assegnare un metodo a una variabile del tipo di delegato corrispondente.
* La riga `Console.WriteLine(rev("a string"));` illustra come usare una variabile di un tipo delegato per richiamare il delegato.

Per semplificare il processo di sviluppo, .NET include un set di tipi di delegato che i programmatori possono riutilizzare senza dover creare nuovi tipi. I tipi sono `Func<>`, `Action<>` e `Predicate<>` e possono essere usati in posizioni diverse all'interno delle API .NET senza dover definire nuovi tipi di delegato. Le differenze tra i tre tipi sono evidenti nelle firme e riguardano principalmente la modalità di utilizzo prevista:

* `Action<>` viene usato quando è necessario eseguire un'azione usando gli argomenti del delegato. Il metodo che incapsula non restituisce un valore.
* `Func<>` viene in genere usato in presenza di una trasformazione, ovvero quando è necessario trasformare gli argomenti del delegato in un risultato diverso. Le proiezioni sono un esempio tipico. Il metodo che incapsula restituisce un valore specificato.
* `Predicate<>` viene usato quando è necessario determinare se l'argomento soddisfa la condizione del delegato. Può anche essere scritto `Func<T, bool>`come un oggetto , ovvero il metodo restituisce un valore booleano.

L'esempio precedente può essere ora riscritto usando il delegato `Func<>` anziché un tipo personalizzato. Il programma continuerà a essere eseguito nello stesso modo.

```csharp
using System;
using System.Linq;

public class Program
{
    static string ReverseString(string s)
    {
        return new string(s.Reverse().ToArray());
    }

    static void Main(string[] args)
    {
        Func<string, string> rev = ReverseString;

        Console.WriteLine(rev("a string"));
    }
}
```

In questo esempio semplice la presenza di un metodo definito all'esterno del metodo `Main` non è necessaria. Per questa ragione è stato introdotto in .NET Framework 2.0 il concetto di **delegati anonimi**. I delegati anonimi consentono di creare delegati "inline" senza dover specificare tipi o metodi aggiuntivi. Sarà sufficiente incorporare la definizione del delegato dove necessario.

In questo esempio il delegato anonimo viene configurato e usato per visualizzare un elenco dei soli numeri pari che vengono quindi stampati nella console.

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(
          delegate (int no)
          {
              return (no % 2 == 0);
          }
        );

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

È possibile osservare che il corpo del delegato è costituito da un set di espressioni, come qualsiasi altro delegato. Ma anziché essere una definizione separata, il delegato è stato inserito _appositamente_ nella chiamata al metodo <xref:System.Collections.Generic.List%601.FindAll%2A?displayProperty=nameWithType>.

Anche con questo approccio, tuttavia, rimane una parte considerevole di codice che è possibile eliminare. A tale scopo, vengono usate le **espressioni lambda**.

Le espressioni lambda, chiamate anche "lambda", sono state usate per la prima volta in C# 3.0 come uno dei componenti fondamentali di Language Integrated Query (LINQ). Si tratta semplicemente una sintassi più pratica per l'uso dei delegati. Dichiarano una firma e un corpo del metodo, ma non hanno un'identità formale propria, a meno che non siano assegnati a un delegato. A differenza dei delegati, possono essere assegnate direttamente come parte sinistra della registrazione eventi o in diverse clausole e metodi LINQ.

Poiché un'espressione lambda è soltanto un modo diverso di specificare un delegato, è possibile riscrivere l'esempio precedente per usare un'espressione lambda anziché un delegato anonimo.

```csharp
using System;
using System.Collections.Generic;

public class Program
{
    public static void Main(string[] args)
    {
        List<int> list = new List<int>();

        for (int i = 1; i <= 100; i++)
        {
            list.Add(i);
        }

        List<int> result = list.FindAll(i => i % 2 == 0);

        foreach (var item in result)
        {
            Console.WriteLine(item);
        }
    }
}
```

Nell'esempio precedente l'espressione lambda usata è `i => i % 2 == 0`. Anche in questo caso, si tratta soltanto di una sintassi **molto** pratica per l'uso di delegati con un funzionamento simile a quello del delegato anonimo.

Le lambda sono semplicemente delegati, ovvero possono essere usate come gestori di eventi come mostra il frammento di codice seguente.

```csharp
public MainWindow()
{
    InitializeComponent();

    Loaded += (o, e) =>
    {
        this.Title = "Loaded";
    };
}
```

L'operatore `+=` in questo contesto viene usato per eseguire la sottoscrizione a un [evento](../../docs/csharp/language-reference/keywords/event.md). Per ulteriori informazioni, vedere [Come sottoscrivere e annullare la sottoscrizione agli eventi](../../docs/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).

## <a name="further-reading-and-resources"></a>Altre informazioni e risorse

* [Delegati](../../docs/csharp/programming-guide/delegates/index.md)
* [Funzioni anonime](../../docs/csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)
* [Espressioni lambda](../../docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)

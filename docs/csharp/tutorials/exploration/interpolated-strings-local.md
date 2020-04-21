---
title: Interpolazione di stringhe - Esercitazione su C#
description: Questa esercitazione mostra come usare la funzionalità di interpolazione di stringhe di C# per includere risultati di espressioni formattate in una stringa più grande.
ms.date: 10/23/2018
ms.openlocfilehash: 22637895f241585bac4909479f225bf3cb581614
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738276"
---
# <a name="use-string-interpolation-to-construct-formatted-strings"></a>Usare l'interpolazione di stringhe per la costruzione di stringhe formattate

Questa esercitazione descrive come usare l'[interpolazione di stringhe](../../language-reference/tokens/interpolated.md) in C# per inserire i valori in un'unica stringa di risultato. Verranno descritte le procedure per scrivere codice C# e visualizzare i risultati della compilazione ed esecuzione del codice. L'esercitazione contiene una serie di lezioni che descrivono come inserire valori in una stringa e formattare questi valori in modi diversi.

Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo. L'esercitazione di .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Windows, Linux o macOS. È inoltre possibile completare la [versione interattiva](interpolated-strings.yml) di questa esercitazione nel browser.

## <a name="create-an-interpolated-string"></a>Creare una stringa interpolata

Creare una directory denominata *interpolated*. Impostarla come directory corrente ed eseguire il comando seguente da una finestra della console:

```dotnetcli
dotnet new console
```

Questo comando crea una nuova applicazione console .NET Core nella directory corrente.

Aprire *Program.cs* nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con il codice seguente, sostituendo `<name>` con il nome:

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

Per provare questo codice, digitare `dotnet run` nella finestra della console. Quando si esegue il programma viene visualizzata una singola stringa con una formula di benvenuto che include il nome dell'utente. La stringa inclusa nella chiamata del metodo <xref:System.Console.WriteLine%2A> è un'*espressione di stringa interpolata*. Si tratta di un tipo di modello che consente di costruire un'unica stringa detta *stringa di risultato* da una stringa che include codice incorporato. Le stringhe interpolate sono particolarmente utili per inserire valori in una stringa o per concatenare (unire) più stringhe.

Questo semplice esempio contiene i due elementi che devono essere presenti in ogni stringa interpolata:

- Un valore letterale stringa che inizia con il carattere `$` prima delle virgolette inglesi aperte. Tra il simbolo `$` e le virgolette non devono essere presenti spazi. Se si vuole vedere cosa accade se ne viene incluso uno, inserire uno spazio dopo il carattere `$`, salvare il file ed eseguire nuovamente il programma digitando `dotnet run` nella finestra della console. Il compilatore C# visualizza un messaggio di errore "errore CS1056: Carattere '$'" imprevisto).

- Una o più *espressioni di interpolazione*. Un'espressione di interpolazione è indicata da parentesi graffe di apertura e chiusura (`{` e `}`). All'interno delle parentesi graffe è possibile inserire qualsiasi espressione C# che restituisce un valore, incluso `null`.

Ora si proveranno altri esempi di interpolazione di stringhe con altri tipi di dati.

## <a name="include-different-data-types"></a>Includere tipi di dati diversi

Nella sezione precedente è stata usata l'interpolazione di stringhe per inserire una stringa in un'altra. Il risultato di un'espressione di interpolazione può avere tuttavia qualsiasi tipo di dati. Includiamo valori di vari tipi di dati in una stringa interpolata.

Nell'esempio seguente viene definito prima di tutto un tipo di dati [class](../../programming-guide/classes-and-structs/classes.md)`Vegetable` con la `Name` [proprietà](../../properties.md) e un `ToString` [metodo](../../methods.md) che esegue l'[override](../../language-reference/keywords/override.md) del comportamento del metodo <xref:System.Object.ToString?displayProperty=nameWithType>. Il [ `public` modificatore](../../language-reference/keywords/public.md) di accesso rende tale metodo disponibile a `Vegetable` qualsiasi codice client per ottenere la rappresentazione di stringa di un'istanza. Nell'esempio `Vegetable.ToString` il metodo restituisce `Name` il valore della `Vegetable` proprietà inizializzata in corrispondenza del [costruttore](../../programming-guide/classes-and-structs/constructors.md):

```csharp
public Vegetable(string name) => Name = name;
```

Quindi viene creata `Vegetable` un'istanza `item` della classe denominata utilizzando l'operatore [ `new` ](../../language-reference/operators/new-operator.md) e fornendo un nome per il costruttore `Vegetable`:

```csharp
var item = new Vegetable("eggplant");
```

Infine, includere la variabile `item` in una stringa interpolata che contenga anche un valore <xref:System.DateTime>, un valore <xref:System.Decimal> e un valore di  [enumerazione](../../language-reference/builtin-types/enum.md)`Unit`. Sostituire tutto il codice C# in un editor con il codice seguente e usare il comando `dotnet run` per l'eseguirlo:

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;

   public string Name { get; }

   public override string ToString() => Name;
}

public class Program
{
   public enum Unit { item, kilogram, gram, dozen };

   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```

L'espressione di interpolazione `item` nella stringa interpolata restituisce il testo "eggplant" nella stringa del risultato. Questo accade perché, quando il tipo di risultato dell'espressione non è una stringa, il risultato restituisce una stringa nel modo seguente:

- Se l'espressione di interpolazione restituisce `null`, viene usata una stringa vuota ("" o <xref:System.String.Empty?displayProperty=nameWithType>).

- Se l'espressione di interpolazione non restituisce `null`, in genere viene chiamato il metodo `ToString` del tipo di risultato. È possibile testare questo processo aggiornando l'implementazione del metodo `Vegetable.ToString`. Potrebbe anche non essere necessario implementare il metodo `ToString`, poiché ogni tipo prevede un'implementazione di questo metodo. Per il test di questo funzionamento, impostare come commento la definizione del metodo `Vegetable.ToString` nell'esempio (facendola precedere dal simbolo di commento `//`). Nell'output la stringa "eggplant" viene sostituita dal nome completo del tipo ("Vegetable" in questo esempio), ovvero il comportamento predefinito del metodo <xref:System.Object.ToString?displayProperty=nameWithType>. Il comportamento predefinito del metodo `ToString` per un tipo di enumerazione prevede la restituzione della rappresentazione stringa di un valore usato nella definizione dell'enumerazione.

Nell'output di questo esempio la data è troppo precisa (il prezzo delle melanzane non varia ogni secondo) e il valore del prezzo non indica una valuta. Nella sezione successiva si apprenderà come risolvere questi problemi controllando la formattazione delle rappresentazioni di stringa dei risultati delle espressioni.

## <a name="control-the-formatting-of-interpolation-expressions"></a>Controllare la formattazione delle espressioni di interpolazione

Nella sezione precedente sono state inserite nella stringa di risultato due stringhe con formattazione non valida. Uno è un valore di data e ora nel quale solo la data risultava corretta. Il secondo è un prezzo che non indica la valuta. Entrambi i problemi sono di facile risoluzione. L'interpolazione di stringhe consente di specificare *stringhe di formato* che controllano la formattazione di determinati tipi. Modificare la chiamata in `Console.WriteLine` dell'esempio precedente in modo da includere le stringhe di formato per le espressioni di data e prezzo, come indicato nella riga seguente:

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

Per specificare una stringa di formato, aggiungere i due punti (":") e la stringa di formato desiderata dopo l'espressione di interpolazione. "d" è un [stringa di formato data e ora standard](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) che rappresenta il formato di data breve. "C2" è una stringa di [formato numerico standard](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) che rappresenta un numero come valore di valuta con due cifre dopo il separatore decimale.

Molti tipi delle librerie .NET supportano un set predefinito di stringhe di formato. Tali tipi includono tutti i tipi numerici e i tipi data e ora. Per l'elenco completo dei tipi che supportano le stringhe di formato, vedere [Stringhe di formato e tipi della libreria di classe .NET](../../../standard/base-types/formatting-types.md#format-strings-and-net-types) nell'articolo [Formattazione di tipi in .NET](../../../standard/base-types/formatting-types.md).

Provare a modificare le stringhe di formato nell'editor di testo ed eseguire nuovamente il programma ogni volta che si apporta una modifica, per verificare l'effetto delle modifiche sulla formattazione di data, ora e valore numerico. Modificare il valore "d" in `{date:d}` inserendo i valori "t" (per visualizzare il formato ora breve), "y" (per visualizzare anno e mese) e "yyyy" (per visualizzare l'anno come numero a quattro cifre). Modificare "C2" in `{price:C2}` inserendo "e" (per la notazione esponenziale) e "F3" (per un valore numerico con tre cifre dopo il separatore decimale).

Oltre alla formattazione è possibile controllare la larghezza del campo e l'allineamento delle stringhe formattate incluse nella stringa di risultato. La sezione successiva spiega come eseguire questa operazione.

## <a name="control-the-field-width-and-alignment-of-interpolation-expressions"></a>Controllare la larghezza del campo e l'allineamento delle espressioni di interpolazione

In genere quando il risultato di un'espressione di interpolazione è formattato in stringa, questa viene inclusa in una stringa del risultato senza spazi iniziali o finali. In particolare quando si usa un set di dati, la possibilità di controllare la larghezza di un campo e l'allineamento del testo consente di generare un output più leggibile. Per verificare, sostituire tutto il codice nell'editor di testo con il codice seguente e digitare `dotnet run` per eseguire il programma:

```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>()
      {
          ["Doyle, Arthur Conan"] = "Hound of the Baskervilles, The",
          ["London, Jack"] = "Call of the Wild, The",
          ["Shakespeare, William"] = "Tempest, The"
      };

      Console.WriteLine("Author and Title List");
      Console.WriteLine();
      Console.WriteLine($"|{"Author",-25}|{"Title",30}|");
      foreach (var title in titles)
         Console.WriteLine($"|{title.Key,-25}|{title.Value,30}|");
   }
}
```

I nomi degli autori vengono allineati a sinistra e i titoli da loro scritti sono allineati a destra. Per specificare l'allineamento, aggiungere una virgola (",") dopo un'espressione di interpolazione e indicare la larghezza *minima* del campo. Se il valore specificato è un numero positivo, il campo è allineato a destra. Se è un numero negativo, il campo è allineato a sinistra.

Provare a rimuovere il segno negativo dal codice `{"Author",-25}` e `{title.Key,-25}` ed eseguire di nuovo l'esempio, come indicato dal codice seguente:

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

Questa volta le informazioni sull'autore sono allineate a destra.

È possibile combinare un identificatore di allineamento e una stringa di formato per un'unica espressione di interpolazione. A tale scopo, specificare prima l'allineamento, seguito da due punti e dalla stringa di formato. Sostituire tutto il codice nel metodo `Main` con il codice seguente, che consente di visualizzare tre stringhe formattate con le larghezze di campo definite. A questo punto eseguire il programma immettendo il comando `dotnet run`.

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

L'output è simile al seguente:

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

È stata completata l'esercitazione sull'interpolazione di stringhe.

Per altre informazioni, vedere l'argomento [Interpolazione di stringhe](../../language-reference/tokens/interpolated.md) e l'esercitazione [Interpolazione di stringhe in C#](../../tutorials/string-interpolation.md).

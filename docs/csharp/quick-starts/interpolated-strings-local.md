---
title: Esercitazione sulle stringhe interpolate - Guide introduttive locali per C#
description: Questa guida introduttiva sulle stringhe interpolate spiega come scrivere codice C# per includere il risultato di un'espressione in una stringa di dimensioni maggiori.
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: b6089b69eb350fce29f86f19f5abeb44acb4b6b4
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="interpolated-strings"></a>Stringhe interpolate

Questa guida introduttiva illustra come usare le stringhe interpolate in C# per inserire i valori in un'unica stringa di output. Verranno descritte le procedure per scrivere codice C# e visualizzare i risultati della compilazione ed esecuzione del codice. La guida introduttiva include una serie di lezioni che spiegano come inserire i valori nelle stringhe e applicare formattazioni diverse a tali valori.

Questa guida introduttiva richiede un computer da usare per lo sviluppo. L'argomento [Get started with .NET in 10 minutes](https://www.microsoft.com/net/core) (Iniziare a usare .NET in 10 minuti) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Mac, PC o Linux. Una breve panoramica dei comandi usati è disponibile nell'[introduzione alle guide introduttive locali](local-environment.md) che contiene anche collegamenti ad altre informazioni. 

## <a name="create-an-interpolated-string"></a>Creare una stringa interpolata

Creare una directory denominata **interpolated-quickstart**. Impostarla come directory corrente ed eseguire il comando seguente da una finestra della console:

```console
dotnet new console -n interpolated -o .
```

Questo comando crea una nuova applicazione console .NET Core nella directory corrente.

Aprire **Program.cs** nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con il codice seguente, sostituendo `<name>` con il nome:

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
Per provare questo codice, digitare `dotnet run` nella finestra della console. Quando si esegue il programma viene visualizzata un'unica stringa contenente un messaggio di saluto che include il nome dell'utente. La stringa inclusa nella chiamata al metodo <xref:System.Console.WriteLine%2A> è una *stringa interpolata*. Si tratta di un tipo di modello che consente di costruire un'unica stringa detta *stringa di risultato* da una stringa che include codice incorporato. Le stringhe interpolate sono particolarmente utili per inserire valori in una stringa o per concatenare (unire) più stringhe. 
    
Questo semplice esempio contiene i due elementi che devono essere presenti in ogni stringa interpolata: 

- Un valore letterale stringa che inizia con il carattere `$` prima delle virgolette inglesi aperte. Tra il simbolo `$` e le virgolette non devono essere presenti spazi. Se si vuole vedere cosa accade se ne viene incluso uno, inserire uno spazio dopo il carattere `$`, salvare il file ed eseguire nuovamente il programma digitando `dotnet run` nella finestra della console. Il compilatore C# visualizza un messaggio di errore "errore CS1056: Carattere '$'" imprevisto). 

- Una o più *espressioni interpolate*. Un'espressione interpolata è indicata tra parentesi graffe di apertura e chiusura (`{` e `}`). All'interno delle parentesi graffe è possibile inserire qualsiasi espressione C# che restituisce un valore, incluso `null`. 

Ora si proveranno altri esempi di stringhe interpolate con altri tipi di dati.
    
## <a name="include-different-data-types"></a>Includere tipi di dati diversi

Nella sezione precedente è stata usata una stringa interpolata per inserire una stringa in un'altra stringa. Un'espressione di stringa interpolata può avere qualsiasi tipo di dati. Considerare ad esempio una stringa interpolata con valori di tipi di dati diversi. 
    
L'esempio seguente include espressioni interpolate con un oggetto `Vegetable`, un membro dell'enumerazione `Unit`, un valore <xref:System.DateTime> e un valore <xref:System.Decimal>. Sostituire tutto il codice C# in un editor con il codice seguente e usare il comando `console run` per l'eseguirlo:

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Example
{
   public enum Unit { item, pound, ounce, dozen };
   
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
    
Si noti che la seconda espressione interpolata include l'oggetto `item` nella stringa di risultato visualizzata nella console e che in questo caso nella stringa di risultato viene inserita la stringa "eggplant" (melanzana). Questo si verifica perché quando un'espressione interpolata non è di tipo stringa, il compilatore C# esegue le operazioni seguenti:

- Se l'espressione interpolata è `null`, restituisce una stringa vuota ("" o <xref:System.String.Empty?displayProperty=nameWithType>).

- Se l'espressione interpolata non è `null`, viene chiamato il metodo `ToString` del tipo dell'espressione interpolata. Per il test di questo funzionamento impostare come commento la definizione del metodo `Vegetable.ToString` dell'esempio facendola precedere da un simbolo di commento (`//`). Nell'output la stringa "eggplant" (melanzana) viene sostituita dal nome del tipo "Vegetable" (verdura), ovvero il comportamento predefinito del metodo <xref:System.Object.ToString?displayProperty=nameWithType>.   

Nell'output di questo esempio la data è troppo precisa (il prezzo delle melanzane non varia ogni secondo) e il valore del prezzo non indica una valuta. Nel sezione successiva si apprenderà come risolvere questi problemi controllando la formattazione delle stringhe restituite dalle espressioni interpolate.

## <a name="control-the-formatting-of-interpolated-expressions"></a>Controllare la formattazione delle espressioni interpolate

Nella sezione precedente sono state inserite nella stringa di risultato due stringhe con formattazione non valida. Il primo problema è un valore di data e ora nel quale solo la data risultava corretta. Il secondo è un prezzo che non indicava la valuta. Entrambi i problemi sono di facile risoluzione. Le espressioni interpolate possono includere *stringhe di formato* che controllano la formattazione di determinati tipi di dati. Modificare la chiamata a `Console.WriteLine` dell'esempio precedente in modo da includere l'identificatore di formato per i campi data e prezzo, come indicato nella riga seguente:

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
Per specificare una stringa di formato, far seguire all'espressione interpolata i due punti e la stringa di formato desiderata. "d" è un [stringa di formato data e ora standard](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) che rappresenta il formato di data breve. "C2" è un [stringa di formato numerico standard](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) che rappresenta un numero come valore di valuta con due cifre dopo il separatore decimale.

Molti tipi delle librerie .NET Standard supportano un set predefinito di stringhe di formato. Tali tipi includono tutti i tipi numerici e i tipi data e ora. Per l'elenco completo dei tipi che supportano le stringhe di formato, vedere [Stringhe di formato e tipi della libreria di classe .NET](../../standard/base-types/formatting-types.md#stringRef) nell'articolo [Formattazione di tipi in .NET](../../standard/base-types/formatting-types.md). Qualsiasi tipo può supportare un set di stringhe di formato. È anche possibile sviluppare estensioni di formattazione personalizzata per aggiungere una formattazione personalizzata ai tipi esistenti. Per informazioni sulla formattazione personalizzata con un'implementazione <xref:System.ICustomFormatter>, vedere [Formattazione personalizzata con ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) nell'articolo [Formattazione di tipi in .NET](../../standard/base-types/formatting-types.md).

Provare a modificare le stringhe di formato nell'editor di testo ed eseguire nuovamente il programma ogni volta che si apporta una modifica, per verificare l'effetto delle modifiche sulla formattazione di data, ora e valore numerico. Modificare il valore "d" in `{date:d}` inserendo i valori "t" (per visualizzare il formato ora breve), "y" (per visualizzare anno e mese) e "yyyy" (per visualizzare l'anno come numero a quattro cifre). Modificare "C2" in `{price:C2}` inserendo "e" (per la notazione esponenziale) e "F3" (per un valore numerico con tre cifre dopo il separatore decimale).

Oltre alla formattazione è possibile controllare la larghezza del campo e l'allineamento delle stringhe restituite da un'espressione interpolata. La sezione successiva spiega come eseguire questa operazione.

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a>Controllare la larghezza del campo e l'allineamento delle espressioni interpolate

In genere quando la stringa restituita da un'espressione interpolata è inclusa in una stringa di risultato non ha spazi iniziali o finali. Specie nelle istanze in cui si lavora con un set di dati, le espressioni interpolate consentono di specificare la larghezza e l'allineamento di un campo. Per verificare, sostituire tutto il codice nell'editor di testo con il codice seguente e digitare `console run` per eseguire il programma:
    
```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>();
      titles.Add("Doyle, Arthur Conan", "Hound of the Baskervilles, The");
      titles.Add("London, Jack", "Call of the Wild, The");
      titles.Add("Shakespeare, William", "Tempest, The");

      Console.WriteLine("Author and Title List");
      Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
      foreach (var title in titles)
         Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
   }
}
```
    
I nomi degli autori vengono allineati a sinistra e i titoli da loro scritti sono allineati a destra. Per specificare l'allineamento aggiungere una virgola (",") dopo l'espressione e quindi indicare la larghezza del campo. Se la larghezza del campo è un numero positivo, il campo è allineato a destra:

```text
{expression, width}
```

Se la larghezza del campo è un numero negativo, il campo è allineato a sinistra:

```text
{expression, -width}
```

Provare a rimuovere il segno negativo dalle espressioni interpolate `{"Author",-25}` e `{title.Key,-25}` ed eseguire di nuovo l'esempio, come indicato dal codice seguente:

```csharp
Console.WriteLine($"\n{"Author",25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,25}     {title.Value,30}");
```

Questa volta le informazioni sull'autore sono allineate a destra.

È possibile combinare una larghezza di campo e una stringa di formato in un'unica espressione interpolata. Immettere prima la larghezza del campo, seguita dai due punti e dalla stringa di formato. Sostituire tutto il codice nel metodo `Main` con il codice seguente, che consente di visualizzare tre stringhe formattate con le larghezze di campo definite. A questo punto eseguire il programma immettendo il comando `dotnet run`.

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
L'output è simile al seguente:

```console
1/11/2018            Hour 09                1,063.34 feet
```

È stata completata la guida introduttiva sulle stringhe interpolate. 
    
È possibile continuare con la guida introduttiva [Matrici e raccolte](arrays-and-collections.md) nel proprio ambiente di sviluppo.

Per altre informazioni sull'uso delle stringhe interpolate, vedere l'argomento [Stringhe interpolate](../language-reference/keywords/interpolated-strings.md) nei Riferimenti per C#.


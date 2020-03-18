---
title: Usare raccolte - Esercitazione introduttiva su C#
description: Imparare a usare C# esplorando la raccolta List in questa esercitazione.
ms.date: 10/13/2017
ms.custom: mvc
ms.openlocfilehash: 25d20de2eae8ad1f544fa17553c173a6141ae464
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156689"
---
# <a name="learn-to-manage-data-collections-using-the-generic-list-type"></a>Informazioni su come gestire le raccolte dati tramite il tipo di elenco generico

Questa esercitazione introduttiva offre un'introduzione al linguaggio C# e i concetti di base relativi alla classe <xref:System.Collections.Generic.List%601>.

Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo. L'esercitazione di .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene istruzioni per la configurazione dell'ambiente di sviluppo locale in Windows, Linux o macOS. Una breve panoramica dei comandi usati è disponibile in [Acquisire familiarità con gli strumenti di sviluppo](local-environment.md), che contiene collegamenti a informazioni più dettagliate.

## <a name="a-basic-list-example"></a>Esempio di elenco di base

Creare una directory denominata *list-tutorial*. Impostarla come directory corrente ed eseguire `dotnet new console`.

Aprire *Program.cs* nell'editor preferito e sostituire il codice esistente con il seguente:

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

Sostituire `<name>` con il proprio nome. Salvare *Program.cs*. Digitare `dotnet run` nella finestra della console per provare il codice.

Questo codice consente di creare un elenco di stringhe, aggiungere tre nomi all'elenco e stampare i nomi in lettere maiuscole. Vengono usati i concetti appresi nelle esercitazioni precedenti per eseguire il ciclo dell'elenco.

Il codice per visualizzare i nomi usa la funzionalità di [interpolazione di stringhe](../../language-reference/tokens/interpolated.md).  Anteponendo il carattere `$` a `string`, è possibile incorporare il codice C# nella dichiarazione della stringa. La stringa effettiva sostituisce il codice C# con il valore generato. In questo esempio, `{name.ToUpper()}` viene sostituito con ogni nome, convertito in lettere maiuscole, perché è stato chiamato il metodo <xref:System.String.ToUpper%2A>.

L'esplorazione continua nelle prossime lezioni.

## <a name="modify-list-contents"></a>Modificare il contenuto dell'elenco

La raccolta creata usa il tipo <xref:System.Collections.Generic.List%601>. Questo tipo archivia sequenze di elementi. Il tipo degli elementi viene specificato tra parentesi uncinate.

Un aspetto importante di questo tipo di <xref:System.Collections.Generic.List%601> è che supporta estensioni o riduzioni, consentendo l'aggiunta o la rimozione di elementi. Aggiungere questo codice prima della parentesi `}` di chiusura nel metodo `Main`:

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Sono stati aggiunti altri due nomi alla fine dell'elenco e ne è stato anche rimosso uno. Salvare il file e digitare `dotnet run` per provare il codice.

<xref:System.Collections.Generic.List%601> consente di fare riferimento a singoli elementi anche in base all'**indice**. Inserire l'indice tra i token `[` e `]` dopo il nome dell'elenco. C# usa il valore 0 per il primo indice. Aggiungere questo codice direttamente sotto il codice appena aggiunto e provarlo:

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

Non è possibile accedere a un indice oltre la fine dell'elenco. Tenere presente che gli indici iniziano da 0, pertanto l'indice massimo valido è minore di un'unità rispetto al numero di elementi nell'elenco. È possibile controllare la lunghezza dell'elenco tramite la proprietà <xref:System.Collections.Generic.List%601.Count%2A>. Aggiungere il codice seguente alla fine del metodo Main:

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

Salvare il file e digitare di nuovo `dotnet run` per visualizzare i risultati.

## <a name="search-and-sort-lists"></a>Eseguire ricerche negli elenchi e ordinarli

In questi esempi vengono usati elenchi relativamente piccoli, ma le applicazioni reali creano spesso elenchi con molti più elementi, a volte anche migliaia. Per trovare elementi in raccolte di tali dimensioni, è necessario avere la possibilità di eseguire ricerche nell'elenco. Il metodo <xref:System.Collections.Generic.List%601.IndexOf%2A> cerca un elemento e ne restituisce l'indice. Aggiungere questo codice in fondo al metodo `Main`:

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
}
else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");

}
```

Gli elementi in un elenco possono anche essere ordinati. Il metodo <xref:System.Collections.Generic.List%601.Sort%2A> ordina tutti gli elementi nell'elenco in base all'ordine normale (alfabetico nel caso delle stringhe). Aggiungere questo codice in fondo al metodo `Main`:

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Salvare il file e digitare `dotnet run` per provare quest'ultima versione.

Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato. In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio. Rinominare il metodo `Main` in `WorkingWithStrings` e scrivere un nuovo metodo `Main` che chiama `WorkingWithStrings`. Al termine, il codice dovrebbe risultare simile al seguente:

```csharp
using System;
using System.Collections.Generic;

namespace list_tutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");
            }

            index = names.IndexOf("Not Found");
            if (index == -1)
            {
                Console.WriteLine($"When an item is not found, IndexOf returns {index}");
            }
            else
            {
                Console.WriteLine($"The name {names[index]} is at index {index}");

            }

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a>Elenchi di altri tipi

Finora è stato usato il tipo `string` negli elenchi. Di seguito verrà creato un <xref:System.Collections.Generic.List%601> con un tipo diverso. Per iniziare, creare un set di numeri.

Aggiungere il codice seguente alla fine del nuovo metodo `Main`:

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

Questo codice crea un elenco di interi e imposta i primi due interi sul valore 1. Questi sono i primi due valori di una *successione di Fibonacci*, ovvero una sequenza di numeri. Ogni numero della successione di Fibonacci viene ottenuto dalla somma dei due numeri precedenti. Aggiungere questo codice:

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach (var item in fibonacciNumbers)
    Console.WriteLine(item);
```

Salvare il file e digitare `dotnet run` per visualizzare i risultati.

> [!TIP]
> Per concentrarsi solo su questa sezione, è possibile impostare come commento il codice che chiama `WorkingWithStrings();`. Inserire due caratteri `/` prima della chiamata come di seguito: `// WorkingWithStrings();`.

## <a name="challenge"></a>Esercizio

È il momento di scoprire se è possibile mettere in pratica alcuni dei concetti appresi in questa lezione e in quelle precedenti. Applicare i concetti appresi finora in relazione ai numeri di Fibonacci. Provare a scrivere il codice per generare i primi 20 numeri nella successione. Tenere presente che il 20° numero di Fibonacci è 6765.

## <a name="complete-challenge"></a>Completare l'esercizio

È possibile visualizzare una soluzione di esempio [esaminando il codice di esempio completato su GitHub](https://github.com/dotnet/samples/tree/master/csharp/list-quickstart/Program.cs#L13-L23).

A ogni iterazione del ciclo, gli ultimi due interi nell'elenco vengono sommati e il valore risultante viene aggiunto all'elenco. Il ciclo viene ripetuto fino ad aggiungere 20 elementi all'elenco.

Complimenti, è stata completata questa esercitazione dedicata agli elenchi. È possibile continuare con l'esercitazione [Introduzione alle classi](introduction-to-classes.md) nell'ambiente di sviluppo.

Altre informazioni sull'uso del tipo `List` sono disponibili nell'argomento della [Guida di .NET](../../../standard/index.md) dedicato alle [raccolte](../../../standard/collections/index.md). Questo argomento include anche informazioni su molti altri tipi di raccolta.

---
title: Guida introduttiva - numeri in c# - c#
description: "Informazioni su c# esaminando i metodi, le proprietà e i tipi numerici."
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 821cca4ea6d6148410e9b179f05d5b74c4844628
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2017
---
# <a name="numbers-in-c-quick-start"></a>Numeri di avvio rapido di c# #

Questa Guida introduttiva illustra sui tipi di numero in c# in modo interattivo. Si scriveranno piccole quantità di codice, quindi verrà compilare ed eseguire il codice. La Guida introduttiva contiene una serie di lezioni progettate per esplorare i numeri e operazioni matematiche in c#. Queste lezioni presentano le nozioni fondamentali del linguaggio C#.

Questa Guida introduttiva prevede di disporre di un computer in cui che è possibile utilizzare per lo sviluppo. L'argomento .NET [Introduzione a 10 minuti](https://www.microsoft.com/net/core) con le istruzioni per configurare l'ambiente di sviluppo locale in Mac, Linux o PC.

## <a name="explore-integer-math"></a>Esplorare le operazioni matematiche su interi

Creare una directory denominata **numeri quickstart**. Impostarla come directory corrente ed eseguire `dotnet new console -n NumbersInCSharp -o .`.

Aprire **Program.cs** nel proprio editor preferito e sostituire la riga `Console.Writeline("Hello World!");` con quanto segue:

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

Eseguire questo codice digitando `dotnet run` nella finestra di comando. 

Questa è una delle operazioni matematiche fondamentali su interi. Il tipo `int` rappresenta un **intero**, ovvero un numero intero positivo o negativo. Per l'addizione si usa il simbolo `+`. Altre operazioni matematiche comuni per gli interi includono:

- `-` per la sottrazione
- `*` per la moltiplicazione
- `/` per la divisione

Per iniziare, esplorare le diverse operazioni. Aggiungere queste righe dopo la riga che scrive il valore del `c`:

```csharp
c = a - b;
Console.WriteLine(c);
c = a * b;
Console.WriteLine(c);
c = a / b;
Console.WriteLine(c);
```

Eseguire questo codice digitando `dotnet run` nella finestra di comando. 
    
È anche possibile sperimentare eseguendo più operazioni matematiche nella stessa riga. Provare a `c = a + b - 12 * 17;` , ad esempio. La combinazione di variabili e i numeri di costanti è consentita.

> [!TIP]
> Mentre si impara a usare C# (o qualsiasi linguaggio di programmazione) sicuramente si commetteranno errori durante la scrittura del codice. Il **compilatore** troverà questi errori e li segnalerà. Quando l'output contiene i messaggi di errore, esaminare attentamente il codice di esempio e il codice nella finestra per visualizzare gli elementi da correggere.
> Questo esercizio sarà utile per imparare la struttura del codice C#.     

Il primo passaggio per volta. Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato. In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio. Rinominare il metodo `Main` in `WorkingWithIntegers` e scrivere un nuovo metodo `Main` che chiama `WorkingWithIntegers`. Al termine, il codice dovrebbe risultare simile al seguente:

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();
        }
    }
}
```

## <a name="explore-order-of-operations"></a>Esplorare l'ordine delle operazioni

Commentare la chiamata a `WorkingWithIntegers()`. L'output che meno pieno di informazioni mentre si lavora in questa sezione sarà:

```csharp
//WorkingWithIntegers();
```

Il `//` avvia un **commento** in c#. I commenti sono qualsiasi testo che si desidera mantenere nel codice sorgente, ma non è stato eseguito come codice. Il compilatore non genera codice eseguibile da commenti.

Il linguaggio C# stabilisce un ordine di precedenza per le diverse operazioni matematiche, con regole coerenti con quelle della matematica.
La moltiplicazione e la divisione hanno la precedenza rispetto ad addizione e sottrazione.
Esplorare che aggiungendo il codice seguente per il `Main` metodo ed execuing `dotnet run`:

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

L'output dimostra che la moltiplicazione viene eseguita prima dell'addizione.

È possibile forzare un ordine diverso dell'operazione mediante l'aggiunta di parentesi per racchiudere l'operazione o le operazioni eseguite per prime. Aggiungere le seguenti righe ed eseguire di nuovo:

```csharp
d = (a  + b) * c;
Console.WriteLine(d);
```

Sperimentare ulteriormente combinando molte operazioni diverse. Aggiungi le seguenti righe in fondo il `Main` metodo. Provare a `dotnet run` nuovamente.

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

È possibile che si sia notato un comportamento interessante per gli interi. Divisione di interi sempre produce un risultato intero, anche quando ci si aspetta il risultato per includere una parte decimale o frazionaria.

Che significa che il problema, provare il codice seguente alla fine del `Main` metodo:

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e  + f) / g;
Console.WriteLine(h);
```

Tipo `dotnet run` nuovamente per visualizzare i risultati.

Prima di continuare, è opportuno tutto il codice è stato scritto in questa sezione e inserirlo in un nuovo metodo. Chiamare il metodo nuovo `OrderPrecedence`.
Al termine con qualcosa di simile al seguente:

```csharp
using System;

namespace NumbersInCSharp
{
    class Program
    {
        static void WorkingWithIntegers()
        {
            int a = 18;
            int b = 6;
            int c = a + b;
            Console.WriteLine(c);
            c = a - b;
            Console.WriteLine(c);
            c = a * b;
            Console.WriteLine(c);
            c = a / b;
            Console.WriteLine(c);
        }

        static void OrderPrecedence()
        {   
            int a = 5;
            int b = 4;
            int c = 2;
            int d = a + b * c;
            Console.WriteLine(d);

            d = (a  + b) * c;
            Console.WriteLine(d);

            d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
            Console.WriteLine(d);

            int e = 7;
            int f = 4;
            int g = 3;
            int h = (e  + f) / g;
            Console.WriteLine(h);
        }

        static void Main(string[] args)
        {
            WorkingWithIntegers();

            OrderPrecedence();

        }
    }
}
```

## <a name="explore-integer-precision-and-limits"></a>Esplorare la precisione e i limiti delle operazioni su interi
L'ultimo esempio dimostra che la divisione di interi tronca il risultato.
È possibile ottenere il **resto** utilizzando il **modulo** (operatore), il `%` carattere. Provare il codice seguente nel `Main` metodo:

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a  + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

Il tipo integer in C# è diverso dagli interi matematici per un altro aspetto, ovvero per il tipo `int` esistono limiti minimi e massimi. Aggiungere questo codice per il `Main` metodo per visualizzare tali limiti:
    
```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

Se un calcolo produce un valore che supera questi limiti, si genera una condizione di **underflow** o **overflow**. La risposta sembra proseguire da un limite all'altro. Aggiungere queste due righe per il `Main` metodo per vedere un esempio:

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```
    
Si noti che la risposta è molto vicina all'intero minimo (negativo). È uguale a `min + 2`. L'operazione di addizione **ha causato l'overflow** dei valori consentiti per gli interi.
La risposta è un numero negativo molto grande, poiché un overflow "ritorna a capo" proseguendo dal valore intero più grande possibile a quello più piccolo.

Esistono altri tipi numerici con limiti e precisione diversi che è possibile usare quando il tipo `int` non soddisfa le proprie esigenze. Questi tipi verranno presentati nelle prossime lezioni.

In questo caso, si sposta il codice che scritto in questa sezione in un metodo separato. Assegnargli il nome `TestLimits`. 

## <a name="work-with-the-double-type"></a>Usare il tipo double

Il tipo numerico `double` rappresenta un numero a virgola mobile a precisione doppia. Questi termini potrebbero risultare sconosciuti. Oggetto **a virgola mobile** è utile per rappresentare i numeri non integrale che possono essere molto grandi o piccole in termini di grandezza. Il termine **precisione doppia** indica che questi numeri vengono archiviati con una maggiore precisione rispetto alla **precisione singola**. Nei computer moderni è più comune usare i numeri a precisione doppia rispetto ai numeri a precisione singola.
Per iniziare a esplorare questo tipo, Aggiungere il codice seguente e visualizzare i risultati:

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a  + b) / c;
Console.WriteLine(d);
```

Si noti che la risposta include la parte decimale del quoziente. Provare ora un'espressione leggermente più complessa con valori double:

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e  + f) / g;
Console.WriteLine(h);
```

L'intervallo di un valore double è molto maggiore rispetto ai valori integer. Provare a ciò che è stato scritto fino a questo punto il seguente codice:

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

Questi valori vengono stampati nella notazione scientifica. A sinistra del numero di `E` è il separatore. Il numero a destra è l'esponente, come potenza di 10. 

Come per i numeri decimali in matematica, i valori double in C# possono presentare errori di arrotondamento. Provare questo codice:

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

Si sa che `0.3` periodico non è esattamente identico a `1/3`.

***Esercizio***

Provare altri calcoli con numeri grandi, numeri piccoli, moltiplicazione e divisione usando il tipo `double`.  Provare calcoli più complessi.

Dopo che è stato speso del tempo con la richiesta di verifica, eseguire il codice è stato scritto e inserirle in un nuovo metodo. Nome di questo nuovo metodo `WorkWithDoubles`.

## <a name="work-with-fixed-point-types"></a>Usare i tipi a virgola fissa

Sono già stati presentati i tipi numerici di base in C#, ovvero integer e double.  C'è un altro tipo da conoscere, ovvero `decimal`. Il `decimal` tipo dispone di un intervallo più piccolo ma maggiore precisione `double`. Il termine **virgola fissa** significa che il separatore decimale (o punto binario) non si sposta. Esaminare il codice seguente:

```csharp
decimal min = decimal.MinValue;
decimal max = decimal.MaxValue;
Console.WriteLine($"The range of the decimal type is {min} to {max}");
```

Si noti che l'intervallo è minore rispetto al tipo `double`. Per vedere la maggiore precisione del tipo decimal, provare il codice seguente:

```csharp
double a = 1.0;
double b = 3.0;
Console.WriteLine(a / b);

decimal c = 1.0M;
decimal d = 3.0M;
Console.WriteLine(c / d);
```

Il suffisso `M` nei numeri è il modo in cui si indica che una costante deve usare il tipo `decimal`.

Si noti che le operazioni matematiche con il tipo decimal includono più cifre a destra del separatore decimale. 

***Esercizio***

Dopo aver esaminato i diversi tipi numerici, scrivere codice che calcola l'area di un cerchio con raggio di 6 cm. Ricordarsi che l'area di un cerchio si calcola moltiplicando il quadrato del raggio per Pi greco. Suggerimento: c# contiene una costante di pi greco, <xref:System.Math.PI?displayProperty=nameWithType> che è possibile utilizzare per quel valore. 

È possibile controllare la risposta da [esaminando il codice di esempio completata su GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/numbers-quickstart/Program.cs#L104-L106)

Se si desidera, provare alcune altre formule. 

È stata completata la "i numeri in c#" Guida introduttiva. È possibile continuare con la [cicli e diramazioni](branches-and-loops-local.md) avvio rapido nel proprio ambiente di sviluppo.

Negli argomenti seguenti sono disponibili ulteriori informazioni sui numeri in C#:

[Tabella dei tipi integrali](../language-reference/keywords/integral-types-table.md)   
[Tabella dei tipi a virgola mobile](../language-reference/keywords/floating-point-types-table.md)   
[Tabella dei tipi predefiniti](../language-reference/keywords/built-in-types-table.md)   
[Tabella delle conversioni numeriche implicite](../language-reference/keywords/implicit-numeric-conversions-table.md)   
[Tabella delle conversioni numeriche esplicite](../language-reference/keywords/explicit-numeric-conversions-table.md)


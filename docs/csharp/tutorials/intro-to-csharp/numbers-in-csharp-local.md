---
title: Numeri in C# - Esercitazione introduttiva su C#
description: Vengono illustrati i tipi numerici, con le proprietà e i metodi, in C#.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: 7537bb597665461021946a792e342149f29c0e95
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75694660"
---
# <a name="manipulate-integral-and-floating-point-numbers-in-c"></a>Modificare numeri a virgola mobile e integrali in C\#

Questa esercitazione presenta in modo interattivo i tipi numerici in C#. Si scriveranno piccole quantità di codice, quindi si compilerà ed eseguirà tale codice. L'esercitazione contiene una serie di lezioni che esplorano numeri e operazioni matematiche in C#. Queste lezioni presentano le nozioni fondamentali del linguaggio C#.

Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo. L'esercitazione .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene le istruzioni per configurare l'ambiente di sviluppo locale in Windows, Linux o MacOS. Una breve panoramica dei comandi usati è disponibile in [Acquisire familiarità con gli strumenti di sviluppo](local-environment.md), che contiene collegamenti a informazioni più dettagliate.

## <a name="explore-integer-math"></a>Esplorare le operazioni matematiche su interi

Creare una directory denominata *numbers-quickstart*. Rendere la directory corrente ed eseguire il comando seguente:

```dotnetcli
dotnet new console -n NumbersInCSharp -o .
```

Aprire *Program.cs* nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con quanto segue:

```csharp
int a = 18;
int b = 6;
int c = a + b;
Console.WriteLine(c);
```

Eseguire questo codice digitando `dotnet run` nella finestra di comando.

Questa è una delle operazioni matematiche fondamentali su interi. Il tipo di `int` rappresenta un **intero**, un numero intero zero, positivo o negativo. Per l'addizione si usa il simbolo `+`. Altre operazioni matematiche comuni per gli interi includono:

- `-` per la sottrazione
- `*` per la moltiplicazione
- `/` per la divisione

Per iniziare, esplorare le diverse operazioni. Aggiungere queste righe dopo quella indicante il valore di `c`:

```csharp

// subtraction
c = a - b;
Console.WriteLine(c);

// multiplication
c = a * b;
Console.WriteLine(c);

// division
c = a / b;
Console.WriteLine(c);
```

Eseguire questo codice digitando `dotnet run` nella finestra di comando.

È anche possibile sperimentare eseguendo più operazioni matematiche nella stessa riga. Provare, esempio, `c = a + b - 12 * 17;`. È consentita la combinazione di variabili e numeri costanti.

> [!TIP]
> Mentre si impara a usare C# (o qualsiasi linguaggio di programmazione) sicuramente si commetteranno errori durante la scrittura del codice. Il **compilatore** troverà questi errori e li segnalerà. Quando l'output contiene messaggi di errore, esaminare attentamente il codice di esempio e il codice nella finestra per scoprire che cosa correggere.
> Questo esercizio sarà utile per imparare la struttura del codice C#.

Il primo passaggio è stato completato. Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato. In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio. Rinominare il metodo `Main` in `WorkingWithIntegers` e scrivere un nuovo metodo `Main` che chiama `WorkingWithIntegers`. Al termine, il codice dovrebbe essere simile al seguente:

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
            
            // addition
            int c = a + b;
            Console.WriteLine(c);
            
            // subtraction
            c = a - b;
            Console.WriteLine(c);
            
            // multiplication
            c = a * b;
            Console.WriteLine(c);
            
            // division
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

Impostare come commento la chiamata a `WorkingWithIntegers()`. L'output risulterà in questo modo meno disordinato quando si usa questa sezione:

```csharp
//WorkingWithIntegers();
```

`//` avvia un **commento** in C#. Un commento è un testo che si vuole conservare nel codice sorgente senza eseguirlo come codice. Il compilatore non genera codici eseguibili da commenti.

Il linguaggio C# stabilisce un ordine di precedenza per le diverse operazioni matematiche, con regole coerenti con quelle della matematica.
La moltiplicazione e la divisione hanno la precedenza rispetto ad addizione e sottrazione.
Per esplorare questo comportamento, è possibile aggiungere il codice seguente al metodo `Main` ed eseguire `dotnet run`:

```csharp
int a = 5;
int b = 4;
int c = 2;
int d = a + b * c;
Console.WriteLine(d);
 ```

L'output dimostra che la moltiplicazione viene eseguita prima dell'addizione.

È possibile forzare un ordine diverso per le operazioni racchiudendo tra parentesi l'operazione o le operazioni che si vuole eseguire per prime. Aggiungere le righe seguenti e ripetere l'esecuzione:

```csharp
d = (a + b) * c;
Console.WriteLine(d);
```

Sperimentare ulteriormente combinando molte operazioni diverse. Aggiungere righe simili alle seguenti in fondo al metodo `Main`. Provare di nuovo `dotnet run`.

```csharp
d = (a + b) - 6 * c + (12 * 4) / 3 + 12;
Console.WriteLine(d);
```

È possibile che si sia notato un comportamento interessante per gli interi. La divisione di interi genera sempre un risultato intero, anche quando ci si aspetta che il risultato includa una parte decimale o frazionaria.

Se questo comportamento non è stato notato, provare il codice seguente alla fine del metodo `Main`:

```csharp
int e = 7;
int f = 4;
int g = 3;
int h = (e + f) / g;
Console.WriteLine(h);
```

Digitare di nuovo `dotnet run` per visualizzare i risultati.

Prima di continuare, tutto il codice scritto in questa sezione verrà inserito in un nuovo metodo. Chiamare il nuovo metodo `OrderPrecedence`.
Si otterranno risultati simili a questi:

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
            
            // addition
            int c = a + b;
            Console.WriteLine(c);
            
            // subtraction
            c = a - b;
            Console.WriteLine(c);
            
            // multiplication
            c = a * b;
            Console.WriteLine(c);
            
            // division
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

            d = (a + b) * c;
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
È possibile ottenere il **resto** usando l'operatore **modulo**, ovvero il carattere `%`. Provare il codice seguente nel metodo `Main`:

```csharp
int a = 7;
int b = 4;
int c = 3;
int d = (a + b) / c;
int e = (a + b) % c;
Console.WriteLine($"quotient: {d}");
Console.WriteLine($"remainder: {e}");
```

Il tipo integer in C# è diverso dagli interi matematici per un altro aspetto, ovvero per il tipo `int` esistono limiti minimi e massimi. Aggiungere questo codice al metodo `Main` per visualizzare tali limiti:

```csharp
int max = int.MaxValue;
int min = int.MinValue;
Console.WriteLine($"The range of integers is {min} to {max}");
```

Se un calcolo produce un valore che supera questi limiti, si genera una condizione di **underflow** o **overflow**. La risposta sembra proseguire da un limite all'altro. Aggiungere queste due righe al metodo `Main` per visualizzare un esempio:

```csharp
int what = max + 3;
Console.WriteLine($"An example of overflow: {what}");
```

Si noti che la risposta è molto vicina all'intero minimo (negativo). È uguale a `min + 2`.
L'operazione di addizione **ha causato l'overflow** dei valori consentiti per gli interi.
La risposta è un numero negativo molto grande, poiché un overflow "ritorna a capo" proseguendo dal valore intero più grande possibile a quello più piccolo.

Esistono altri tipi numerici con limiti e precisione diversi che è possibile usare quando il tipo `int` non soddisfa le proprie esigenze. Questi tipi verranno presentati nelle prossime lezioni.

Ancora una volta il codice scritto in questa sezione verrà spostato in un metodo separato. Assegnargli il nome `TestLimits`.

## <a name="work-with-the-double-type"></a>Usare il tipo double

Il tipo numerico `double` rappresenta un numero a virgola mobile a precisione doppia. Questi termini potrebbero risultare sconosciuti. Un numero **a virgola mobile** è utile per rappresentare numeri non integrali, con ordine di grandezza molto grande o molto piccolo. Il termine **precisione doppia** indica che questi numeri vengono archiviati con una maggiore precisione rispetto alla **precisione singola**. Nei computer moderni è più comune usare i numeri a precisione doppia rispetto ai numeri a precisione singola.
Per iniziare a esplorare questo tipo, Aggiungere il codice seguente e visualizzare il risultato:

```csharp
double a = 5;
double b = 4;
double c = 2;
double d = (a + b) / c;
Console.WriteLine(d);
```

Si noti che la risposta include la parte decimale del quoziente. Provare ora un'espressione leggermente più complessa con valori double:

```csharp
double e = 19;
double f = 23;
double g = 8;
double h = (e + f) / g;
Console.WriteLine(h);
```

L'intervallo di un valore double è molto maggiore rispetto ai valori integer. Provare il codice seguente sotto il codice già scritto finora:

```csharp
double max = double.MaxValue;
double min = double.MinValue;
Console.WriteLine($"The range of double is {min} to {max}");
```

Questi valori vengono stampati con la notazione scientifica. Il numero a sinistra di `E` rappresenta il significando. Il numero a destra è l'esponente, come potenza di 10.

Come per i numeri decimali in matematica, i valori double in C# possono presentare errori di arrotondamento. Provare questo codice:

```csharp
double third = 1.0 / 3.0;
Console.WriteLine(third);
```

Si sa che `0.3` periodico non è esattamente identico a `1/3`.

***Esercizio***

Provare altri calcoli con numeri grandi, numeri piccoli, moltiplicazione e divisione usando il tipo `double`. Provare calcoli più complessi.

Dopo avere dedicato un po' di tempo all'esercizio, inserire il codice scritto in un nuovo metodo. Denominare il nuovo metodo `WorkWithDoubles`.

## <a name="work-with-fixed-point-types"></a>Usare i tipi a virgola fissa

Sono già stati presentati i tipi numerici di base in C#, ovvero integer e double.  C'è un altro tipo da conoscere, ovvero `decimal`. Il tipo `decimal` ha un intervallo più piccolo, ma maggiore precisione di `double`. Il termine **virgola fissa** significa che il separatore decimale (o punto binario) non si sposta. Esaminare il codice seguente:

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

Dopo aver esaminato i diversi tipi numerici, scrivere codice che calcola l'area di un cerchio con raggio di 2,5 cm. Ricordarsi che l'area di un cerchio si calcola moltiplicando il quadrato del raggio per Pi greco. Suggerimento: .NET contiene una costante per Pi greco, <xref:System.Math.PI?displayProperty=nameWithType>, che è possibile usare per tale valore.

Si otterrà una risposta compresa tra 19 e 20.
È possibile controllare la risposta esaminando [il codice di esempio completato su GitHub](https://github.com/dotnet/samples/tree/master/csharp/numbers-quickstart/Program.cs#L104-L106).

È anche possibile provare alcune altre formule.

È stata completata la guida introduttiva "Numeri in C#". È possibile continuare con la guida introduttiva [Rami e cicli](branches-and-loops-local.md) nel proprio ambiente di sviluppo.

Negli argomenti seguenti sono disponibili ulteriori informazioni sui numeri in C#:

- [Tipi numerici integrali](../../language-reference/builtin-types/integral-numeric-types.md)
- [Tipi numerici a virgola mobile](../../language-reference/builtin-types/floating-point-numeric-types.md)
- [Conversioni numeriche predefinite](../../language-reference/builtin-types/numeric-conversions.md)

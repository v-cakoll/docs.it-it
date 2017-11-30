---
title: Avvio rapido - rami e lops - Guida per c#
description: In questa Guida introduttiva su cicli e diramazioni, scrivere codice c# per esplorare la sintassi del linguaggio che supporta rami condizionali e cicli per eseguire istruzioni ripetutamente.
author: billwagner
ms.author: wiwagn
ms.date: 10/31/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 4b077a29cf42072a93b054f50a13a4580ad54304
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2017
---
# <a name="branches-and-loops"></a>Rami e cicli

Questa Guida introduttiva illustra come scrivere codice che esamina le variabili e cambia il percorso di esecuzione in base a tali variabili. Scrivere codice c# e visualizzare i risultati della compilazione e l'esecuzione. La Guida introduttiva contiene una serie di lezioni che esplorano la diramazione e costrutti del linguaggio c# di ciclo. Queste lezioni presentano le nozioni fondamentali del linguaggio C#.

Questa Guida introduttiva prevede di disporre di un computer in cui che è possibile utilizzare per lo sviluppo. L'argomento .NET [Introduzione a 10 minuti](https://www.microsoft.com/net/core) con le istruzioni per configurare l'ambiente di sviluppo locale in Mac, Linux o PC.

## <a name="make-decisions-using-the-if-statement"></a>Prendere le decisioni utilizzando il `if` istruzione

Creare una directory denominata **Guida introduttiva di rami**. Impostarla come directory corrente ed eseguire `dotnet new console -n BranchesAndLoops -o .`. Questo comando crea una nuova applicazione console .NET Core nella directory corrente. 

Aprire **Program.cs** nel proprio editor preferito e sostituire la riga `Console.Writeline("Hello World!");` con il codice seguente:

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

Provare questo codice digitando `dotnet run` nella finestra di console. Verrà visualizzato il messaggio "la risposta è maggiore di 10". stampato sulla console.

Modificare la dichiarazione di `b` in modo che la somma sia minore di 10: 

```csharp
int b = 3;
```

Tipo `dotnet run` nuovamente. Dato che la risposta è minore a 10, non viene visualizzato nulla. La **condizione** testata è false. Non esiste codice da eseguire perché è stato scritto solo uno dei possibili rami per un'istruzione `if`, ovvero il ramo true.

> [!TIP]
> Mentre si impara a usare C# (o qualsiasi linguaggio di programmazione) sicuramente si commetteranno errori durante la scrittura del codice. Il compilatore sarà individuare e segnalare gli errori. Esaminare attentamente l'output degli errori e il codice che ha generato l'errore. L'errore compler consentono in genere di individuare il problema. 

Questo primo esempio viene illustrata la potenza di `if` e i tipi booleani. Oggetto *booleano* è una variabile che può avere uno dei due valori: `true` o `false`. C# definisce un tipo speciale, `bool` per variabili booleane. L'istruzione `if` controlla il valore di un `bool`. Quando il valore è `true`, viene eseguita l'istruzione che segue `if`. In caso contrario, l'istruzione viene ignorata. 

Questo processo di controllo delle condizioni ed esecuzione di istruzioni in base a queste condizioni offre molte potenzialità.


## <a name="make-if-and-else-work-together"></a>Usare insieme if ed else

Per eseguire codice diverso per i rami true e false, è necessario creare un ramo `else` che viene eseguito quando la condizione è false. Provare questa. Aggiungere il codice seguente per le ultime due righe del `Main` metodo (dovrebbe già disporre i primi quattro):

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

L'istruzione che segue la parola chiave `else` viene eseguita solo quando la condizione testata è `false`. La combinazione di `if` e `else` con valore booleano condizioni fornisce tutte le funzionalità necessarie per gestire entrambi un `true` e `false` condizione.

> [!IMPORTANT]
> Il rientro applicato alle righe successive alle istruzioni `if` e `else` è pensato per i lettori umani.
> Nel linguaggio C# i rientri o gli spazi vuoti non sono significativi. L'istruzione che segue la parola chiave `if` o `else` verrà eseguita in base alla condizione. Tutti gli esempi in questa Guida introduttiva seguono una pratica comune per il rientro alle righe in base al flusso di controllo di istruzioni.

Dato che il rientro non è significativo, è necessario usare `{` e `}` per indicare quando si vuole includere più di un'istruzione nel blocco con esecuzione condizionale. I programmatori C# usano in genere le parentesi graffe in tutte le clausole `if` e `else`. L'esempio seguente è lo stesso di quello che appena creato. Modificare il codice precedente in modo che corrisponda il codice seguente:

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
{
    Console.WriteLine("The answer is greater than 10");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
}
```

> [!TIP]
> Resto di questa Guida introduttiva, tutti gli esempi di codice includono le parentesi graffe dopo accettato consigliate.

È possibile verificare le condizioni più complesse. Aggiungere il codice seguente nel `Main` metodo dopo il codice scritto finora:

```csharp
    int c = 4;
    if ((a + b + c > 10) && (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not greater than the second");
}
```

`&&` rappresenta "e" e significa che entrambe le condizioni devono essere true per eseguire l'istruzione nel ramo true.  Questi esempi mostrano anche che è possibile includere più istruzioni in ogni ramo condizionale, a condizione di racchiuderle tra `{` e `}`.

È inoltre possibile utilizzare `||` per rappresentare "o". Dopo di ciò che è stato scritto fino a questo punto, aggiungere il codice seguente:

```csharp
if ((a + b + c > 10) || (a > b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is greater than the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not greater than the second");
}
```

Il primo passaggio per volta. Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato. In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio. Rinominare il metodo `Main` in `ExploreIf` e scrivere un nuovo metodo `Main` che chiama `ExploreIf`. Al termine, il codice dovrebbe risultare simile al seguente:

```csharp
using System;

namespace BranchesAndLoops
{
    class Program
    {
        static void ExploreIf()
        {
            int a = 5;
            int b = 3;
            if (a + b > 10)
            {
                Console.WriteLine("The answer is greater than 10");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
            }

            if ((a + b + c > 10) && (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("And the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("Or the first number is not greater than the second");
            }

            if ((a + b + c > 10) || (a > b))
            {
                Console.WriteLine("The answer is greater than 10");
                Console.WriteLine("Or the first number is greater than the second");
            }
            else
            {
                Console.WriteLine("The answer is not greater than 10");
                Console.WriteLine("And the first number is not greater than the second");
            }            
        }

        static void Main(string[] args)
        {
            ExploreIf();
        }
    }
}
```

Commentare la chiamata a `ExploreIf()`. L'output che meno pieno di informazioni mentre si lavora in questa sezione sarà:

```csharp
//ExploreIf();
```

Il `//` avvia un **commento** in c#. I commenti sono qualsiasi testo che si desidera mantenere nel codice sorgente, ma non è stato eseguito come codice. Il compilatore non genera codice eseguibile da commenti.

## <a name="use-loops-to-repeat-operations"></a>Usare i cicli per ripetere le operazioni

In questa sezione useranno **cicli** ripetere le istruzioni. Provare questo codice nel `Main` metodo:

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

Il `while` istruzione verifica una condizione ed esegue l'istruzione o un blocco di istruzione che segue il `while`. Verifica ripetutamente la condizione e l'esecuzione di tali istruzioni fino a quando la condizione è false.

Questo esempio include un altro operatore nuovo. I caratteri `++` dopo la variabile `counter` rappresentano l'operatore di **incremento**. Viene aggiunto 1 al valore di `counter` e archivia il valore nel `counter` variabile.

> [!IMPORTANT]
> Assicurarsi che il `while` ciclo modifiche condizione su false quando si esegue il codice. In caso contrario, si crea un **ciclo infinito** in cui il programma non termina mai. Che non viene dimostrata in questo esempio, in quanto è necessario forzare la chiusura utilizzando il programma **CTRL-C** o altri metodi.

Il ciclo `while` testa la condizione prima di eseguire il codice dopo `while`. Il ciclo `do` ... `while` esegue prima il codice e poi controlla la condizione, L'attività durante il ciclo è illustrato nel codice seguente:

```csharp
counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

Questo `do` ciclo e la precedente `while` ciclo producono lo stesso output.

## <a name="work-with-the-for-loop"></a>Usare il ciclo for

Il **per** ciclo viene utilizzato comunemente in c#. Provare questo codice nel metodo Main ():

```csharp
for(int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
} 
```

Questo codice esegue le stesse operazioni di ciclo `while` e `do` già usate. L'istruzione `for` è composta da tre parti che ne controllano il funzionamento. 

La prima parte è l'**inizializzatore for**: `for index = 0;` dichiara che `index` è la variabile di ciclo e imposta il valore iniziale su `0`.

La parte centrale è la **condizione for**: `index < 10` dichiara che questo ciclo `for` continua l'esecuzione fino a quando il valore del contatore è minore di 10.

La parte finale è l'**iteratore for**: `index++` specifica come modificare la variabile di ciclo dopo l'esecuzione del blocco successivo all'istruzione `for`. In questo caso, specifica che `index` deve essere incrementato di 1 a ogni esecuzione del blocco.

Sperimentare da soli questi elementi. Eseguire queste prove:

- Cambiare l'inizializzatore in modo che inizi da un valore diverso.
- Cambiare la condizione in modo che si interrompa in corrispondenza di un valore diverso.

Al termine, passare alla prossima lezione che prevede la scrittura di codice per usare quanto finora appreso.

## <a name="combine-branches-and-loops"></a>Combinare i cicli e diramazioni

Dopo aver esaminato l'istruzione `if` e i costrutti per i cicli nel linguaggio C#, provare a scrivere codice C# per ottenere la somma di tutti i numeri interi da 1 a 20 divisibili per 3.  Ecco alcuni suggerimenti:

- L'operatore `%` restituisce il resto di un'operazione di divisione.
- Il `if` istruzione che permette la condizione per vedere se un numero deve essere parte della somma.
- Il ciclo `for` può essere utile per ripetere una serie di passaggi per tutti i numeri da 1 a 20.

Sperimentare e quindi controllare i risultati. È possibile visualizzare una possibile risposta da [visualizzando il codice completato su GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/branches-quickstart/Program.cs#L46-L54).

È stata completata la "rami e cicli" Guida introduttiva.

È possibile continuare con la [matrici e raccolte](arrays-and-collections.md) avvio rapido nel proprio ambiente di sviluppo.

Maggiori informazioni su questi concetti sono disponibili in questi argomenti:

[Istruzioni if ed else](../language-reference/keywords/if-else.md)   
[Istruzione while](../language-reference/keywords/while.md)   
[Istruzione do](../language-reference/keywords/do.md)   
[Istruzione for](../language-reference/keywords/for.md)   

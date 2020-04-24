---
title: Rami e cicli - Esercitazione introduttiva su C#
description: In questa esercitazione su rami e cicli si scriverà codice C# per esplorare la sintassi del linguaggio che supporta cicli e diramazioni condizionali per eseguire ripetutamente istruzioni.
ms.date: 10/31/2017
ms.custom: mvc
ms.openlocfilehash: d8c10a7462b7c27c5353aee6d957732a8d161015
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135945"
---
# <a name="learn-conditional-logic-with-branch-and-loop-statements"></a>Informazioni sulla logica condizionale con istruzioni per rami e cicli

Questa esercitazione descrive come scrivere codice che esamina le variabili e modifica il percorso di esecuzione in base a queste variabili. Verranno descritte le procedure per scrivere codice C# e visualizzare i risultati della compilazione ed esecuzione del codice. L'esercitazione contiene una serie di lezioni che esplorano i costrutti per rami e cicli in C#. Queste lezioni presentano le nozioni fondamentali del linguaggio C#.

Questa esercitazione prevede la presenza di un computer da usare per lo sviluppo. L'esercitazione .NET [Hello World in 10 minuti](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) contiene le istruzioni per configurare l'ambiente di sviluppo locale in Windows, Linux o MacOS. Una breve panoramica dei comandi usati è disponibile in [Acquisire familiarità con gli strumenti di sviluppo](local-environment.md), che contiene collegamenti a informazioni più dettagliate.

## <a name="make-decisions-using-the-if-statement"></a>Prendere decisioni usando l'istruzione `if`

Creare una directory denominata *branches-tutorial*. Rendere la directory corrente ed eseguire il comando seguente:

```dotnetcli
dotnet new console -n BranchesAndLoops -o .
```

Questo comando crea una nuova applicazione console .NET Core nella directory corrente.

Aprire *Program.cs* nell'editor preferito e sostituire la riga `Console.WriteLine("Hello World!");` con il codice seguente:

```csharp
int a = 5;
int b = 6;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10.");
```

Per provare questo codice, digitare `dotnet run` nella finestra della console. Verrà visualizzato il messaggio "The answer is greater than 10." nella console.

Modificare la dichiarazione di `b` in modo che la somma sia minore di 10:

```csharp
int b = 3;
```

Digitare di nuovo `dotnet run`. Dato che la risposta è minore a 10, non viene visualizzato nulla. La **condizione** testata è false. Non esiste codice da eseguire perché è stato scritto solo uno dei possibili rami per un'istruzione `if`, ovvero il ramo true.

> [!TIP]
> Mentre si impara a usare C# (o qualsiasi linguaggio di programmazione) sicuramente si commetteranno errori durante la scrittura del codice. Il compilatore troverà e segnalerà gli errori. Esaminare attentamente l'output dell'errore e il codice che ha generato l'errore. L'errore del compilatore consente in genere di trovare il problema.

Questo primo esempio dimostra le potenzialità di `if` e dei tipi booleani. Un valore *booleano* è una variabile che può avere uno di due valori: `true` o `false`. C# definisce un tipo speciale, `bool` per le variabili booleane. L'istruzione `if` controlla il valore di un `bool`. Quando il valore è `true`, viene eseguita l'istruzione che segue `if`. In caso contrario, l'istruzione viene ignorata.

Questo processo di controllo delle condizioni ed esecuzione di istruzioni in base a queste condizioni offre molte potenzialità.

## <a name="make-if-and-else-work-together"></a>Usare insieme if ed else

Per eseguire codice diverso per i rami true e false, è necessario creare un ramo `else` che viene eseguito quando la condizione è false. Provare questo codice. Aggiungere le ultime due righe del codice seguente al metodo `Main` (le prime quattro dovrebbero essere già presenti):

```csharp
int a = 5;
int b = 3;
if (a + b > 10)
    Console.WriteLine("The answer is greater than 10");
else
    Console.WriteLine("The answer is not greater than 10");
```

L'istruzione che segue la parola chiave `else` viene eseguita solo quando la condizione testata è `false`. La combinazione di `if` e `else` con condizioni booleane offre tutte le potenzialità necessarie per gestire sia una condizione `true` che una condizione `false`.

> [!IMPORTANT]
> Il rientro applicato alle righe successive alle istruzioni `if` e `else` è pensato per i lettori umani.
> Nel linguaggio C# i rientri o gli spazi vuoti non sono significativi.
> L'istruzione che segue la parola chiave `if` o `else` verrà eseguita in base alla condizione. Tutti gli esempi in questa esercitazione seguono una procedura comune che prevede il rientro delle righe in base al flusso di controllo delle istruzioni.

Dato che il rientro non è significativo, è necessario usare `{` e `}` per indicare quando si vuole includere più di un'istruzione nel blocco con esecuzione condizionale. I programmatori C# usano in genere le parentesi graffe in tutte le clausole `if` e `else`. L'esempio seguente è identico a quello appena creato. Modificare il codice precedente in modo che corrisponda al codice seguente:

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
> Nelle parti restanti di questa esercitazione, tutti gli esempi di codice includono le parentesi graffe conformemente alle consuetudini comuni.

È possibile testare condizioni più complesse. Aggiungere il codice seguente nel metodo `Main` dopo il codice scritto finora:

```csharp
int c = 4;
if ((a + b + c > 10) && (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("And the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("Or the first number is not equal to the second");
}
```

Il simbolo `==` verifica l'*uguaglianza*. Il simbolo `==` distingue il test per l'uguaglianza dall'assegnazione, illustrata in `a = 5`.

`&&` rappresenta "e" e significa che entrambe le condizioni devono essere true per eseguire l'istruzione nel ramo true.  Questi esempi mostrano anche che è possibile includere più istruzioni in ogni ramo condizionale, a condizione di racchiuderle tra `{` e `}`.

È anche possibile usare `||` per rappresentare "or". Aggiungere il codice seguente dopo il codice già scritto finora:

```csharp
if ((a + b + c > 10) || (a == b))
{
    Console.WriteLine("The answer is greater than 10");
    Console.WriteLine("Or the first number is equal to the second");
}
else
{
    Console.WriteLine("The answer is not greater than 10");
    Console.WriteLine("And the first number is not equal to the second");
}
```

Modificare i valori di `a`, `b` e `c` e passare da `&&` a `||` per esplorare. Si otterranno più informazioni sul funzionamento degli operatori `&&` e `||`.

Il primo passaggio è stato completato. Prima di iniziare la sezione successiva, è necessario spostare il codice corrente in un metodo separato. In questo modo sarà più semplice iniziare a lavorare con un nuovo esempio. Rinominare il metodo `Main` in `ExploreIf` e scrivere un nuovo metodo `Main` che chiama `ExploreIf`. Al termine, il codice dovrebbe risultare simile al seguente:

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

Impostare come commento la chiamata a `ExploreIf()`. L'output risulterà in questo modo meno disordinato quando si usa questa sezione:

```csharp
//ExploreIf();
```

`//` avvia un **commento** in C#. Un commento è un testo che si vuole conservare nel codice sorgente senza eseguirlo come codice. Il compilatore non genera codici eseguibili da commenti.

## <a name="use-loops-to-repeat-operations"></a>Usare i cicli per ripetere le operazioni

In questa sezione si usano i **cicli** per ripetere le istruzioni. Provare questo codice nel metodo `Main`:

```csharp
int counter = 0;
while (counter < 10)
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
}
```

L'istruzione `while` verifica una condizione ed esegue l'istruzione o il blocco di istruzioni che segue `while`. Ripete la verifica della condizione e l'esecuzione di tali istruzioni fino a quando la condizione è false.

Questo esempio include un altro operatore nuovo. I caratteri `++` dopo la variabile `counter` rappresentano l'operatore di **incremento**. Questo operatore aggiunge 1 al valore di `counter` e archivia il valore nella variabile `counter`.

> [!IMPORTANT]
> Assicurarsi che la condizione del ciclo `while` passi a false quando si esegue il codice. In caso contrario, si crea un **ciclo infinito** in cui il programma non termina mai. Tale situazione non è illustrata in questo esempio, perché è necessario forzare l'uscita dal programma usando **CTRL+C** o in altro modo.

Il ciclo `while` testa la condizione prima di eseguire il codice dopo `while`. Il ciclo `do` ... `while` esegue prima il codice e poi controlla la condizione, Il ciclo do while è illustrato nel codice riportato di seguito:

```csharp
int counter = 0;
do
{
    Console.WriteLine($"Hello World! The counter is {counter}");
    counter++;
} while (counter < 10);
```

Questo ciclo `do` e il ciclo `while` precedente generano lo stesso output.

## <a name="work-with-the-for-loop"></a>Usare il ciclo for

Il ciclo **for** viene in genere usato in C#. Provare questo codice nel metodo Main():

```csharp
for (int index = 0; index < 10; index++)
{
    Console.WriteLine($"Hello World! The index is {index}");
}
```

Questo codice esegue le stesse operazioni di ciclo `while` e `do` già usate. L'istruzione `for` è composta da tre parti che ne controllano il funzionamento.

La prima parte è l' **inizializzatore for**: `int index = 0;` dichiara che `index` è la variabile del ciclo e imposta il valore iniziale su `0`.

La parte intermedia è la **condizione for**: `index < 10` dichiara che questo `for` ciclo continua a essere eseguito fino a quando il valore del contatore è minore di 10.

La parte finale è l' **iteratore for**: `index++` specifica come modificare la variabile del ciclo dopo l'esecuzione del blocco dopo `for` l'istruzione. In questo caso, specifica che `index` deve essere incrementato di 1 a ogni esecuzione del blocco.

Sperimentare da soli questi elementi. Eseguire queste prove:

- Cambiare l'inizializzatore in modo che inizi da un valore diverso.
- Cambiare la condizione in modo che si interrompa in corrispondenza di un valore diverso.

Al termine, passare alla prossima lezione che prevede la scrittura di codice per usare quanto finora appreso.

## <a name="created-nested-loops"></a>Cicli annidati creati

Un `while`ciclo `do` , `for` o può essere annidato all'interno di un altro ciclo per creare una matrice utilizzando la combinazione di ogni elemento del ciclo esterno con ogni elemento del ciclo interno. A questo scopo, è necessario compilare un set di coppie alfanumeriche per rappresentare righe e colonne.

Un `for` ciclo può generare le righe:

```csharp
for (int row = 1; row < 11; row++)
{
    Console.WriteLine($"The row is {row}");
}
```

Un altro ciclo può generare le colonne:

```csharp
for (char column = 'a'; column < 'k'; column++)
{
    Console.WriteLine($"The column is {column}");
}
```

È possibile annidare un ciclo all'interno dell'altro per formare coppie:

```csharp
for (int row = 1; row < 11; row++)
{
    for (char column = 'a'; column < 'k'; column++)
    {
        Console.WriteLine($"The cell is ({row}, {column})");
    }
}
```

È possibile osservare che il ciclo esterno viene incrementato una volta per ogni esecuzione completa del ciclo interno. Invertire l'annidamento di righe e colonne e visualizzare le modifiche per se stessi.

## <a name="combine-branches-and-loops"></a>Combinare rami e cicli

Dopo aver esaminato l'istruzione `if` e i costrutti per i cicli nel linguaggio C#, provare a scrivere codice C# per ottenere la somma di tutti i numeri interi da 1 a 20 divisibili per 3.  Ecco alcuni suggerimenti:

- L'operatore `%` restituisce il resto di un'operazione di divisione.
- L'istruzione `if` offre la condizione per stabilire se un numero deve fare parte della somma.
- Il ciclo `for` può essere utile per ripetere una serie di passaggi per tutti i numeri da 1 a 20.

Sperimentare e quindi controllare i risultati. Verrà visualizzata una risposta 63. Per vedere una possibile risposta, [visualizzare il codice completo in GitHub](https://github.com/dotnet/samples/tree/master/csharp/branches-quickstart/Program.cs#L46-L54).

È stata completata l'esercitazione "Cicli e rami".

È possibile continuare con l'esercitazione [Matrici e raccolte](arrays-and-collections.md) nel proprio ambiente di sviluppo.

Maggiori informazioni su questi concetti sono disponibili in questi argomenti:

- [Istruzioni if ed else](../../language-reference/keywords/if-else.md)
- [Istruzione while](../../language-reference/keywords/while.md)
- [Istruzione do](../../language-reference/keywords/do.md)
- [Istruzione for](../../language-reference/keywords/for.md)

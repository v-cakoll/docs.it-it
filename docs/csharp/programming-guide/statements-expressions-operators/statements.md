---
title: Istruzioni - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- statements [C#], about statements
- C# language, statements
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
ms.openlocfilehash: d50b50bb291d0d087015ea5bd075ae90ced66ff5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75711935"
---
# <a name="statements-c-programming-guide"></a>Istruzioni (Guida per programmatori C#)

Le azioni accettate da un programma vengono espresse in istruzioni. Le azioni comuni includono la dichiarazione di variabili, l'assegnazione di valori, le chiamate ai metodi, il ciclo delle raccolte e la creazione di rami tra blocchi di codice, a seconda di una data condizione. L'ordine in cui vengono le istruzioni eseguite in un programma viene chiamato "flusso di controllo" o "flusso di esecuzione". Il flusso di controllo può variare ogni volta che viene eseguito un programma, a seconda della reazione del programma all'input ricevuto in fase di esecuzione.

Un'istruzione può essere costituito da una singola riga di codice che termina con un punto e virgola o da una serie di istruzioni a riga singola in un blocco. Un blocco di istruzioni è racchiuso tra parentesi {} e può contenere blocchi annidati. Il codice seguente mostra due esempi di istruzioni a riga singola e un blocco di istruzioni a più righe:

[!code-csharp[csProgGuideStatements#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#1)]

## <a name="types-of-statements"></a>Tipi di istruzioni

Nella tabella seguente sono elencati i vari tipi di istruzioni in C# e le parole chiave associate, con link ad argomenti contenenti maggiori informazioni:

|Category|Parole chiave C#/note|
|--------------|---------------------------|
|[Istruzioni di dichiarazione](#declaration-statements)|Un'istruzione di dichiarazione introduce una nuova variabile o costante. Una dichiarazione di variabile può facoltativamente assegnare un valore alla variabile. In una dichiarazione di costante, l'assegnazione è necessaria.|
|[Istruzioni di espressione](expressions.md)|Le istruzioni di espressione che calcolano un valore devono archiviare il valore in una variabile. Per altre informazioni, vedere [Istruzioni di espressione](#expression-statements).|
|Istruzioni di selezione|Le istruzioni di selezione consentono di creare un ramo tra le diverse sezioni di codice, in base a una o più condizioni specificate. Per altre informazioni, vedere gli argomenti seguenti: <ul><li>[Se](../../language-reference/keywords/if-else.md)</li><li>[else](../../language-reference/keywords/if-else.md)</li><li>[Interruttore](../../language-reference/keywords/switch.md)</li><li>[case](../../language-reference/keywords/switch.md)</li></ul>|
|Istruzioni di iterazione|Le istruzioni di iterazione consentono di eseguire un ciclo tra le raccolte come matrici o eseguono ripetutamente lo stesso set di istruzioni finché non viene soddisfatta una condizione specificata. Per altre informazioni, vedere gli argomenti seguenti: <ul><li>[fare](../../language-reference/keywords/do.md)</li><li>[Per](../../language-reference/keywords/for.md)</li><li>[Foreach](../../language-reference/keywords/foreach-in.md)</li><li>[in](../../language-reference/keywords/foreach-in.md)</li><li>[mentre](../../language-reference/keywords/while.md)</li></ul>|
|Istruzioni di salto|Le istruzioni di salto trasferiscono il controllo a un'altra sezione di codice. Per altre informazioni, vedere gli argomenti seguenti: <ul><li>[Pausa](../../language-reference/keywords/break.md)</li><li>[Continuare](../../language-reference/keywords/continue.md)</li><li>[Predefinito](../../language-reference/keywords/switch.md)</li><li>[Goto](../../language-reference/keywords/goto.md)</li><li>[Ritorno](../../language-reference/keywords/return.md)</li><li>[yield](../../language-reference/keywords/yield.md)</li></ul>|
|Istruzioni di gestione delle eccezioni|Le istruzioni di gestione delle eccezioni consentono di recuperare condizioni eccezionali che si verificano in fase di esecuzione. Per altre informazioni, vedere gli argomenti seguenti: <ul><li>[generazione](../../language-reference/keywords/throw.md)</li><li>[try-catch](../../language-reference/keywords/try-catch.md)</li><li>[try...finally](../../language-reference/keywords/try-finally.md)</li><li>[try-catch-finally](../../language-reference/keywords/try-catch-finally.md)</li></ul>|
|[Selezionato e deselezionato](../../language-reference/keywords/checked-and-unchecked.md)|Le istruzioni Checked e Unchecked consentono di specificare se le operazioni numeriche possono provocare un overflow quando il risultato viene archiviato in una variabile troppo piccola per contenere il valore risultante. Per altre informazioni, vedere [checked](../../language-reference/keywords/checked.md) e [unchecked](../../language-reference/keywords/unchecked.md).|
|Istruzione `await`|Se si contrassegna un metodo con il modificatore [async](../../language-reference/keywords/async.md), è possibile usare l'operatore [await](../../language-reference/operators/await.md) nel metodo. Quando il controllo raggiunge un'espressione `await` nel metodo asincrono, il controllo torna al chiamante e l'avanzamento nel metodo viene sospeso fino al completamento dell'attività attesa. Una volta completata l'attività, l'esecuzione del metodo può riprendere.<br /><br /> Per un esempio semplice, vedere la sezione "Metodi asincroni" in [Metodi](../classes-and-structs/methods.md). Per altre informazioni, vedere [Programmazione asincrona con async e await](../concepts/async/index.md).|
|Istruzione `yield return`|Un iteratore esegue un'iterazione personalizzata su una raccolta, ad esempio un elenco o una matrice. Un iteratore usa l'istruzione [yield return](../../language-reference/keywords/yield.md) per restituire un elemento alla volta. Quando viene raggiunta un'istruzione `yield return`, la posizione corrente nel codice viene memorizzata. L'esecuzione viene riavviata a partire da quella posizione la volta successiva che viene chiamato l'iteratore.<br /><br /> Per ulteriori informazioni, vedere [Iteratori](../concepts/iterators.md).|
|Istruzione `fixed`|L'istruzione fixed impedisce che il Garbage Collector esegua la rilocazione di una variabile mobile. Per altre informazioni, vedere [fixed](../../language-reference/keywords/fixed-statement.md).|
|Istruzione `lock`|L'istruzione lock consente di limitare l'accesso ai blocchi di codice a un solo thread per volta. Per altre informazioni, vedere [lock](../../language-reference/keywords/lock-statement.md).|
|Istruzioni con etichetta|È possibile assegnare un'etichetta a un'istruzione e quindi usare la parola chiave [goto](../../language-reference/keywords/goto.md) per passare all'istruzione con etichetta. Vedere l'esempio nell'argomento seguente.|
|[L'istruzione vuota](#the-empty-statement)|L'istruzione vuota è costituita da un singolo punto e virgola. Non esegue alcuna operazione e può essere usata in posizioni in cui è richiesta un'istruzione ma non deve essere eseguita alcuna azione.|

## <a name="declaration-statements"></a>Istruzioni di dichiarazione

Il codice seguente illustra esempi di dichiarazioni di variabili con e senza un'assegnazione iniziale e una dichiarazione di costante con le inizializzazioni necessarie.

[!code-csharp[csProgGuideStatements#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#23)]

## <a name="expression-statements"></a>Istruzioni di espressione

Il codice seguente illustra esempi di istruzioni di espressione, tra cui assegnazione, creazione di oggetti con assegnazione, e la chiamata al metodo.

[!code-csharp[csProgGuideStatements#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#24)]

## <a name="the-empty-statement"></a>Istruzione vuota

Gli esempi seguenti illustrano due usi di un'istruzione vuota:

[!code-csharp[csProgGuideStatements#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#25)]

## <a name="embedded-statements"></a>Dichiarazioni incorporate

Alcune istruzioni, fra cui [do](../../language-reference/keywords/do.md), [while](../../language-reference/keywords/while.md), [for](../../language-reference/keywords/for.md) e [foreach](../../language-reference/keywords/foreach-in.md), dispongono sempre di un'istruzione incorporata che le segue. Questa istruzione incorporata può essere una singola istruzione o più istruzioni racchiuse tra parentesi {} in un blocco di istruzioni. Anche le istruzioni incorporate a riga singola possono essere racchiuse tra parentesi {}, come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideStatements#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#26)]

Un'istruzione incorporata non racchiusa tra parentesi {} non può essere un'istruzione di dichiarazione o un'istruzione con etichetta. Questa operazione è illustrata nell'esempio seguente:

[!code-csharp[csProgGuideStatements#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#27)]

Inserire l'istruzione incorporata in un blocco per correggere l'errore:

[!code-csharp[csProgGuideStatements#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#28)]

## <a name="nested-statement-blocks"></a>Blocchi di istruzioni annidatiNested statement blocks

I blocchi di istruzioni possono essere annidati, come illustrato nel codice seguente:

[!code-csharp[csProgGuideStatements#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#29)]

## <a name="unreachable-statements"></a>Dichiarazioni irraggiungibili

Se il compilatore determina che il flusso di controllo non può raggiungere mai una particolare istruzione in nessuna circostanza, genererà l'avviso CS0162, come illustrato nell'esempio seguente:

[!code-csharp[csProgGuideStatements#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#22)]

## <a name="c-language-specification"></a>Specifiche del linguaggio C#

Per altre informazioni, vedere la sezione [Istruzioni](~/_csharplang/spec/statements.md) della [specifica del linguaggio C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Parole chiave di istruzione](../../language-reference/keywords/statement-keywords.md)  
- [Espressioni](expressions.md)  

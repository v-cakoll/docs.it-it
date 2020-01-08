---
title: Esplorare il codice con il visualizzatore di sintassi Roslyn in Visual Studio
description: Il visualizzatore di sintassi è uno strumento visivo che consente di esaminare i modelli che .NET Compiler Platform SDK genera per il codice.
ms.date: 03/07/2018
ms.custom: mvc, vs-dotnet
ms.openlocfilehash: c4b4414dabcb6c9749a23d726e4a69334376d988
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346969"
---
# <a name="explore-code-with-the-roslyn-syntax-visualizer-in-visual-studio"></a>Esplorare il codice con il visualizzatore di sintassi Roslyn in Visual Studio

Questo articolo offre una panoramica sul visualizzatore di sintassi incluso in .NET Compiler Platform ("Roslyn") SDK. Il visualizzatore di sintassi è una finestra degli strumenti che consente di controllare ed esaminare gli alberi della sintassi. È uno strumento fondamentale per esaminare i modelli del codice che si vuole analizzare. Può anche essere usato per eseguire il debug durante lo sviluppo delle applicazioni che usano .NET Compiler Platform ("Roslyn") SDK. Aprire questo strumento quando si creano i primi analizzatori. Il visualizzatore consente di esaminare i modelli usati dalle API. È anche possibile usare strumenti quali [SharpLab](https://sharplab.io) oppure [LINQPad](https://www.linqpad.net/) per controllare il codice e analizzare gli alberi della sintassi.

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

Per acquisire familiarità con i concetti usati in .NET Compiler Platform SDK, leggere l'articolo relativo alle [informazioni generali](compiler-api-model.md). Contiene un'introduzione ad alberi della sintassi, nodi, token ed elementi semplici.

## <a name="syntax-visualizer"></a>Visualizzatore di sintassi

Il **Syntax Visualizer** consente di controllare l'albero della sintassi per C# il file di codice o Visual Basic nella finestra dell'editor attiva corrente all'interno dell'IDE di Visual Studio. Il visualizzatore può essere avviato facendo clic su **Visualizza** > **Altre finestre** > **Syntax Visualizer** (Visualizzatore di sintassi).  È anche possibile usare la barra degli strumenti **Avvio veloce** nell'angolo in alto a destra. Digitare "syntax" per visualizzare il comando che apre il **visualizzatore di sintassi**.

Questo comando apre il visualizzatore di sintassi sotto forma di finestra degli strumenti mobile. Se non si apre una finestra dell'editore del codice, l'area visualizzata è vuota, come illustrato nella figura seguente. 

![Finestra degli strumenti del visualizzatore di sintassi](media/syntax-visualizer/syntax-visualizer.png)

Ancorare questa finestra degli strumenti in una posizione appropriata all'interno di Visual Studio, ad esempio sul lato sinistro. Il visualizzatore offre le informazioni sul file di codice corrente.

Creare un nuovo progetto usando il comando **File** > **Nuovo progetto**. È possibile creare un Visual Basic o C# un progetto. Quando Visual Studio apre il file di codice principale di questo progetto, il visualizzatore ne visualizza l'albero della sintassi. È possibile aprire qualsiasi file C# esistente/Visual Basic in questa istanza di Visual Studio e il Visualizzatore Visualizza l'albero della sintassi del file. Se in Visual Studio sono aperti più file di codice, viene visualizzato l'albero della sintassi del file di codice attualmente attivo, vale a dire il file di codice con lo stato attivo.

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Visualizzazione di un albero della sintassi di C#](media/syntax-visualizer/visualize-csharp.png)

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)
![Visualizzazione di un albero della sintassi di Visual Basic](media/syntax-visualizer/visualize-visual-basic.png)

---

Come illustrato nelle immagini precedenti, nella finestra degli strumenti del visualizzatore vengono visualizzati l'albero della sintassi in alto e una griglia delle proprietà in basso. Questa griglia contiene le proprietà dell'elemento attualmente selezionato nell'albero, comprese le proprietà *Type* e *Kind* (SyntaxKind) .NET dell'elemento.

Gli alberi della sintassi includono tre tipi di elementi: *nodi*, *token* ed *elementi semplici*. Per altre informazioni su questi tipi di elementi, leggere l'articolo [Usare la sintassi](work-with-syntax.md). Gli elementi di ogni tipo sono rappresentati da un colore diverso. Fare clic sul pulsante "Legend" (Leggenda) per informazioni sui colori usati.

Ogni elemento dell'albero indica anche il relativo elemento **span**. L'elemento **span** rappresenta gli indici (posizione iniziale e finale) di tale nodo nel file di testo.  Nell'esempio precedente di C# il token "UsingKeyword [0..5)" selezionato ha un elemento **Span** di cinque caratteri, rappresentato dalla notazione [0..5)). La notazione "[..)" indica che l'indice iniziale è parte dello span, mentre non lo è l'indice finale.

Esistono due modi per esplorare l'albero:

* Espandere o fare clic sugli elementi dell'albero. Il visualizzatore seleziona automaticamente il testo corrispondente allo span dell'elemento nell'editor di codice.
* Selezionare o fare clic sul testo nell'editor di codice. Nel Visual Basic esempio precedente, se si seleziona la riga contenente "modulo Module1" nell'editor di codice, il visualizzatore passa automaticamente al nodo ModuleStatement corrispondente nell'albero. 

Il visualizzatore evidenzia l'elemento nell'albero il cui span corrisponde maggiormente allo span del testo selezionato nell'editor.

Il visualizzatore aggiorna l'albero per visualizzare le modifiche apportate nel file di codice attivo. Aggiungere una chiamata a `Console.WriteLine()` all'interno di `Main()`. Durante la digitazione, il visualizzatore aggiorna l'albero.

Sospendere la digitazione dopo aver digitato `Console.`. L'albero include alcuni elementi di colore rosa. Si tratta di errori nel codice tipizzato, definiti anche "Diagnostica", associati a nodi, token ed elementi semplici nell'albero della sintassi. Il visualizzatore visualizza gli elementi con errori associati evidenziandone lo sfondo di colore rosa. È possibile esaminare gli errori associati a tutti gli elementi evidenziati di rosa, passando il puntatore sull'elemento. Il visualizzatore visualizza solo gli errori sintattici, vale a dire gli errori correlati alla sintassi del codice tipizzato. Non vengono visualizzati gli errori di tipo semantico.
 
## <a name="syntax-graphs"></a>Grafici di sintassi

Fare clic con il pulsante destro su un elemento qualsiasi dell'albero e fare clic su **View Directed Syntax Graph** (Visualizza grafico di sintassi diretto). 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

Sarà visualizzata una rappresentazione grafica del sottoalbero corrispondente all'elemento selezionato. Provare questi passaggi per il nodo **MethodDeclaration** corrispondente al metodo `Main()` nell'esempio di C#. Il grafico di sintassi visualizzato sarà simile al seguente:

![Visualizzazione di un grafico di sintassi di C#](media/syntax-visualizer/csharp-syntax-graph.png)

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

Provare lo stesso per il nodo del **sottoblocco** corrispondente al metodo `Main()` nell'esempio di Visual Basic precedente. Il grafico di sintassi visualizzato sarà simile al seguente:

![Visualizzazione di un grafico della sintassi di Visual Basic](media/syntax-visualizer/visual-basic-syntax-graph.png)

---

Nel visualizzatore del grafico di sintassi è possibile visualizzare una legenda relativa allo schema colori. È anche possibile passare il puntatore del mouse sui singoli elementi nel grafico di sintassi per visualizzare le proprietà che corrispondono a tale elemento.

È possibile visualizzare ripetutamente grafici di sintassi per elementi diversi dell'albero. I grafici saranno sempre visualizzati nella stessa finestra all'interno di Visual Studio. Tale finestra può essere ancorata in una posizione appropriata all'interno di Visual Studio in modo che non sia necessario passare da una scheda all'altra per visualizzare un nuovo grafico di sintassi. È spesso consigliabile posizionarla in basso, sotto le finestre dell'editor del codice.

Di seguito è raffigurato il layout di ancoraggio da usare con la finestra degli strumenti del visualizzatore e la finestra del grafico di sintassi:

![Layout di ancoraggio per la finestra del visualizzatore e del grafico di sintassi](media/syntax-visualizer/docking-layout.png)

È anche possibile inserire la finestra del grafico di sintassi in un secondo monitor, in caso di configurazione a doppio monitor.

## <a name="inspecting-semantics"></a>Analisi della semantica

Il visualizzatore di sintassi consente di eseguire un'ispezione elementare di simboli e informazioni semantiche. Digitare `double x = 1 + 1;` all'interno di Main () nell'esempio di C#. A questo punto, selezionare l'espressione `1 + 1` nella finestra dell'editor del codice. Il visualizzatore evidenzierà il nodo **AddExpression** nel visualizzatore. Fare clic con il pulsante destro sul nodo **AddExpression** e fare clic su **View Symbol (if any)** (Visualizza simbolo (se esiste)). Si noti che la maggior parte delle voci di menu usa il qualificatore "se esiste". Il visualizzatore di sintassi controlla le proprietà di un nodo, incluse le proprietà che possono non essere presenti per tutti i nodi. 

La griglia delle proprietà nel visualizzatore viene aggiornata come illustrato nella figura seguente. Il simbolo dell'espressione è un oggetto **SynthesizedIntrinsicOperatorSymbol** con **Kind = Method**.

![Proprietà del simbolo](media/syntax-visualizer/symbol-properties.png)

Provare a selezionare **View TypeSymbol (if any)** (Visualizza TypeSymbol (se esiste)) per lo stesso nodo **AddExpression**. La griglia delle proprietà nel visualizzatore viene aggiornata come illustrato nella figura seguente e indica che il tipo dell'espressione selezionata è `Int32`.

![Proprietà di TypeSymbol](media/syntax-visualizer/type-symbol-properties.png)

Provare a selezionare **View Converted TypeSymbol (if any)** (Visualizza TypeSymbol convertito (se esiste)) per lo stesso nodo **AddExpression**. La griglia delle proprietà viene aggiornata e indica che, sebbene il tipo dell'espressione sia `Int32`, il tipo convertito dell'espressione è `Double`, come illustrato nella figura seguente. Questo nodo include le informazioni sul simbolo del tipo convertito perché l'espressione `Int32` si trova in un contesto in cui deve essere convertita in `Double`. Questa conversione soddisfa il tipo `Double` specificato per la variabile `x` a sinistra dell'operatore di assegnazione.

![Proprietà di Converted TypeSymbol](media/syntax-visualizer/converted-type-symbol-properties.png)

Infine, provare a selezionare **View Constant Value (if any)** (Visualizza valore costante (se esiste) per lo stesso nodo **AddExpression**. La griglia delle proprietà indica che il valore dell'espressione è una costante in fase di compilazione con valore `2`.

![Un valore costante](media/syntax-visualizer/constant-value.png)

L'esempio precedente può essere replicato anche in Visual Basic. Digitare `Dim x As Double = 1 + 1` in un file di Visual Basic. Selezionare l'espressione `1 + 1` nella finestra dell'editor del codice. Il visualizzatore evidenzierà il nodo **AddExpression** corrispondente nel visualizzatore. Ripetere i passaggi precedenti per il nodo **AddExpression**. I risultati saranno identici.

Esaminare altro codice in Visual Basic. Aggiornare il file di Visual Basic principale con il codice seguente:

```vb
Imports C = System.Console

Module Program
    Sub Main(args As String())
        C.WriteLine()
    End Sub
End Module
```

Questo codice introduce un alias denominato `C` che esegue il mapping al tipo `System.Console` all'inizio del file e usa l'alias all'interno di `Main()`. Selezionare l'uso di questo alias (`C` in `C.WriteLine()`) all'interno del metodo `Main()`. Il visualizzatore seleziona il nodo **IdentifierName** corrispondente nel visualizzatore. Fare clic con il pulsante destro del mouse su questo nodo e selezionare **View Symbol (if any)** (Visualizza simbolo (se esiste)). La griglia delle proprietà indica che questo identificatore è associato al tipo `System.Console` come illustrato nella figura seguente:

![Proprietà del simbolo](media/syntax-visualizer/symbol-visual-basic.png)

Provare a selezionare **View AliasSymbol (if any))** (Visualizza AliasSymbol (se esiste)) per lo stesso nodo **IdentifierName**. La griglia delle proprietà indica che l'identificatore è un alias denominato `C` e associato alla destinazione `System.Console`. In altre parole, la griglia delle proprietà contiene informazioni relative all'oggetto **AliasSymbol** che corrisponde all'identificatore `C`.

![Proprietà del simbolo alias](media/syntax-visualizer/alias-symbol.png)

Controllare il simbolo che corrisponde a qualsiasi tipo, metodo, proprietà dichiarati. Selezionare il nodo corrispondente nel visualizzatore e fare clic su **View Symbol (if any)** (Visualizza simbolo (se esiste)). Selezionare il metodo `Sub Main()`, incluso il corpo del metodo. Fare clic su **View Symbol (if any)** (Visualizza simbolo (se esiste)) per il nodo **SubBlock** corrispondente nel visualizzatore. La griglia delle proprietà indica che il nome di **MethodSymbol** per il nodo **SubBlock** è `Main` con tipo restituito `Void`.

![Visualizzazione del simbolo per una dichiarazione del metodo](media/syntax-visualizer/method-symbol.png)

Gli esempi Visual Basic precedenti possono essere facilmente replicati in C#. Digitare `using C = System.Console;` invece di `Imports C = System.Console` per l'alias. I passaggi precedenti in C# restituiscono gli stessi risultati nella finestra del visualizzatore.

È possibile eseguire l'ispezione semantica solo sui nodi. Non è disponibile su token o elementi semplici. Non tutti i nodi contengono informazioni semantiche interessanti da controllare. Quando un nodo non contiene informazioni semantiche interessanti, facendo clic su **View \* Symbol (if any)** (Visualizza simbolo se esistente) apparirà una griglia delle proprietà vuota.

Altre informazioni sulle API per l'esecuzione dell'analisi semantica sono disponibile nel documento di anteprima [Usare la semantica](work-with-semantics.md).

## <a name="closing-the-syntax-visualizer"></a>Chiusura del visualizzatore di sintassi

È possibile chiudere la finestra del visualizzatore se non si sta usando lo strumento per esaminare il codice sorgente. Il visualizzatore di sintassi aggiorna i dati visualizzati man mano che ci sposta all'interno del codice, modificando l'origine. Lo strumento può rivelarsi di disturbo se non è usato. 

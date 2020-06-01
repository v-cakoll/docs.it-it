---
title: Eseguire il debug di un'applicazione console .NET Core con Visual Studio Code
description: Informazioni su come eseguire il debug di un'app console .NET Core con Visual Studio Code.
ms.date: 05/26/2020
ms.openlocfilehash: 82b2798397d702aa2a50c04bf6e4d569b97e3666
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241513"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-code"></a>Esercitazione: eseguire il debug di un'applicazione console .NET Core usando Visual Studio Code

Questa esercitazione introduce gli strumenti di debug disponibili in Visual Studio Code per l'uso con le app .NET Core.

## <a name="prerequisites"></a>Prerequisiti

- Questa esercitazione funziona con l'app console creata in [creare un'applicazione console .NET Core in Visual Studio Code](with-visual-studio-code.md).

## <a name="use-debug-build-configuration"></a>Usa configurazione build di debug

Il *debug* e la *versione* sono due delle configurazioni della build di .NET Core. Usare la configurazione della build di debug per il debug e la configurazione di rilascio per la distribuzione finale della versione.

Nella configurazione di debug, un programma viene compilato con informazioni di debug simboliche complete e senza ottimizzazione. L'ottimizzazione rende più difficile il debug perché la relazione tra il codice sorgente e le istruzioni generate è più complessa. La configurazione di rilascio di un programma non dispone di informazioni di debug simboliche ed è completamente ottimizzata.

 Per impostazione predefinita, Visual Studio Code Usa la configurazione della build di debug, pertanto non è necessario modificarla prima del debug.

## <a name="set-a-breakpoint"></a>Imposta punto di interruzione

Un punto di interruzione interrompe temporaneamente l'esecuzione dell'applicazione *prima* che venga eseguita la riga con il punto di interruzione.

1. Aprire Visual Studio Code.

1. Aprire la cartella del progetto *HelloWorld* creata in [creare un'applicazione console .net core in Visual Studio Code](with-visual-studio-code.md).

1. Aprire il file *Program.cs* .

1. Impostare un punto di *interruzione* nella riga in cui vengono visualizzati il nome, la data e l'ora facendo clic sul margine sinistro della finestra del codice. Il margine sinistro è a sinistra dei numeri di riga. Un altro modo per impostare un punto di interruzione consiste nel posizionare il cursore nella riga di codice e quindi premere <kbd>F9</kbd>.

   Come illustrato nell'immagine seguente, Visual Studio Code indica la riga in cui è impostato il punto di interruzione visualizzando un punto rosso nel margine sinistro.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="Set di punti di interruzione":::

## <a name="set-up-for-terminal-input"></a>Configurare per l'input del terminale

Il punto di interruzione si trova dopo una `Console.ReadLine` chiamata al metodo. Il **console di debug** non accetta l'input del terminale per un programma in esecuzione. Per gestire l'input del terminale durante il debug, è possibile usare il terminale integrato (uno dei Visual Studio Code Windows) o un terminale esterno. Per questa esercitazione si userà il terminale integrato.

1. Aprire *. VSCODE/Launch. JSON*.

1. Modificare l' `console` impostazione in `integratedTerminal` .

   Da:

   ```
   "console": "internalConsole",
   ```

   Con:

   ```
   "console": "integratedTerminal",
   ```

1. Salvare le modifiche.

## <a name="start-debugging"></a>Consente di iniziare il debug

1. Aprire la visualizzazione debug selezionando l'icona debug nel menu a sinistra.

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Aprire la scheda Debug in Visual Studio Code":::

1. Avviare il debug selezionando la freccia verde nella parte superiore del riquadro, accanto a **.NET Core Launch (console)**.  Un altro modo per avviare il debug è premere <kbd>F5</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="Consente di iniziare il debug":::

1. Selezionare la scheda **terminale** per visualizzare il nome dell'utente. richiede che il programma venga visualizzato prima dell'attesa di una risposta.

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="Selezionare la scheda terminale":::

1. Immettere una stringa nella finestra del **terminale** in risposta alla richiesta di un nome, quindi premere <kbd>invio</kbd>.

   L'esecuzione del programma si arresta quando raggiunge il punto di interruzione e prima che il metodo `Console.WriteLine` venga eseguito. Nella sezione variabili **locali** della finestra **variabili** vengono visualizzati i valori delle variabili definite nel metodo attualmente in esecuzione.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="Raggiunto punto di interruzione, che Mostra variabili locali":::

## <a name="change-variable-values"></a>Modificare i valori delle variabili

La finestra di **console di debug** consente di interagire con l'applicazione di cui si sta eseguendo il debug. È possibile modificare il valore delle variabili per vedere come influiscono sul programma.

1. Selezionare la scheda **console di debug** .

1. Immettere `name = "Gracie"` al prompt nella parte inferiore della finestra **console di debug** e premere il tasto <kbd>invio</kbd> .

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="Modificare i valori delle variabili":::

1. Immettere `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` nella parte inferiore della finestra di **console di debug** e premere il tasto <kbd>invio</kbd> .

   Nella finestra **variabili** vengono visualizzati i nuovi valori delle `name` `date` variabili e.

1. Continuare l'esecuzione del programma selezionando il pulsante **continua** sulla barra degli strumenti. Un altro modo per continuare è premere <kbd>F5</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="Continua debug":::

1. Selezionare di nuovo la scheda **terminale** .

   I valori visualizzati nella finestra della console corrispondono alle modifiche apportate nel **console di debug**.

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="Terminale che mostra i valori immessi":::

1. Premere un tasto qualsiasi per uscire dall'applicazione e arrestare il debug.

## <a name="set-a-conditional-breakpoint"></a>Impostare un punto di interruzione condizionale

Il programma Visualizza la stringa che l'utente immette. Ma cosa succede se l'utente non immette alcuna stringa? È possibile eseguire il test con una funzionalità di debug utile denominata punto di *interruzione condizionale*.

1. Fare clic con il pulsante destro del mouse (<kbd>CTRL</kbd>+ clic su MacOS) sul punto rosso che rappresenta il punto di interruzione. Nel menu di scelta rapida selezionare **modifica** punto di interruzione per aprire una finestra di dialogo che consente di immettere un'espressione condizionale.

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="Menu di scelta rapida Punto di interruzione":::

1. Selezionare `Expression` nell'elenco a discesa, immettere l'espressione condizionale seguente e premere <kbd>invio</kbd>.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="Immettere un'espressione condizionale":::

   Ogni volta che viene raggiunto il punto di interruzione, il debugger chiama il `String.IsNullOrEmpty(name)` metodo e si interrompe in questa riga solo se la chiamata al metodo restituisce `true` .

   Anziché un'espressione condizionale, è possibile specificare un numero di *passaggi*, che interrompe l'esecuzione del programma prima che un'istruzione venga eseguita un numero specificato di volte o una *condizione di filtro*, che interrompe l'esecuzione del programma in base a tali attributi come identificatore del thread, nome del processo o nome del thread.

1. Avviare il programma con il debug premendo <kbd>F5</kbd>.

1. Nella scheda **terminale** premere il tasto <kbd>invio</kbd> quando viene richiesto di immettere il nome.

   Poiché la condizione specificata ( `name` is `null` o <xref:System.String.Empty?displayProperty=nameWithType> ) è stata soddisfatta, l'esecuzione del programma si interrompe quando raggiunge il punto di interruzione e prima che venga eseguito il `Console.WriteLine` metodo.

   La finestra **variabili** Mostra che il valore della `name` variabile è `""` o <xref:System.String.Empty?displayProperty=nameWithType> .

1. Confermare che il valore è una stringa vuota immettendo l'istruzione seguente al prompt dei **console di debug** e premendo <kbd>invio</kbd>. Il risultato è `true`.

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="Console di debug la restituzione di un valore true dopo l'esecuzione dell'istruzione":::

1. Selezionare il pulsante **Continua** sulla barra degli strumenti per continuare l'esecuzione del programma.

1. Selezionare la scheda **terminale** e premere un tasto qualsiasi per uscire dal programma e arrestare il debug.

1. Cancellare il punto di interruzione facendo clic sul punto sul margine sinistro della finestra del codice. Un altro modo per cancellare un punto di interruzione consiste nel premere <kbd>F9</kbd> mentre è selezionata la riga di codice.

1. Se viene visualizzato un avviso che indica che la condizione del punto di interruzione andrà persa, selezionare Rimuovi punto di **interruzione**.

## <a name="step-through-a-program"></a>Scorrere un programma

Visual Studio Code consente inoltre di passare riga per riga attraverso un programma e monitorarne l'esecuzione. In genere, si imposta un punto di interruzione e si segue il flusso del programma attraverso una piccola parte del codice programma. Poiché questo programma è di piccole dimensioni, è possibile eseguire l'intero programma.

1. Impostare un punto di interruzione sulla parentesi graffa di apertura del `Main` metodo.

1. Premere <kbd>F5</kbd> per avviare il debug.

   Visual Studio Code evidenzia la riga del punto di interruzione.

   A questo punto, nella finestra **variabili** viene indicato che la `args` matrice è vuota e `name` e `date` hanno valori predefiniti.

1. Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="Pulsante Esegui istruzione":::

   Visual Studio Code evidenzia la riga successiva.

1. Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.

   Visual Studio Code esegue `Console.WriteLine` per la richiesta del nome ed evidenzia la riga successiva di esecuzione. La riga successiva è `Console.ReadLine` per `name` . La finestra **variabili** è invariata e la scheda **terminale** Mostra "Qual è il nome?" prompt.

1. Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.

   Visual Studio evidenzia l' `name` assegnazione della variabile. La finestra **variabili** Mostra che `name` è ancora `null` .

1. Per rispondere alla richiesta, immettere una stringa nella scheda terminale e premere <kbd>invio</kbd>.

   La scheda **terminale** potrebbe non visualizzare la stringa immessa durante l'immissione, ma il <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> Metodo acquisirà l'input.

1. Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.

   Visual Studio Code evidenzia l' `date` assegnazione della variabile. Nella finestra **variabili** viene visualizzato il valore restituito dalla chiamata al <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> metodo. Nella scheda **terminale** viene visualizzata la stringa immessa al prompt.

1. Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.

   Nella finestra **variabili** viene visualizzato il valore della `date` variabile dopo l'assegnazione dalla <xref:System.DateTime.Now?displayProperty=nameWithType> Proprietà.

1. Selezionare **Esegui istruzione** o premere <kbd>F11</kbd>.

   Visual Studio Code chiama il <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> metodo. Nella finestra della console viene visualizzata la stringa formattata.

1. Selezionare **Esci da istruzione/uscita** o premere <kbd>MAIUSC</kbd> + <kbd>F11</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="Pulsante Esci da istruzione/uscita":::

1. Selezionare la scheda **terminale** .

   Il terminale Visualizza "premere un tasto qualsiasi per uscire..."

1. Premere un tasto qualsiasi per uscire dal programma.

## <a name="select-release-build-configuration"></a>Selezionare la configurazione della build di rilascio

Dopo aver testato la versione di debug dell'applicazione, è necessario compilare e testare anche la versione di rilascio. La versione di rilascio incorpora le ottimizzazioni del compilatore che possono influire sul comportamento di un'applicazione. Ad esempio, le ottimizzazioni del compilatore progettate per migliorare le prestazioni possono creare race condition nelle applicazioni multithread.

Per compilare e testare la versione di rilascio dell'applicazione console, aprire il **terminale** ed eseguire il comando seguente:

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a>Risorse aggiuntive

* [Debugging in Visual Studio Code (Debug in Visual Studio Code)](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono stati usati Visual Studio Code strumenti di debug. Nell'esercitazione successiva si pubblica una versione distribuibile dell'app.

> [!div class="nextstepaction"]
> [Pubblicare un'applicazione console .NET Core con Visual Studio Code](publishing-with-visual-studio-code.md)

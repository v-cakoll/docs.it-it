---
title: Flusso di controllo in programmi asincroni
ms.date: 07/20/2015
ms.assetid: b0443af7-c586-4cb0-b476-742ae4098a96
ms.openlocfilehash: 0c479b9dd2a691b1b353fac54ee3320a895b1c7f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396662"
---
# <a name="control-flow-in-async-programs-visual-basic"></a>Flusso di controllo in programmi asincroni (Visual Basic)

Le parole chiave `Async` e `Await` consentono di scrivere e gestire più facilmente i programmi asincroni. Tuttavia, i risultati potrebbero creare perplessità se non si conosce il funzionamento del programma. Questo argomento descrive il flusso di controllo attraverso un programma asincrono semplice per indicare quando il controllo si sposta da un metodo a un altro e quali informazioni vengono trasferite ogni volta.

> [!NOTE]
> Le parole chiave `Async` e `Await` sono state introdotte in Visual Studio 2012.

In generale, si contrassegnano i metodi che contengono codice asincrono con il modificatore [Async](../../../language-reference/modifiers/async.md) . In un metodo contrassegnato con un modificatore async, è possibile usare un operatore [await (Visual Basic)](../../../language-reference/operators/await-operator.md) per specificare dove il metodo viene sospeso per attendere il completamento di un processo asincrono chiamato. Per ulteriori informazioni, vedere [programmazione asincrona con Async e await (Visual Basic)](index.md).

L'esempio seguente usa i metodi asincroni per scaricare come stringa il contenuto di un sito Web specificato e per visualizzare la lunghezza della stringa. L'esempio contiene i due metodi seguenti.

- `startButton_Click`, che chiama `AccessTheWebAsync` e visualizza il risultato.

- `AccessTheWebAsync`, che scarica il contenuto di un sito Web come stringa e restituisce la lunghezza della stringa. `AccessTheWebAsync` usa un metodo <xref:System.Net.Http.HttpClient> asincrono, ovvero <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>, per scaricare il contenuto.

In corrispondenza dei punti strategici del programma sono visualizzate righe numerate che consentono di comprendere come viene eseguito il programma e spiegano che cosa accade in ogni punto contrassegnato. Le righe sono evidenziate con etichette numerate da "ONE" a "SIX." Le etichette rappresentano l'ordine in cui il programma raggiunge queste righe di codice.

Il codice seguente rappresenta una struttura del programma.

```vb
Class MainWindow

    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click

        ' ONE
        Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()

        ' FOUR
        Dim contentLength As Integer = Await getLengthTask

        ' SIX
        ResultsTextBox.Text &=
            vbCrLf & $"Length of the downloaded string: {contentLength}." & vbCrLf

    End Sub

    Async Function AccessTheWebAsync() As Task(Of Integer)

        ' TWO
        Dim client As HttpClient = New HttpClient()
        Dim getStringTask As Task(Of String) =
            client.GetStringAsync("https://msdn.microsoft.com")

        ' THREE
        Dim urlContents As String = Await getStringTask

        ' FIVE
        Return urlContents.Length
    End Function

End Class
```

Ognuna delle posizioni con etichetta da "ONE" a "SIX" visualizza informazioni sullo stato corrente del programma. Viene generato l'output seguente:

```console
ONE:   Entering startButton_Click.
           Calling AccessTheWebAsync.

TWO:   Entering AccessTheWebAsync.
           Calling HttpClient.GetStringAsync.

THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.

FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.

FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.

SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.

Length of the downloaded string: 33946.
```

## <a name="set-up-the-program"></a>Impostare il programma

È possibile scaricare il codice usato in questo argomento da MSDN oppure crearlo manualmente.

> [!NOTE]
> Per eseguire l'esempio, è necessario che nel computer sia installato Visual Studio 2012 o versione successiva e il .NET Framework 4,5 o versione successiva.

### <a name="download-the-program"></a>Scaricare il programma

È possibile scaricare l'applicazione di questo argomento da [Async Sample: Control Flow in Async Programs](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) (Esempio di attività asincrona: flusso di controllo in programmi asincroni). I passaggi seguenti consentono di aprire ed eseguire il programma.

1. Decomprimere il file scaricato e quindi avviare Visual Studio.

2. Nella barra dei menu scegliere **File**, **Apri**, **Progetto/Soluzione**.

3. Passare alla cartella che contiene il codice di esempio decompresso, aprire il file della soluzione (SLN) e quindi scegliere il tasto F5 per compilare ed eseguire il progetto.

### <a name="build-the-program-yourself"></a>Compilare il programma autonomamente

Il seguente progetto Windows Presentation Foundation (WPF) contiene gli esempi di codice per questo argomento.

Per eseguire il progetto, effettuare i passaggi seguenti:

1. Avviare Visual Studio.

2. Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.

    Verrà visualizzata la finestra di dialogo **Nuovo progetto** .

3. Nel riquadro **modelli installati** scegliere **Visual Basic**, quindi scegliere **applicazione WPF** dall'elenco dei tipi di progetto.

4. Immettere `AsyncTracer` come nome del progetto, quindi scegliere il pulsante **OK**.

    Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.

5. Nell'Editor di codice di Visual Studio scegliere la scheda **MainWindow.xaml** .

    Se la scheda non è visibile, aprire il menu di scelta rapida per MainWindow.xaml in **Esplora soluzioni** e scegliere **Visualizza codice**.

6. Nella visualizzazione **XAML** di MainWindow.xaml sostituire il codice con quello riportato di seguito.

    ```vb
    <Window
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d" x:Class="MainWindow"
        Title="Control Flow Trace" Height="350" Width="525">
        <Grid>
            <Button x:Name="StartButton" Content="Start" HorizontalAlignment="Left" Margin="221,10,0,0" VerticalAlignment="Top" Width="75"/>
            <TextBox x:Name="ResultsTextBox" HorizontalAlignment="Left" TextWrapping="Wrap" VerticalAlignment="Bottom" Width="510" Height="265" FontFamily="Lucida Console" FontSize="10" VerticalScrollBarVisibility="Visible" d:LayoutOverrides="HorizontalMargin"/>

        </Grid>
    </Window>
    ```

    Nella visualizzazione **Progettazione** di MainWindow.xaml viene visualizzata una finestra semplice contenente una casella di testo e un pulsante.

7. Aggiunge un riferimento a <xref:System.Net.Http>.

8. In **Esplora soluzioni**aprire il menu di scelta rapida per MainWindow. XAML. vb, quindi scegliere **Visualizza codice**.

9. In MainWindow. XAML. vb sostituire il codice con il codice seguente.

    ```vb
    ' Add an Imports statement and a reference for System.Net.Http.
    Imports System.Net.Http

    Class MainWindow

        Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs) Handles StartButton.Click

            ' The display lines in the example lead you through the control shifts.
            ResultsTextBox.Text &= "ONE:   Entering StartButton_Click." & vbCrLf &
                "           Calling AccessTheWebAsync." & vbCrLf

            Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()

            ResultsTextBox.Text &= vbCrLf & "FOUR:  Back in StartButton_Click." & vbCrLf &
                "           Task getLengthTask is started." & vbCrLf &
                "           About to await getLengthTask -- no caller to return to." & vbCrLf

            Dim contentLength As Integer = Await getLengthTask

            ResultsTextBox.Text &= vbCrLf & "SIX:   Back in StartButton_Click." & vbCrLf &
                "           Task getLengthTask is finished." & vbCrLf &
                "           Result from AccessTheWebAsync is stored in contentLength." & vbCrLf &
                "           About to display contentLength and exit." & vbCrLf

            ResultsTextBox.Text &=
                String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)
        End Sub

        Async Function AccessTheWebAsync() As Task(Of Integer)

            ResultsTextBox.Text &= vbCrLf & "TWO:   Entering AccessTheWebAsync."

            ' Declare an HttpClient object.
            Dim client As HttpClient = New HttpClient()

            ResultsTextBox.Text &= vbCrLf & "           Calling HttpClient.GetStringAsync." & vbCrLf

            ' GetStringAsync returns a Task(Of String).
            Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")

            ResultsTextBox.Text &= vbCrLf & "THREE: Back in AccessTheWebAsync." & vbCrLf &
                "           Task getStringTask is started."

            ' AccessTheWebAsync can continue to work until getStringTask is awaited.

            ResultsTextBox.Text &=
                vbCrLf & "           About to await getStringTask & return a Task(Of Integer) to StartButton_Click." & vbCrLf

            ' Retrieve the website contents when task is complete.
            Dim urlContents As String = Await getStringTask

            ResultsTextBox.Text &= vbCrLf & "FIVE:  Back in AccessTheWebAsync." &
                vbCrLf & "           Task getStringTask is complete." &
                vbCrLf & "           Processing the return statement." &
                vbCrLf & "           Exiting from AccessTheWebAsync." & vbCrLf

            Return urlContents.Length
        End Function

    End Class
    ```

10. Premere F5 per eseguire il programma e quindi scegliere il pulsante **Avvia**.

    Verrà visualizzato l'output seguente:

    ```console
    ONE:   Entering startButton_Click.
               Calling AccessTheWebAsync.

    TWO:   Entering AccessTheWebAsync.
               Calling HttpClient.GetStringAsync.

    THREE: Back in AccessTheWebAsync.
               Task getStringTask is started.
               About to await getStringTask & return a Task<int> to startButton_Click.

    FOUR:  Back in startButton_Click.
               Task getLengthTask is started.
               About to await getLengthTask -- no caller to return to.

    FIVE:  Back in AccessTheWebAsync.
               Task getStringTask is complete.
               Processing the return statement.
               Exiting from AccessTheWebAsync.

    SIX:   Back in startButton_Click.
               Task getLengthTask is finished.
               Result from AccessTheWebAsync is stored in contentLength.
               About to display contentLength and exit.

    Length of the downloaded string: 33946.
    ```

## <a name="trace-the-program"></a>Analizzare il programma

### <a name="steps-one-and-two"></a>Passaggi UNO e DUE

Le prime due righe di visualizzazione tracciano il percorso poiché `startButton_Click` chiama `AccessTheWebAsync` e `AccessTheWebAsync` chiama il metodo asincrono <xref:System.Net.Http.HttpClient>, ovvero <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29>. Nell'immagine seguente vengono illustrate le chiamate metodo a metodo.

![Passaggi UNO e DUE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-onetwo.png "AsyncTrace-ONETWO")

Il tipo restituito di `AccessTheWebAsync` e `client.GetStringAsync` è <xref:System.Threading.Tasks.Task%601>. Per `AccessTheWebAsync` TResult è un numero intero. Per `GetStringAsync` TResult è una stringa. Per ulteriori informazioni sui tipi restituiti del metodo asincrono, vedere [tipi restituiti asincroni (Visual Basic)](async-return-types.md).

Un metodo asincrono che restituisce un'attività restituisce un'istanza dell'attività quando il controllo torna al chiamante. Il controllo viene restituito da un metodo asincrono al relativo chiamante quando viene rilevato un operatore `Await` nel metodo chiamato o quando termina il metodo chiamato. Le righe evidenziate con le etichette da "THREE" a "SIX" analizzano questa parte del processo.

### <a name="step-three"></a>Passaggio TRE

In `AccessTheWebAsync`, il metodo asincrono <xref:System.Net.Http.HttpClient.GetStringAsync%28System.String%29> viene chiamato per scaricare il contenuto della pagina Web di destinazione. Il controllo viene restituito da `client.GetStringAsync` a `AccessTheWebAsync` quando viene restituito `client.GetStringAsync`.

Il metodo `client.GetStringAsync` restituisce un'attività di stringa che viene assegnata alla variabile `getStringTask` in `AccessTheWebAsync`. La riga seguente nel programma di esempio indica la chiamata a `client.GetStringAsync` e l'assegnazione.

```vb
Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")
```

Si può pensare all'attività come a una promessa fatta da `client.GetStringAsync` di produrre una stringa reale alla fine. Nel frattempo, se `AccessTheWebAsync` ha del lavoro da svolgere che non dipende dalla stringa promessa da `client.GetStringAsync`, il lavoro può continuare mentre `client.GetStringAsync` rimane in attesa. Nell'esempio, le righe di output seguenti, che sono contrassegnate con "THREE", rappresentano la possibilità di eseguire operazioni indipendenti

```console
THREE: Back in AccessTheWebAsync.
           Task getStringTask is started.
           About to await getStringTask & return a Task<int> to startButton_Click.
```

 L'istruzione seguente sospende lo stato di avanzamento in `AccessTheWebAsync` quando si attende `getStringTask`.

```vb
Dim urlContents As String = Await getStringTask
```

Nell'immagine seguente viene illustrato il flusso di controllo da `client.GetStringAsync` all'assegnazione a `getStringTask` e dalla creazione di `getStringTask` all'applicazione di un operatore await.

![TERZO passaggio](../../../../csharp/programming-guide/concepts/async/media/asynctrace-three.png "AsyncTrace-tre")

L'espressione await sospende `AccessTheWebAsync` finché non viene restituito `client.GetStringAsync`. Nel frattempo il controllo viene restituito al chiamante di `AccessTheWebAsync`, `startButton_Click`.

> [!NOTE]
> In genere, la chiamata a un metodo asincrono si attende immediatamente. Ad esempio, l'assegnazione seguente potrebbe sostituire il codice precedente che crea e quindi attende `getStringTask`:`Dim urlContents As String = Await client.GetStringAsync("https://msdn.microsoft.com")`
>
> In questo argomento l'operatore await viene applicato in un secondo tempo per contenere le righe di output che indicano il flusso di controllo attraverso il programma.

### <a name="step-four"></a>Passaggio QUATTRO

Il tipo restituito dichiarato di `AccessTheWebAsync` è `Task(Of Integer)`. Di conseguenza, quando `AccessTheWebAsync` è sospeso, restituisce un'attività di valori integer a `startButton_Click`. È necessario comprendere che l'attività restituita non è `getStringTask`. L'attività restituita è una nuova attività di valori integer che rappresenta ciò che resta da eseguire nel metodo sospeso, `AccessTheWebAsync`. L'attività è una promessa da parte di `AccessTheWebAsync` di produrre un numero intero al termine dell'attività.

L'istruzione seguente assegna questa attività alla variabile `getLengthTask`.

```vb
Dim getLengthTask As Task(Of Integer) = AccessTheWebAsync()
```

Come in `AccessTheWebAsync`, `startButton_Click` può continuare a eseguire operazioni che non dipendono dai risultati dell'attività asincrona (`getLengthTask`) finché si è in attesa dell'attività. Le seguenti righe di output rappresentano il lavoro:

```console
FOUR:  Back in startButton_Click.
           Task getLengthTask is started.
           About to await getLengthTask -- no caller to return to.
```

Lo stato di avanzamento in `startButton_Click` viene sospeso quando si attende `getLengthTask`. La seguente istruzione di assegnazione sospende `startButton_Click` finché non si completa `AccessTheWebAsync`.

```vb
Dim contentLength As Integer = Await getLengthTask
```

Nella figura seguente le frecce indicano il flusso di controllo dall'espressione await in `AccessTheWebAsync` all'assegnazione di un valore a `getLengthTask`, seguita dall'elaborazione normale in `startButton_Click` finché si è in attesa di `getLengthTask`.

![Passaggio quattro](../../../../csharp/programming-guide/concepts/async/media/asynctrace-four.png "AsyncTrace-quattro")

### <a name="step-five"></a>Passaggio CINQUE

Quando l'attività `client.GetStringAsync` segnala il proprio completamento, l'elaborazione in `AccessTheWebAsync` viene rilasciata dalla sospensione e può continuare oltre l'istruzione await. Le seguenti righe di output rappresentano la ripresa dell'elaborazione:

```console
FIVE:  Back in AccessTheWebAsync.
           Task getStringTask is complete.
           Processing the return statement.
           Exiting from AccessTheWebAsync.
```

L'operando dell'istruzione return, `urlContents.Length`, viene archiviato nell'attività restituita da `AccessTheWebAsync`. L'espressione await recupera tale valore da `getLengthTask` in `startButton_Click`.

L'immagine seguente illustra il trasferimento del controllo dopo il completamento di `client.GetStringAsync` (e `getStringTask`).

![Passaggio CINQUE](../../../../csharp/programming-guide/concepts/async/media/asynctrace-five.png "AsyncTrace-cinque")

`AccessTheWebAsync` viene eseguita fino al completamento e il controllo viene restituito a `startButton_Click`, che è in attesa del completamento.

### <a name="step-six"></a>Passaggio SEI

Quando l'attività `AccessTheWebAsync` segnala il proprio completamento, l'elaborazione può continuare oltre l'istruzione await in `startButton_Async`. Di fatto il programma non ha altre operazioni da eseguire.

Le seguenti righe di output rappresentano la ripresa dell'elaborazione in `startButton_Async`:

```console
SIX:   Back in startButton_Click.
           Task getLengthTask is finished.
           Result from AccessTheWebAsync is stored in contentLength.
           About to display contentLength and exit.
```

L'espressione await recupera da `getLengthTask` il valore integer che rappresenta l'operando dell'istruzione return in `AccessTheWebAsync`. L'istruzione seguente assegna tale valore alla variabile `contentLength`.

```vb
Dim contentLength As Integer = Await getLengthTask
```

La figura seguente illustra la restituzione del controllo da `AccessTheWebAsync` a `startButton_Click`.

![Passaggio SEI](../../../../csharp/programming-guide/concepts/async/media/asynctrace-six.png "AsyncTrace-sei")

## <a name="see-also"></a>Vedere anche

- [Programmazione asincrona con Async e Await (Visual Basic)](index.md)
- [Tipi restituiti asincroni (Visual Basic)](async-return-types.md)
- [Procedura dettagliata: accesso al Web con Async e Await (Visual Basic)](walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Async Sample: Control Flow in Async Programs (C# and Visual Basic)](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0) (Esempio di attività asincrona: Flusso di controllo in programmi asincroni (C# e Visual Basic))

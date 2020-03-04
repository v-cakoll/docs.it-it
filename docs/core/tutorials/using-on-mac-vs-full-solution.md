---
title: Creare una soluzione .NET Core completa usando Visual Studio per Mac
description: Questo articolo illustra la creazione di una soluzione .NET Core che include una libreria riutilizzabile e un unit test.
ms.date: 12/19/2019
ms.openlocfilehash: 8c9fcca404a3875b6bb7f9cf20551a017ff553c5
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "78239963"
---
# <a name="build-a-complete-net-core-solution-on-macos-using-visual-studio-for-mac"></a>Creare una soluzione .NET Core completa in macOS usando Visual Studio per Mac

Visual Studio per Mac offre un ambiente di sviluppo integrato completo per lo sviluppo di applicazioni .NET Core. Questo articolo illustra la creazione di una soluzione .NET Core che include una libreria riutilizzabile e un unit test.

In questa esercitazione viene illustrato come creare un'applicazione che accetta una parola di ricerca e una stringa di testo dall'utente, conta il numero di volte in cui la parola di ricerca appare nella stringa usando un metodo in una libreria di classi e restituisce il risultato all'utente. La soluzione include anche unit test per la libreria di classi come introduzione ai concetti relativi al testing unità. Se si preferisce continuare l'esercitazione con un esempio completo, scaricare la [soluzione di esempio](https://github.com/dotnet/samples/blob/master/core/tutorials/using-on-mac-vs-full-solution/WordCounter). Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

> [!NOTE]
> Microsoft considera di fondamentale importanza i commenti e i suggerimenti degli utenti. Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:
>
> - In Visual Studio per Mac scegliere **Aiuto** > **Segnala un problema** dal menu o **Segnala un problema** dalla schermata iniziale per visualizzare una finestra per la registrazione di un report sul bug. È possibile tenere traccia dei commenti e dei suggerimenti inviati nel portale della [community di sviluppatori](https://developercommunity.visualstudio.com/spaces/41/index.html).
> - Per inviare un suggerimento, scegliere **Aiuto** > **Invia un suggerimento** dal menu o **Invia un suggerimento** dalla schermata iniziale per aprire la [pagina Web Developer Community di Visual Studio per Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Prerequisites

- [.NET Core SDK 3,1 o versione successiva](https://dotnet.microsoft.com/download)
- [Visual Studio 2019 per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

Per ulteriori informazioni sui prerequisiti, vedere le [dipendenze e i requisiti di .NET Core](../install/dependencies.md?pivots=os-macos). Per i requisiti di sistema completi di Visual Studio 2019 per Mac, vedere requisiti di sistema per la [famiglia di prodotti Visual studio 2019 per Mac](/visualstudio/productinfo/vs2019-system-requirements-mac).

## <a name="building-a-library"></a>Creazione di una libreria

1. Nella finestra Start selezionare **nuovo progetto**. Nella finestra di dialogo **Nuovo progetto**, nel nodo **.NET Core**, selezionare il modello **Libreria .NET Standard**. Questo comando crea una libreria di .NET Standard destinata a .NET Core e a qualsiasi altra implementazione di .NET che supporta la versione 2,1 del [.NET standard](../../standard/net-standard.md). Se sono installate più versioni del .NET Core SDK, è possibile scegliere diverse versioni di .NET Standard per la libreria. Scegliere ".NET Standard 2,1" e fare clic su **Avanti**.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac finestra di dialogo nuovo progetto](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project.png)

1. Assegnare al progetto il nome "TextUtils" (nome breve per "Text Utilities") e alla soluzione il nome "WordCounter". Lasciare selezionata la casella **Crea una directory del progetto nella directory della soluzione**. Selezionare **Create** (Crea).

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac opzioni della finestra di dialogo nuovo progetto](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-options.png)

1. Nel riquadro della **soluzione** espandere il nodo `TextUtils` per visualizzare il file di classe fornito dal modello, *Class1.cs*. Fare clic con il pulsante destro del mouse sul file, scegliere **Rinomina** dal menu di scelta rapida e rinominare il file in *WordCount.cs*. Aprire il file e sostituire il contenuto con il codice seguente:

   [!code-csharp[Main](../../../samples/snippets/core/tutorials/using-on-mac-vs-full-solution/csharp/TextUtils/WordCount.cs)]

1. Salvare il file usando uno dei tre metodi seguenti: usare i tasti di scelta <kbd>&#8984;</kbd> rapida+<kbd>s</kbd>, selezionare **file** > **Salva** dal menu o fare clic con il pulsante destro del mouse sulla scheda del file e scegliere **Salva** dal menu contestuale. Nell'immagine seguente viene visualizzata la finestra dell'IDE:

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac finestra IDE con il metodo e il file della libreria di classi](./media/using-on-mac-vs-full-solution/visual-studio-mac-editor.png)

1. Selezionare **Errori** nel margine inferiore della finestra dell'IDE per aprire il pannello **Errori**. Selezionare il pulsante **Output di compilazione**.

   > [!div class="mx-imgBorder"]
   > ![margine inferiore dell'IDE Mac di Visual Studio che mostra il pulsante errori](./media/using-on-mac-vs-full-solution/visual-studio-mac-error-button.png)

1. Scegliere **Compila** > **Compila tutto** dal menu.

   La soluzione viene compilata e il riquadro dell'output di compilazione indica che la compilazione ha avuto esito positivo.

   > [!div class="mx-imgBorder"]
   > ![riquadro di output di compilazione Mac di Visual Studio del pannello Errori con messaggio di compilazione completata](./media/using-on-mac-vs-full-solution/visual-studio-mac-build-panel.png)

## <a name="creating-a-test-project"></a>Creazione di un progetto di test

Gli unit test forniscono test software automatici durante le fasi di sviluppo e pubblicazione. Il Framework di test usato in questa esercitazione è [xUnit (versione 2.4.0 o successiva)](https://xunit.github.io/), che viene installato automaticamente quando il progetto di test xUnit viene aggiunto alla soluzione nei passaggi seguenti:

1. Nella barra laterale della **soluzione** fare clic con il pulsante destro del mouse sulla soluzione `WordCounter` e scegliere **Aggiungi** > **Aggiungi nuovo progetto**.

1. Nella finestra di dialogo **Nuovo progetto** selezionare **Test** sotto il nodo **.NET Core**. Selezionare **xUnit Test Project** (Progetto di test xUnit) e quindi scegliere **Avanti**.

   > [!div class="mx-imgBorder"]
   > ![finestra di dialogo nuovo progetto di Visual Studio Mac Creazione del progetto di test xUnit](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-project.png)

1. Se sono disponibili più versioni del .NET Core SDK, è necessario selezionare la versione per questo progetto. Selezionare **.NET Core 3,1**. Assegnare al nuovo progetto il nome "TestLibrary" e scegliere **Crea**.

   > [!div class="mx-imgBorder"]
   > ![finestra di dialogo nuovo progetto di Visual Studio Mac che fornisce il nome del progetto](./media/using-on-mac-vs-full-solution/visual-studio-mac-new-project-name.png)

1. Aggiungere un riferimento al progetto `WordCount` per consentire l'interazione tra la libreria di test e la classe `TextUtils`. Nella barra laterale della **soluzione** , fare clic su **dipendenze** sotto **TestLibrary**. Scegliere **Modifica riferimenti** dal menu di scelta rapida.

1. Nella finestra di dialogo **modifica riferimenti** selezionare il progetto **TextUtils** nella scheda **progetti** . Selezionare **OK**.

   > [!div class="mx-imgBorder"]
   > ![finestra di dialogo Modifica riferimenti di Visual Studio Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-edit-references.png)

1. Nel progetto **TestLibrary** rinominare il file *UnitTest1.cs* in *TextUtilsTests.cs*.

1. Aprire il file e sostituire il codice con il codice seguente:

   ```csharp
   using Xunit;
   using TextUtils;
   using System.Diagnostics;

   namespace TestLibrary
   {
       public class TextUtils_GetWordCountShould
       {
           [Fact]
           public void IgnoreCasing()
           {
               var wordCount = WordCount.GetWordCount("Jack", "Jack jack");

               Assert.NotEqual(2, wordCount);
           }
       }
   }
   ```

   Nell'immagine seguente viene visualizzato l'IDE con il codice dell'unit test. Prestare attenzione all'istruzione `Assert.NotEqual`.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac unit test iniziale nella finestra principale dell'IDE](./media/using-on-mac-vs-full-solution/visual-studio-mac-assert-test.png)

   È importante fare in modo che il nuovo test la prima volta abbia esito negativo per verificare che la logica di test sia corretta. Il metodo passa il nome "Jack" (lettere maiuscole) e una stringa con "Jack" e "jack" (lettere maiuscole e minuscole). Se il metodo `GetWordCount` funziona correttamente, viene restituito un conteggio di due istanze della parola di ricerca. Per fare in modo che il test non riesca, è necessario prima implementare il test asserendo che dal metodo `GetWordCount` non vengono restituite due istanze della parola di ricerca "Jack". Andare quindi al passaggio successivo per fare in modo che il test abbia esito negativo.

1. Aprire il pannello **Unit test** sul lato destro dello schermo. Selezionare **visualizza** > **test** dal menu.

   > [!div class="mx-imgBorder"]
   > ![pannello unit test Visual Studio per Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-panel.png)

1. Fare clic sull'icona **Ancora** per mantenere aperto il pannello. (Evidenziato nella figura seguente).

   > [!div class="mx-imgBorder"]
   > icona di ancoraggio del pannello unit test ![Visual Studio per Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-dock-icon.png)

1. Fare clic sul pulsante **Esegui tutto**.

   Il test ha esito negativo, che è il risultato previsto. Il metodo di test indica che dalla stringa "Jack Jack" fornita al metodo `inputString` non vengono restituite due istanze della stringa `GetWordCount`, "Jack". Poiché nel metodo `GetWordCount` è stato escluso l'uso delle maiuscole/minuscole, vengono invece restituite due istanze. L'asserzione che 2 *non è uguale a* 2 ha esito negativo. Questo risultato è il risultato corretto e la logica del test è valida.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac visualizzazione errore test](./media/using-on-mac-vs-full-solution/visual-studio-for-mac-unit-test-failure.png)

1. Modificare il metodo di test `IgnoreCasing` sostituendo `Assert.NotEqual` con `Assert.Equal`. Salvare il file usando il tasto di scelta rapida <kbd>Ctrl</kbd>+<kbd>s</kbd>, scegliere **file** > **Salva** dal menu o fare clic con il pulsante destro del mouse sulla scheda del file e scegliere **Salva** dal menu di scelta rapida.

   Si prevede che l'oggetto `searchWord` "Jack" restituisca due istanze con la stringa `inputString` "Jack jack" passata a `GetWordCount`. Eseguire di nuovo il test: fare clic sul pulsante **Esegui test** nel pannello **Unit test** o sul pulsante **Riesegui test** nel pannello **Risultati test** nella parte inferiore della schermata. Il test viene superato. Nella stringa "Jack jack" (senza distinzione tra maiuscole e minuscole) sono presenti due istanze di "Jack" e l'asserzione del test è `true`.

   > [!div class="mx-imgBorder"]
   > visualizzazione ![Visual Studio per Mac test superati](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)

1. La restituzione di singoli valori di test con un oggetto `Fact` è solo una delle operazioni che è possibile eseguire con gli unit test. Grazie a un'altra tecnica molto efficace, è possibile eseguire il test di più valori contemporaneamente usando un oggetto `Theory`. Aggiungere il metodo seguente alla classe `TextUtils_GetWordCountShould`. Dopo aver aggiunto il metodo alla classe sono disponibili due metodi:

   ```csharp
   [Theory]
   [InlineData(0, "Ting", "Does not appear in the string.")]
   [InlineData(1, "Ting", "Ting appears once.")]
   [InlineData(2, "Ting", "Ting appears twice with Ting.")]
   public void CountInstancesCorrectly(int count,
                                       string searchWord,
                                       string inputString)
   {
       Assert.NotEqual(count, WordCount.GetWordCount(searchWord,
                                                  inputString));
   }
   ```

   `CountInstancesCorrectly` verifica che il metodo `GetWordCount` esegua il conteggio in modo corretto. L'oggetto `InlineData` fornisce un conteggio, una parola di ricerca e una stringa di input da verificare. Il metodo di test viene eseguito una volta per ogni riga di dati. Tenere presente che, ancora una volta, si sta asserendo un esito negativo prima di tutto tramite `Assert.NotEqual`, anche se si è certi che i conteggi dei dati siano corretti e che i valori corrispondano ai conteggi restituiti dal metodo `GetWordCount`. Anche se, in un primo momento, l'esecuzione del test con esito negativo sembra una perdita di tempo, la verifica della logica del test tramite la generazione di un esito negativo consente in realtà di attestarne la correttezza. Quando si riscontra un metodo di test che ha esito positivo quando invece dovrebbe avere esito negativo, si è trovato un bug nella logica del test. Vale quindi la pena eseguire questo passaggio ogni volta che si crea un metodo di test.

1. Salvare il file ed eseguire di nuovo i test. Il test delle maiuscole/minuscole ha esito positivo, mentre i tre test del conteggio hanno esito negativo. Questo risultato è esattamente quello che si prevede di eseguire.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac errore di test previsto](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-failure.png)

1. Modificare il metodo di test `CountInstancesCorrectly` sostituendo `Assert.NotEqual` con `Assert.Equal`. Salvare il file. Eseguire di nuovo i test. Tutti i test hanno esito positivo.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac sessioni di test previste](./media/using-on-mac-vs-full-solution/visual-studio-mac-unit-test-pass.png)

## <a name="adding-a-console-app"></a>Aggiunta di un'app console

1. Nella barra laterale della **soluzione** fare clic con il pulsante destro del mouse sulla soluzione `WordCounter`. Aggiungere un nuovo progetto **Applicazione console** selezionando il modello corrispondente dai modelli **.NET Core** > **App**. Selezionare **Avanti**. Assegnare al progetto il nome **WordCounterApp**. Scegliere **Crea** per creare il progetto nella soluzione.

1. Nella barra laterale **soluzioni** , fare clic con il pulsante destro del mouse sul nodo **dipendenze** del nuovo progetto **WordCounterApp** . Nella finestra di dialogo **Modifica riferimenti** selezionare **TextUtils** e scegliere **OK**.

1. Aprire il file *Program.cs*. Sostituire il codice con il codice seguente:

   [!code-csharp[Main](../../../samples/snippets/core/tutorials/using-on-mac-vs-full-solution/csharp/WordCounterApp/Program.cs)]

1. Fare clic con il pulsante destro del mouse sul progetto `WordCounterApp` e scegliere **Esegui progetto** dal menu di scelta rapida. Con l'app in esecuzione, specificare i valori relativi alla parola di ricerca e alla stringa di input quando vengono richiesti nella finestra della console. L'app indica il numero di volte in cui la parola di ricerca appare nella stringa.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac finestra della console che mostra l'app in esecuzione](./media/using-on-mac-vs-full-solution/visual-studio-mac-console-window.png)

1. Si esaminerà infine la funzionalità di debug con Visual Studio per Mac. Impostare un punto di interruzione nell'istruzione `Console.WriteLine` e selezionare il margine sinistro della riga 23. Verrà visualizzato un cerchio rosso accanto alla riga di codice. In alternativa, selezionare un punto qualsiasi nella riga di codice e scegliere **Esegui** > **Imposta/Rimuovi punto di interruzione** dal menu.

   > [!div class="mx-imgBorder"]
   > set di punti di interruzione ![Visual Studio per Mac](./media/using-on-mac-vs-full-solution/visual-studio-mac-breakpoint.png)

1. fare clic con il pulsante destro del mouse sul progetto `WordCounterApp`. Selezionare **Avvia progetto di debug** dal menu di scelta rapida. Quando si esegue l'app, immettere la parola di ricerca "cat" e "The dog chased the cat, but the cat escaped." come stringa in cui eseguire la ricerca. Quando viene raggiunta l'istruzione `Console.WriteLine`, l'esecuzione del programma si interrompe per consentire l'esecuzione dell'istruzione. Nella scheda **Variabili locali** sono presenti i valori `searchWord`, `inputString`, `wordCount` e `pluralChar`.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac esecuzione del programma debugger arrestato](./media/using-on-mac-vs-full-solution/visual-studio-mac-debugger.png)

1. Nel riquadro **Immediato** digitare "wordCount = 999;" e premere INVIO. Questo comando assegna un valore non sensato di 999 alla variabile `wordCount` che indica che è possibile sostituire i valori delle variabili durante il debug.

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac la modifica dei valori nella finestra di controllo immediato](./media/using-on-mac-vs-full-solution/visual-studio-mac-immediate-window.png)

1. Sulla barra degli strumenti fare clic sulla freccia per *continuare*. Esaminare l'output nella finestra della console. Viene visualizzato il valore non corretto 999 impostato durante il debug dell'app.

   > [!div class="mx-imgBorder"]
   > ![pulsante continua Visual Studio per Mac sulla barra degli strumenti](./media/using-on-mac-vs-full-solution/visual-studio-mac-toolbar.png)

   > [!div class="mx-imgBorder"]
   > ![Visual Studio per Mac output della finestra della console](./media/using-on-mac-vs-full-solution/visual-studio-mac-output.png)

È possibile usare lo stesso processo per eseguire il debug del codice usando il progetto unit test. Anziché avviare il progetto dell'app WordCount, fare clic con il pulsante destro del mouse sul progetto **libreria di test** e scegliere **Avvia progetto di debug** dal menu di scelta rapida. Visual Studio per Mac avvia il progetto di test con il debugger collegato. L'esecuzione si arresterà in corrispondenza di qualsiasi punto di interruzione aggiunto al progetto di test o al codice della libreria sottostante.

## <a name="see-also"></a>Vedere anche

- [Note sulla versione di Visual Studio 2019 per Mac](/visualstudio/releasenotes/vs2019-mac-relnotes)

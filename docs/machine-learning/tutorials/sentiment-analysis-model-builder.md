---
title: 'Esercitazione: Analizzare il sentiment - classificazione binariaTutorial: Analyze sentiment - binary classification'
description: Questa esercitazione illustra come creare un'applicazione Razor Pages che classifica il sentiment dai commenti del sito Web ed esegue l'azione appropriata. Il classificatore di valutazione binario usa Model Builder in Visual Studio.The binary sentiment classifier uses Model Builder in Visual Studio.
ms.date: 11/21/2019
author: luisquintanilla
ms.author: luquinta
ms.topic: tutorial
ms.custom: mvc,mlnet-tooling
ms.openlocfilehash: 7761240055c90ae9c713b1c460e9e83316d256f9
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278951"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-in-a-web-application-using-mlnet-model-builder"></a>Esercitazione: Analizzare il sentiment dei commenti del sito Web in un'applicazione Web utilizzando ML.NET Model Builder

Scopri come analizzare il sentiment dei commenti in tempo reale all'interno di un'applicazione Web.

Questa esercitazione illustra come creare un'applicazione ASP.NET Core Razor Pages che classifica il sentiment dei commenti del sito Web in tempo reale.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> - Creare un'applicazione ASP.NET Core Razor PagesCreate an ASP.NET Core Razor Pages application
> - Preparare e identificare i dati
> - Scegliere uno scenario
> - Caricare i dati
> - Eseguire il training del modello
> - Valutare il modello
> - Usare il modello per le stime

> [!NOTE]
> Il generatore di modelli è attualmente in anteprima.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/machinelearning-samples.You](https://github.com/dotnet/machinelearning-samples) can find the source code for this tutorial at the dotnet/machinelearning-samples repository.

## <a name="pre-requisites"></a>Prerequisiti

Per un elenco di prerequisiti e istruzioni di installazione, vedere la [Guida all'installazione del generatore di modelli](../how-to-guides/install-model-builder.md).

## <a name="create-a-razor-pages-application"></a>Creare un'applicazione Razor PagesCreate a Razor Pages application

1. Creare **un'applicazione ASP.NET pagine razor di base**.

    1. Aprire Visual Studio e selezionare **File > nuovo > progetto** dalla barra dei menu.
    1. Nella finestra di dialogo Nuovo progetto selezionare il nodo **Visual C#** seguito dal nodo **Web**.
    1. Selezionare quindi il modello di progetto **Applicazione Web ASP.NET Core**.
    1. Nella casella di testo **Nome** digitare "SentimentRazor".
    1. Assicurarsi che **l'opzione Inserisci soluzione e progetto nella stessa directory** sia **deselezionata** (VS 2019) o **l'opzione Crea directory per soluzione** sia **selezionata** (VS 2017).
    1. Selezionare il pulsante **OK.**
    1. Scegliere **Applicazione Web** nella finestra che visualizza i diversi tipi di ASP.NET progetti principali, quindi fare clic sul pulsante **OK.**

## <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

Scarica [Wikipedia disintossicazione set di dati](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv). Quando si apre la pagina Web, fare clic con il pulsante destro del mouse sulla pagina, selezionare **Salva con** nome e salvare il file in un punto qualsiasi del computer.

Ogni riga del set di dati *wikipedia-detox-250-line-data.tsv* rappresenta una revisione diversa lasciata da un utente su Wikipedia. La prima colonna rappresenta il sentiment del testo (0 è non tossico, 1 è tossico) e la seconda colonna rappresenta il commento lasciato dall'utente. Le colonne sono separate da tabulazioni. I dati sono simili ai seguenti:

| Valutazione | SentimentText |
| :---: | :---: |
1 | Amico, sei un caricamento maleducato che l'immagine di Carl indietro, altrimenti.
1 | " OK! IM GOING TO VANDALIzeI WILD ONES WIKI THEN!!!
0 | Spero che questo aiuti.

## <a name="choose-a-scenario"></a>Scegliere uno scenario

![Creazione guidata Generatore di modelli in Visual StudioModel Builder wizard in Visual Studio](./media/sentiment-analysis-model-builder/model-builder-screen.png)

Per eseguire il training del modello, è necessario scegliere uno scenario di Machine Learning disponibile nell'elenco del generatore di modelli.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto *SentimentRazor* e scegliere **Aggiungi** > **Machine Learning**.
1. Per questo esempio, lo scenario è l'analisi del sentiment. Nel passaggio *dello scenario* dello strumento Generatore di modelli, selezionare lo scenario Analisi **del sentiment.**

## <a name="load-the-data"></a>Caricare i dati

Model Builder accetta dati da due origini, un database `csv` `tsv` di SQL Server o un file locale in o formato.

1. Nel passaggio relativo ai dati dello strumento generatore di modelli selezionare **File** dall'elenco a discesa delle origini dati.
1. Selezionare il pulsante accanto alla casella di testo **Selezionare un file** e utilizzare Esplora file per sfogliare e selezionare il file *wikipedia-detox-250-line-data.tsv.*
1. Scegli **Valutazione** nell'elenco a discesa **Colonna da prevedere (etichetta).**
1. Lasciare i valori predefiniti per l'elenco a discesa **Colonne di input (funzionalità).**
1. Selezionare il collegamento **Train** per passare al passaggio successivo nello strumento Generatore di modelli.

## <a name="train-the-model"></a>Eseguire il training del modello

L'attività di apprendimento automatico usata per eseguire il training del modello di analisi del sentiment in questa esercitazione è la classificazione binaria. Durante il processo di training del modello, Model Builder esegue il training di modelli separati usando algoritmi e impostazioni di classificazione binaria diversi per trovare il modello con le prestazioni migliori per il set di dati.

Il tempo necessario per l'esecuzione del training di ogni modello è proporzionato alla quantità di dati. Model Builder seleziona automaticamente un valore predefinito per **Time to train (seconds)** in base alle dimensioni dell'origine dati.

1. Anche se Model Builder imposta il valore di **Time to train (secondi)** su 10 secondi, aumentarlo a 30 secondi. Il training per un periodo di tempo più lungo consente a Model Builder di esplorare un numero maggiore di algoritmi e una combinazione di parametri alla ricerca del modello migliore.
1. Selezionare **Start Training** (Avvia training).

    Durante il processo di training i dati dell'avanzamento vengono visualizzati nella sezione `Progress` del passaggio relativo al training.

    - Stato visualizza lo stato di completamento del processo di training.
    - Precisione migliore visualizza la precisione del modello con le prestazioni migliori individuato dal generatore di modelli. Precisione maggiore indica il modello stimato più correttamente con i dati di test.
    - Algoritmo migliore visualizza il nome dell'algoritmo con le prestazioni migliori individuato dal generatore di modelli.
    - Ultimo algoritmo visualizza il nome dell'algoritmo usato più di recente dal generatore di modelli per eseguire il training del modello.

1. Una volta completato l'allenamento, selezionare il collegamento **di valutazione** per passare al passaggio successivo.

## <a name="evaluate-the-model"></a>Valutare il modello

Il risultato del passaggio di training sarà un modello con le migliori prestazioni. Nel passaggio di valutazione dello strumento Generatore di modelli, la sezione di output conterrà l'algoritmo utilizzato dal modello con le migliori prestazioni nella voce **Best Model** insieme alle metriche in Best **Model Accuracy**. Inoltre, viene visualizzata una tabella di riepilogo contenente i primi cinque modelli e le relative metriche.

Se non si è soddisfatti delle metriche di accuratezza, alcuni modi semplici per cercare di migliorare l'accuratezza del modello sono per aumentare la quantità di tempo per eseguire il training del modello o usare più dati. In caso contrario, selezionare il collegamento al **codice** per passare al passaggio finale nello strumento Generatore di modelli.

## <a name="add-the-code-to-make-predictions"></a>Aggiungere il codice per eseguire stime

Il risultato del processo di training sarà la creazione di due progetti.

### <a name="reference-the-trained-model"></a>Fare riferimento al modello sottoposto a trainingReference the trained model

1. Nel passaggio di *codice* dello strumento Generatore di modelli selezionare **Aggiungi progetti** per aggiungere i progetti generati automaticamente alla soluzione.

    I progetti seguenti dovrebbero essere visualizzati in **Esplora soluzioni:**

    - *SentimentRazorML.ConsoleApp:* applicazione console .NET Core che contiene il codice di training e stima del modello.
    - *SentimentRazorML.Model:* libreria di classi .NET Standard contenente i modelli di dati che definiscono lo schema dei dati del modello di input e di output, nonché la versione salvata del modello con le prestazioni migliori durante il training.

    Per questa esercitazione viene usato solo il progetto *SentimentRazorML.Model* perché le stime verranno eseguite nell'applicazione Web *SentimentRazor* anziché nella console. Anche se *sentimentRazorML.ConsoleApp* non verrà usata per il punteggio, può essere usata per eseguire nuovamente il training del modello usando nuovi dati in un secondo momento. La riqualificazione non rientra nell'ambito di questa esercitazione.

### <a name="configure-the-predictionengine-pool"></a>Configurare il pool PredictionEngine

Per eseguire una singola stima, <xref:Microsoft.ML.PredictionEngine%602>è necessario creare un file . <xref:Microsoft.ML.PredictionEngine%602> non è thread-safe. Inoltre, è necessario creare un'istanza di esso ovunque sia necessario all'interno dell'applicazione. Man mano che l'applicazione cresce, questo processo può diventare ingestibile. Per migliorare le prestazioni e la thread safety, `PredictionEnginePool` usare una <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601> combinazione <xref:Microsoft.ML.PredictionEngine%602> di inserimento delle dipendenze e il servizio, che crea un oggetto da utilizzare in tutta l'applicazione.

1. Installare il *pacchetto NuGet Microsoft.Extensions.ML:*

    1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto e **scegliere Gestisci pacchetti NuGet**.
    1. Scegliere "nuget.org" come origine del pacchetto.
    1. Selezionare la scheda **Sfoglia** e cercare **Microsoft.Extensions.ML**.
    1. Selezionare il pacchetto nell'elenco e selezionare il pulsante **Installa.**
    1. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche**
    1. Selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione licenza** se si è soddisfatti delle condizioni di licenza per i pacchetti elencati.

1. Aprire il file *Startup.cs* nel progetto *SentimentRazor.*
1. Aggiungere le istruzioni using seguenti per fare riferimento al Microsoft.Extensions.ML pacchetto NuGet e al progetto *SentimentRazorML.Model:Add* the following using statements to reference the *Microsoft.Extensions.ML* NuGet package and SentimentRazorML.Model project:

    ```csharp
    using System.IO;
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

1. Creare una variabile globale per archiviare il percorso del file di modello sottoposto a training.

    ```csharp
    private readonly string _modelPath;
    ```

1. Il file di modello viene archiviato nella directory di compilazione insieme ai file di assembly dell'applicazione. Per semplificare l'accesso, creare `GetAbsolutePath` un `Configure` metodo helper chiamato dopo il metodoTo make it easier to access, create a helper method called after the method

    ```csharp
    public static string GetAbsolutePath(string relativePath)
    {
        FileInfo _dataRoot = new FileInfo(typeof(Program).Assembly.Location);
        string assemblyFolderPath = _dataRoot.Directory.FullName;

        string fullPath = Path.Combine(assemblyFolderPath, relativePath);
        return fullPath;
    }
    ```

1. Utilizzare `GetAbsolutePath` il metodo `Startup` nel costruttore `_modelPath`della classe per impostare l'oggetto .

    ```csharp
    _modelPath = GetAbsolutePath("MLModel.zip");
    ```

1. Configurare `PredictionEnginePool` l'oggetto `ConfigureServices` per l'applicazione nel metodo:

    ```csharp
    services.AddPredictionEnginePool<ModelInput, ModelOutput>()
            .FromFile(_modelPath);
    ```

### <a name="create-sentiment-analysis-handler"></a>Creare un gestore di analisi del sentimentCreate sentiment analysis handler

Le previsioni verranno effettuate all'interno della pagina principale dell'applicazione. Pertanto, è necessario aggiungere un `PredictionEnginePool` metodo che accetta l'input dell'utente e che utilizza per restituire una stima.

1. Aprire il file *Index.cshtml.cs* che si trova nella directory *Pages* e aggiungere le seguenti istruzioni using:

    ```csharp
    using Microsoft.Extensions.ML;
    using SentimentRazorML.Model;
    ```

    Per utilizzare il `PredictionEnginePool` configurato `Startup` nella classe, è necessario inserirlo nel costruttore del modello in cui si desidera utilizzarlo.

1. Aggiungere una variabile `PredictionEnginePool` per `IndexModel` fare riferimento all'interno della classe.

    ```csharp
    private readonly PredictionEnginePool<ModelInput, ModelOutput> _predictionEnginePool;
    ```

1. Creare un costruttore nella `IndexModel` `PredictionEnginePool` classe e inserirlo il servizio.

    ```csharp
    public IndexModel(PredictionEnginePool<ModelInput, ModelOutput> predictionEnginePool)
    {
        _predictionEnginePool = predictionEnginePool;
    }
    ```

1. Creare un gestore `PredictionEnginePool` di metodo che utilizza l'oggetto per eseguire stime dall'input dell'utente ricevuto dalla pagina Web.Create a method handler that uses the to make predictions from user input received from the web page.

    1. Sotto `OnGet` il metodo, creare un nuovo metodo chiamato`OnGetAnalyzeSentiment`

        ```csharp
        public IActionResult OnGetAnalyzeSentiment([FromQuery] string text)
        {

        }
        ```

    1. All'interno del `OnGetAnalyzeSentiment` metodo, restituire il sentiment *neutro* se l'input dell'utente è vuoto o null.

        ```csharp
        if (String.IsNullOrEmpty(text)) return Content("Neutral");
        ```

    1. Dato un input valido, creare `ModelInput`una nuova istanza di .

        ```csharp
        var input = new ModelInput { SentimentText = text };
        ```

    1. Utilizzare `PredictionEnginePool` il per prevedere il sentiment.

        ```csharp
        var prediction = _predictionEnginePool.Predict(input);
        ```

    1. Convertire il `bool` valore stimato in tossico o non tossico con il codice seguente.

        ```csharp
        var sentiment = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";
        ```

    1. Infine, riporta il sentiment alla pagina web.

        ```csharp
        return Content(sentiment);
        ```

### <a name="configure-the-web-page"></a>Configurare la pagina Web

I risultati restituiti `OnGetAnalyzeSentiment` da `Index` verranno visualizzati dinamicamente nella pagina Web.

1. Aprire il file *Index.cshtml* nella directory *Pages* e sostituirne il contenuto con il codice seguente:

    [!code-cshtml [IndexPage](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/Pages/Index.cshtml)]

1. Successivamente, aggiungere il codice di stile css alla fine della pagina *site.css* nella directory *wwwroot:css:*

    [!code-css [CssStyling](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/css/site.css#L61-L105)]

1. Successivamente, aggiungere il codice per inviare gli `OnGetAnalyzeSentiment` input dalla pagina Web al gestore.

    1. Nel file *site.js* che si trova nella directory *wwwroot.js,* creare una funzione `getSentiment` chiamata `OnGetAnalyzeSentiment` per effettuare una richiesta HTTP GET con l'input dell'utente al gestore.

        [!code-javascript [GetSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L5-L10)]

    1. Sotto di esso, `updateMarker` aggiungere un'altra funzione chiamata per aggiornare dinamicamente la posizione del marcatore nella pagina web come sentiment è previsto.

        [!code-javascript [UpdateMarkerMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L12-L15)]

    1. Creare una funzione `updateSentiment` del gestore eventi chiamata per ottenere `OnGetAnalyzeSentiment` l'input dall'utente, inviarlo alla funzione utilizzando la `getSentiment` funzione e aggiornare il marcatore con la `updateMarker` funzione.

        [!code-javascript [UpdateSentimentMethod](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L17-L34)]

    1. Infine, registrare il gestore `textarea` eventi e `id=Message` associarlo all'elemento con l'attributo .

        [!code-javascript [UpdateSentimentEvtHandler](~/machinelearning-samples/samples/modelbuilder/BinaryClassification_Sentiment_Razor/SentimentRazor/wwwroot/js/site.js#L36)]

## <a name="run-the-application"></a>Eseguire l'applicazione

Ora che l'applicazione è configurata, eseguire l'applicazione, che dovrebbe essere avviata nel browser.

Quando l'applicazione viene avviata, immettere *Model Builder è cool!* nell'area di testo. Il sentiment previsto visualizzato deve essere *Non tossico*.

![Finestra in esecuzione con la finestra di valutazione prevista](./media/sentiment-analysis-model-builder/web-app.png)

Se è necessario fare riferimento ai progetti generati da Model Builder in `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` un secondo momento all'interno di un'altra soluzione, è possibile trovarli all'interno della directory.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> - Creare un'applicazione ASP.NET Core Razor PagesCreate an ASP.NET Core Razor Pages application
> - Preparare e identificare i dati
> - Scegliere uno scenario
> - Caricare i dati
> - Eseguire il training del modello
> - Valutare il modello
> - Usare il modello per le stime

### <a name="additional-resources"></a>Risorse aggiuntive

Per altre informazioni sugli argomenti presentati in questa esercitazione, vedere le risorse seguenti:

- [Scenari del generatore di modelli](../automate-training-with-model-builder.md#scenario)
- [Classificazione binaria](../resources/glossary.md#binary-classification)
- [Metriche del modello di classificazione binariaBinary Classification Model Metrics](../resources/metrics.md#evaluation-metrics-for-binary-classification)

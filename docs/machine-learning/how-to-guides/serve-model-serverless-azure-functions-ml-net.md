---
title: Distribuire un modello in Funzioni di Azure
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET per le previsioni tramite Internet usando Funzioni di Azure
ms.date: 02/21/2020
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 2f340805200a14e0e145ffe1bf20f8059df63555
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81608049"
---
# <a name="deploy-a-model-to-azure-functions"></a>Distribuire un modello in Funzioni di Azure

Informazioni su come distribuire un modello di Machine Learning ML.NET con training preliminare per le previsioni su HTTP tramite un ambiente serverless di Funzioni di Azure.

> [!NOTE]
> In questo esempio viene `PredictionEnginePool` eseguita una versione di anteprima del servizio.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o versione successiva o Visual Studio 2017 versione 15.6 o successiva con i carichi di lavoro "Sviluppo multipiattaforma .NET Core" e "Sviluppo di Azure" installati.
- [Strumenti: Funzioni di Azure](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- PowerShell
- Modello con training preliminare. Usare l'[esercitazione di analisi del sentiment in ML.NET](../tutorials/sentiment-analysis.md) per creare un modello personalizzato oppure scaricare questo [modello di Machine Learning di analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)

## <a name="azure-functions-sample-overview"></a>Panoramica dell'esempio di Funzioni di AzureAzure Functions sample overview

Questo esempio è **un'applicazione http trigger di Azure funzioni** di Azure di C' che usa un modello di classificazione binaria con training preliminare per classificare il sentiment del testo come positivo o negativo. Funzioni di Azure offre un modo semplice per eseguire piccole parti di codice su larga scala in un ambiente serverless gestito nel cloud. Il codice per questo esempio è disponibile nel repository dotnet/machinelearning-samples in GitHub.The code for this sample can be found on the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction) repository on GitHub.

## <a name="create-azure-functions-project"></a>Creare un progetto di Funzioni di Azure

1. Aprire Visual Studio 2017. Selezionare **File** > **nuovo** > **progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **Cloud**. Selezionare quindi il modello di progetto **Funzioni di Azure**. Nella casella di testo **Nome** digitare "SentimentAnalysisFunctionsApp" e quindi selezionare il pulsante **OK**.
1. Nella finestra di dialogo **Nuovo progetto** aprire l'elenco a discesa sopra le opzioni del progetto e selezionare **Azure Functions v2 (.NET Core)** (Funzioni di Azure v2 - .NET Core). Selezionare quindi il progetto **Trigger HTTP** e infine fare clic su **OK**.
1. Creare una directory denominata *MLModels* nel progetto per salvare il modello:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**. Digitare "MLModels" e premere INVIO.

1. Installare il **Microsoft.ML NuGet Package** versione **1.3.1:**

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

1. Installare il **pacchetto NuGet Microsoft.Azure.Functions.Extensions**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Azure.Functions.Extensions**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

1. Installare il **pacchetto NuGet Microsoft.Extensions.ML** versione **0.15.1:**

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Extensions.ML**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

1. Installare **Microsoft.NET.Sdk.Functions NuGet Package** versione **1.0.31**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Installato, cercare **Microsoft.NET.Sdk.Functions**, selezionare il pacchetto nell'elenco, selezionare **1.0.31** dall'elenco a discesa Versione e selezionare il pulsante **Aggiorna.** Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

## <a name="add-pre-trained-model-to-project"></a>Aggiungere il modello con training preliminare al progetto

1. Copiare il modello predefinito nella cartella *MLModels*.
1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file del modello predefinito e scegliere **Proprietà**. In **Avanzate**, modificare il valore di **Copia nella directory** di output in Copia se **più recente**.

## <a name="create-azure-function-to-analyze-sentiment"></a>Creare la funzione di Azure per analizzare il sentiment

Creare una classe per prevedere il sentiment. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi selezionare **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Funzione di Azure** e impostare il campo **Nome** su *AnalyzeSentiment.cs*. Selezionare quindi il pulsante **Aggiungi**.

1. Nella finestra di dialogo **Nuova funzione di Azure** selezionare **Trigger HTTP**. Fare quindi clic su **OK**.

    Il file *AnalyzeSentiment.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio di *AnalyzeSentiment.cs*:

    [!code-csharp [AnalyzeUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L1-L11)]

    Per impostazione predefinita, la classe `AnalyzeSentiment` è `static`. Assicurarsi di rimuovere la parola chiave `static` dalla definizione della classe.

    ```csharp
    public class AnalyzeSentiment
    {

    }
    ```

## <a name="create-data-models"></a>Creare i modelli di dati

È necessario creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati: in Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi > nuova cartella**. Digitare "DataModels" e premere INVIO.
2. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* , quindi **scegliere Aggiungi > nuovo elemento**.
3. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*. Selezionare quindi il pulsante **Aggiungi**.

    Il file *SentimentData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:

    [!code-csharp [SentimentDataUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L1)]

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *di SentimentData.cs:*

    [!code-csharp [SentimentData](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L5-L13)]

4. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* , quindi **scegliere Aggiungi > nuovo elemento**.
5. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*. Selezionare quindi il pulsante **Aggiungi**. Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:

    [!code-csharp [SentimentPredictionUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L1)]

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:

    [!code-csharp [SentimentPrediction](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L5-L14)]

    `SentimentPrediction` eredita da `SentimentData` che consente l'accesso ai dati originali nella proprietà `SentimentText` e all'output generato dal modello.

## <a name="register-predictionenginepool-service"></a>Registrare il servizio PredictionEnginePool

Per eseguire una singola stima, [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)è necessario creare un file . [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe. Inoltre, è necessario creare un'istanza di esso ovunque sia necessario all'interno dell'applicazione. Man mano che l'applicazione cresce, questo processo può diventare ingestibile. Per migliorare le prestazioni e la thread safety, `PredictionEnginePool` usare una [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) combinazione [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) di inserimento delle dipendenze e il servizio, che crea un oggetto da utilizzare in tutta l'applicazione.

Il collegamento seguente fornisce ulteriori informazioni se si desidera ottenere ulteriori informazioni [sull'inserimento](https://en.wikipedia.org/wiki/Dependency_injection)delle dipendenze.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi selezionare **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *Startup.cs*. Selezionare quindi il pulsante **Aggiungi**.
1. Aggiungere le seguenti istruzioni using all'inizio di *Startup.cs*:

    [!code-csharp [StartupUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L1-L6)]

1. Rimuovere il codice esistente sotto le istruzioni using e aggiungere il codice seguente:

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {

        }
    }
    ```

1. Definire le variabili per archiviare l'ambiente in cui è in `Startup` esecuzione l'app e il percorso del file in cui si trova il modello all'interno della classeDefine variables to store the environment the app is running in and the file path where the model is located inside the class

    [!code-csharp [DefineStartupVars](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L13-L14)]

1. Sotto di esso, creare un costruttore per impostare i valori delle variabili `_environment` e `_modelPath` . Quando l'applicazione è in esecuzione in locale, l'ambiente predefinito è *Sviluppo*.

    [!code-csharp [StartupCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L16-L29)]

1. Aggiungere quindi un nuovo `Configure` metodo `PredictionEnginePool` chiamato per registrare il servizio sotto il costruttore.

    [!code-csharp [ConfigureServices](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/Startup.cs#L31-L35)]

A livello generale, questo codice inizializza automaticamente gli oggetti e i servizi per un utilizzo successivo quando richiesto dall'applicazione anziché dover eseguire manualmente.

I modelli di apprendimento automatico non sono statici. Man mano che i nuovi dati di training diventano disponibili, il modello viene riaddestrato e ridistribuito. Un modo per ottenere la versione più recente del modello nell'applicazione consiste nel ridistribuire l'intera applicazione. Tuttavia, questo introduce i tempi di inattività dell'applicazione. Il `PredictionEnginePool` servizio fornisce un meccanismo per ricaricare un modello aggiornato senza arrestare l'applicazione.

Impostare `watchForChanges` il `true`parametro `PredictionEnginePool` su [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) e gli avvii che ascoltano le notifiche di modifica del file system e generano eventi quando viene apportata una modifica al file. In questo `PredictionEnginePool` modo viene richiesto di ricaricare automaticamente il modello.

Il modello è `modelName` identificato dal parametro in modo che più di un modello per applicazione possa essere ricaricato al momento della modifica.

> [!TIP]
> In alternativa, è `FromUri` possibile utilizzare il metodo quando si lavora con modelli memorizzati in remoto. Anziché controllare gli eventi `FromUri` di modifica dei file, esegue il polling della posizione remota per le modifiche. Il valore predefinito dell'intervallo di polling è 5 minuti. È possibile aumentare o ridurre l'intervallo di polling in base ai requisiti dell'applicazione. Nell'esempio di codice `PredictionEnginePool` riportato di seguito, il modello esegue il polling del modello archiviato nell'URI specificato ogni minuto.
>
>```csharp
>builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
>   .FromUri(
>       modelName: "SentimentAnalysisModel",
>       uri:"https://github.com/dotnet/samples/raw/master/machine-learning/models/sentimentanalysis/sentiment_model.zip",
>       period: TimeSpan.FromMinutes(1));
>```

## <a name="load-the-model-into-the-function"></a>Caricare il modello nella funzione

Inserire il codice seguente all'interno della classe *AnalyzeSentiment*:

[!code-csharp [AnalyzeCtor](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L18-L24)]

Questo codice assegna `PredictionEnginePool` passandolo al costruttore della funzione ottenuto tramite l'inserimento delle dipendenze.

## <a name="use-the-model-to-make-predictions"></a>Usare il modello per effettuare previsioni

Sostituire l'implementazione esistente del metodo *Run* nella classe *AnalyzeSentiment* con il codice seguente:

[!code-csharp [AnalyzeRunMethod](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/AnalyzeSentiment.cs#L26-L45)]

Quando il metodo `Run` viene eseguito, i dati in ingresso dalla richiesta HTTP vengono deserializzati e usati come input per `PredictionEnginePool`. Il `Predict` metodo viene quindi chiamato per `SentimentAnalysisModel` eseguire `Startup` stime utilizzando l'oggetto registrato nella classe e restituisce i risultati all'utente in caso di esito positivo.

## <a name="test-locally"></a>Test in locale

Dopo aver completato la configurazione, è possibile testare l'applicazione:

1. Eseguire l'applicazione
1. Aprire PowerShell e immettere il codice nel prompt, dove PORT è la porta su cui l'applicazione è in esecuzione. La porta è in genere la 7071.

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    In caso di esito positivo, l'output sarà simile al testo seguente:

    ```powershell
    Negative
    ```

Congratulazioni! È stato creato il modello per eseguire previsioni tramite Internet usando una funzione di Azure.

## <a name="next-steps"></a>Passaggi successivi

- [Distribuzione in Azure](/azure/azure-functions/functions-develop-vs#publish-to-azure)

---
title: Distribuire un modello in Funzioni di Azure
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET per le previsioni tramite Internet usando Funzioni di Azure
ms.date: 09/12/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 2abd8588aa314b630c995e0c78b5869ec00a89df
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179366"
---
# <a name="deploy-a-model-to-azure-functions"></a>Distribuire un modello in Funzioni di Azure

Informazioni su come distribuire un modello di Machine Learning ML.NET con training preliminare per le previsioni su HTTP tramite un ambiente serverless di Funzioni di Azure.

> [!NOTE]
> L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" e "Sviluppo di Azure" installato.
- Pacchetto NuGet Microsoft.NET.Sdk.Functions versione 1.0.28+.
- [Strumenti di Funzioni di Azure](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- PowerShell
- Modello con training preliminare. Usare l'[esercitazione di analisi del sentiment in ML.NET](../tutorials/sentiment-analysis.md) per creare un modello personalizzato oppure scaricare questo [modello di Machine Learning di analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)

## <a name="create-azure-functions-project"></a>Creare un progetto Funzioni di Azure

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **Cloud**. Selezionare quindi il modello di progetto **Funzioni di Azure**. Nella casella di testo **Nome** digitare "SentimentAnalysisFunctionsApp" e quindi selezionare il pulsante **OK**.
1. Nella finestra di dialogo **Nuovo progetto** aprire l'elenco a discesa sopra le opzioni del progetto e selezionare **Azure Functions v2 (.NET Core)** (Funzioni di Azure v2 - .NET Core). Selezionare quindi il progetto **Trigger HTTP** e infine fare clic su **OK**.
1. Creare una directory denominata *MLModels* nel progetto per salvare il modello:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**. Digitare "MLModels" e premere INVIO.

1. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

1. Installare il **pacchetto NuGet Microsoft.Azure.Functions.Extensions**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Azure.Functions.Extensions**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

1. Installare il **pacchetto Microsoft.Extensions.ML NuGet**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Extensions.ML**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

1. Aggiornare il **pacchetto NuGet Microsoft.NET.Sdk.Functions** alla versione 1.0.28+:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Installati, cercare **Microsoft.NET.Sdk.Functions**, selezionare il pacchetto nell'elenco, selezionare 1.0.28 o versione successiva nell'elenco a discesa Versione e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

## <a name="add-pre-trained-model-to-project"></a>Aggiungere il modello con training preliminare al progetto

1. Copiare il modello predefinito nella cartella *MLModels*.
1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file del modello predefinito e scegliere **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

## <a name="create-azure-function-to-analyze-sentiment"></a>Creare la funzione di Azure per analizzare il sentiment

Creare una classe per prevedere il sentiment. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

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

1. Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati: In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi > Nuova cartella**. Digitare "DataModels" e premere INVIO.
2. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.
3. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*. Selezionare quindi il pulsante **Aggiungi**. 

    Il file *SentimentData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:

    [!code-csharp [SentimentDataUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L1)]

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentData.cs*:

    [!code-csharp [SentimentData](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentData.cs#L5-L13)]

4. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.
5. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*. Selezionare quindi il pulsante **Aggiungi**. Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:

    [!code-csharp [SentimentPredictionUsings](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L1)]

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:

    [!code-csharp [SentimentPrediction](~/machinelearning-samples/samples/csharp/end-to-end-apps/ScalableMLModelOnAzureFunction/SentimentAnalysisFunctionsApp/DataModels/SentimentPrediction.cs#L5-L14)]

    `SentimentPrediction` eredita da `SentimentData` che consente l'accesso ai dati originali nella proprietà `SentimentText` e all'output generato dal modello.

## <a name="register-predictionenginepool-service"></a>Registrare il servizio PredictionEnginePool

Per eseguire una singola stima, è necessario creare un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602). [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe. Inoltre, è necessario crearne un'istanza ovunque sia necessario all'interno dell'applicazione. Con la crescita dell'applicazione, questo processo può diventare non gestibile. Per migliorare le prestazioni e thread safety, usare una combinazione di inserimento delle dipendenze e il servizio `PredictionEnginePool`, che consente di creare un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di oggetti [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) da usare nell'applicazione.

Il collegamento seguente fornisce ulteriori informazioni se si desidera ottenere ulteriori informazioni sull' [inserimento delle dipendenze](https://en.wikipedia.org/wiki/Dependency_injection).

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *Startup.cs*. Selezionare quindi il pulsante **Aggiungi**. 

    Il file *Startup.cs* verrà aperto nell'editor di codice. Aggiungere l'istruzione using seguente all'inizio di *Startup.cs*:

    ```csharp
    using Microsoft.Azure.Functions.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    Rimuovere il codice esistente sotto le istruzioni using e aggiungere il codice seguente al file *Startup.cs*:

    ```csharp
    [assembly: FunctionsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        public class Startup : FunctionsStartup
        {
            public override void Configure(IFunctionsHostBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
            }
        }
    }
    ```

A un livello elevato, questo codice inizializza automaticamente gli oggetti e i servizi per un uso successivo quando richiesto dall'applicazione anziché eseguire manualmente questa operazione. 

I modelli di apprendimento automatico non sono statici. Al momento della disponibilità dei nuovi dati di training, il modello viene nuovamente sottoposto a training e ridistribuito. Un modo per ottenere la versione più recente del modello nell'applicazione consiste nel ridistribuire l'intera applicazione. Questa operazione introduce tuttavia i tempi di inattività dell'applicazione. Il servizio `PredictionEnginePool` fornisce un meccanismo per ricaricare un modello aggiornato senza interrompere l'esecuzione dell'applicazione. 

Impostare il parametro `watchForChanges` su `true` e il `PredictionEnginePool` avvia un [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) in ascolto delle notifiche di modifica file System e genera eventi quando viene apportata una modifica al file. In questo modo viene richiesto `PredictionEnginePool` per ricaricare automaticamente il modello.

Il modello è identificato dal parametro `modelName` in modo che sia possibile ricaricare più di un modello per applicazione al momento della modifica. 

> [!TIP]
> In alternativa, è possibile utilizzare il metodo `FromUri` quando si utilizzano i modelli archiviati in remoto. Invece di controllare gli eventi di modifica dei file, `FromUri` esegue il polling della posizione remota per le modifiche. Per impostazione predefinita, l'intervallo di polling è 5 minuti. È possibile aumentare o diminuire l'intervallo di polling in base ai requisiti dell'applicazione. Nell'esempio di codice riportato di seguito, il `PredictionEnginePool` esegue il polling del modello archiviato nell'URI specificato ogni minuto.
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

```csharp
[FunctionName("AnalyzeSentiment")]
public async Task<IActionResult> Run(
[HttpTrigger(AuthorizationLevel.Function, "post", Route = null)] HttpRequest req,
ILogger log)
{
    log.LogInformation("C# HTTP trigger function processed a request.");

    //Parse HTTP Request Body
    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

    //Make Prediction
    SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

Quando il metodo `Run` viene eseguito, i dati in ingresso dalla richiesta HTTP vengono deserializzati e usati come input per `PredictionEnginePool`. Il metodo `Predict` viene quindi chiamato a per eseguire stime utilizzando `SentimentAnalysisModel` registrato nella classe `Startup` e restituisce i risultati all'utente in caso di esito positivo.

## <a name="test-locally"></a>Eseguire il test in locale

Dopo aver completato la configurazione, è possibile testare l'applicazione:

1. Esecuzione dell'applicazione
1. Aprire PowerShell e immettere il codice nel prompt, dove PORT è la porta su cui l'applicazione è in esecuzione. La porta è in genere la 7071.

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    In caso di esito positivo, l'output sarà simile al testo seguente:
    
    ```powershell
    Negative
    ```

La procedura è stata completata. È stato creato il modello per eseguire previsioni tramite Internet usando una funzione di Azure.

## <a name="next-steps"></a>Passaggi successivi

- [Distribuire in Azure](/azure/azure-functions/functions-develop-vs#publish-to-azure)

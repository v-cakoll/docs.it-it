---
title: Distribuire un modello in Funzioni di Azure
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET per le previsioni tramite Internet usando Funzioni di Azure
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: c30c1c2e6f00020d22fe32fb3f53cefe88d8bb09
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063507"
---
# <a name="deploy-a-model-to-azure-functions"></a>Distribuire un modello in Funzioni di Azure

Informazioni su come distribuire un modello di Machine Learning ML.NET con training preliminare per le previsioni su HTTP tramite un ambiente serverless di Funzioni di Azure.

> [!NOTE]
> L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" e "Sviluppo di Azure" installato.
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

1. Installare il **pacchetto Microsoft.Extensions.ML NuGet**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Extensions.ML**, selezionare il pacchetto nell'elenco e quindi il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

## <a name="add-pre-trained-model-to-project"></a>Aggiungere il modello con training preliminare al progetto

1. Copiare il modello predefinito nella cartella *MLModels*.
1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file del modello predefinito e scegliere **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

## <a name="create-azure-function-to-analyze-sentiment"></a>Creare la funzione di Azure per analizzare il sentiment

Creare una classe per prevedere il sentiment. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Funzione di Azure** e impostare il campo **Nome** su *AnalyzeSentiment.cs*. Selezionare quindi il pulsante **Aggiungi**.

1. Nella finestra di dialogo **Nuova funzione di Azure** selezionare **Trigger HTTP**. Fare quindi clic su **OK**.

    Il file *AnalyzeSentiment.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio di *AnalyzeSentiment.cs*:

    ```csharp
    using System;
    using System.IO;
    using System.Threading.Tasks;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using Microsoft.AspNetCore.Http;
    using Microsoft.Extensions.Logging;
    using Newtonsoft.Json;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

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

    ```csharp
    using Microsoft.ML.Data;
    ```

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentData.cs*:
    
    ```csharp
    public class SentimentData
    {
        [LoadColumn(0)]
        public string SentimentText;

        [LoadColumn(1)]
        [ColumnName("Label")]
        public bool Sentiment;
    }
    ```

4. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.
5. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*. Selezionare quindi il pulsante **Aggiungi**. Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:

    ```csharp
    using Microsoft.ML.Data;
    ```

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    `SentimentPrediction` eredita da `SentimentData` che consente l'accesso ai dati originali nella proprietà `SentimentText` e all'output generato dal modello.

## <a name="register-predictionenginepool-service"></a>Registrare il servizio PredictionEnginePool

Per effettuare una singola previsione, usare [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602). Per poter usare la classe [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) nell'applicazione è necessario crearla quando è richiesta. In tal caso, una procedura consigliata da prendere in considerazione è l'inserimento delle dipendenze.

Il collegamento seguente fornisce altre informazioni sull'[inserimento delle dipendenze](https://en.wikipedia.org/wiki/Dependency_injection).

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il campo **Nome** in *Startup.cs*. Selezionare quindi il pulsante **Aggiungi**. 

    Il file *Startup.cs* verrà aperto nell'editor di codice. Aggiungere l'istruzione using seguente all'inizio di *Startup.cs*:

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    Rimuovere il codice esistente sotto le istruzioni using e aggiungere il codice seguente al file *Startup.cs*:

    ```csharp
    [assembly: WebJobsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        class Startup : IWebJobsStartup
        {
            public void Configure(IWebJobsBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

In generale, questo codice inizializza automaticamente gli oggetti e i servizi quando vengono richiesti dall'applicazione invece di doverlo fare manualmente.

> [!WARNING]
> [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe. Per migliorare le prestazioni e le capacità di thread safety, usare il servizio `PredictionEnginePool` che crea una classe [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di oggetti `PredictionEngine` per l'uso da parte dell'applicazione. 

## <a name="register-startup-as-an-azure-functions-extension"></a>Registrare Startup come estensione di Funzioni di Azure

Per poter usare `Startup` nell'applicazione è necessario registrarlo come estensione di Funzioni di Azure. Creare un nuovo file denominato *extensions.json* nel progetto, se non ne esiste già uno.

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Nuovo elemento** selezionare il nodo **Visual C#**  seguito dal nodo **Web**. Quindi selezionare l'opzione **File Json**. Nella casella di testo **Nome** digitare "extensions.json" e quindi selezionare il pulsante **OK**.

    Il file *extensions.json* verrà aperto nell'editor di codice. Aggiungere il contenuto seguente a *extensions.json*:
    
    ```json
    {
      "extensions": [
        {
          "name": "Startup",
          "typename": "SentimentAnalysisFunctionsApp.Startup, SentimentAnalysisFunctionsApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"
        }
      ]
    }
    ```

1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file *extensions.json* e selezionare **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

## <a name="load-the-model-into-the-function"></a>Caricare il modello nella funzione

Inserire il codice seguente all'interno della classe *AnalyzeSentiment*:

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

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
    SentimentPrediction prediction = _predictionEnginePool.Predict(data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

Quando il metodo `Run` viene eseguito, i dati in ingresso dalla richiesta HTTP vengono deserializzati e usati come input per `PredictionEnginePool`. Viene quindi chiamato il metodo `Predict` per generare una previsione e restituire il risultato all'utente. 

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

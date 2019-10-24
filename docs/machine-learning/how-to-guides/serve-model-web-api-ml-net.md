---
title: Distribuire un modello in un'API Web ASP.NET Core
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET tramite Internet usando l'API Web ASP.NET Core
ms.date: 09/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: b85d77900c5d9227ecc6fe81b8a8d68171dd9ef5
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774515"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a>Distribuire un modello in un'API Web ASP.NET Core

Informazioni su come rendere disponibile un modello di Machine Learning ML.NET con training preliminare sul Web usando un'API Web ASP.NET Core. La disponibilità di un modello su un'API Web consente previsioni tramite metodi HTTP standard.

> [!NOTE]
> L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

## <a name="prerequisites"></a>Prerequisites

- [Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.
- PowerShell.
- Modello con training preliminare. Usare l'[esercitazione di analisi del sentiment in ML.NET](../tutorials/sentiment-analysis.md) per creare un modello personalizzato oppure scaricare questo [modello di Machine Learning di analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)

## <a name="create-aspnet-core-web-api-project"></a>Creare un progetto API Web ASP.NET Core

1. Aprire Visual Studio 2017. Dalla barra dei menu scegliere **File > Nuovo > Progetto**. Nella finestra di dialogo Nuovo progetto selezionare il nodo **Visual C#** seguito dal nodo **Web**. Selezionare quindi il modello di progetto **Applicazione Web ASP.NET Core**. Nella casella di testo **Nome** digitare "SentimentAnalysisWebAPI" e quindi selezionare il pulsante **OK**.

1. Nella finestra in cui sono visualizzati i diversi tipi di progetti ASP.NET Core selezionare **API** e quindi fare clic su **OK**.

1. Nel progetto creare una directory denominata *MLModels* in cui salvare i file dei modelli di Machine Learning predefiniti:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella. Digitare "MLModels" e premere INVIO.

1. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante Installa. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.

1. Installare il **pacchetto Nuget Microsoft.Extensions.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.Extensions.ML**, selezionare il pacchetto nell'elenco e quindi il pulsante Installa. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.

### <a name="add-model-to-aspnet-core-web-api-project"></a>Aggiungere il modello al progetto API Web ASP.NET Core

1. Copiare il modello predefinito nella directory *MLModels*
1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file ZIP del modello e scegliere Proprietà. In Avanzate impostare il valore di Copia nella directory di output su Copia se più recente.

## <a name="create-data-models"></a>Creare modelli di dati

È necessario creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella. Digitare "DataModels" e premere **INVIO**.

2. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere Aggiungi > Nuovo elemento.
3. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*. Selezionare quindi il pulsante **Aggiungi**. Il file *SentimentData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:

    ```csharp
    using Microsoft.ML.Data;
    ```

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file **SentimentData.cs**:

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
5. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*. Selezionare quindi il pulsante Aggiungi. Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:

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

    `SentimentPrediction` eredita da `SentimentData`. Ciò semplifica la visualizzazione dei dati originali nella proprietà `SentimentText` insieme all'output generato dal modello.

## <a name="register-predictionenginepool-for-use-in-the-application"></a>Registrare PredictionEnginePool per l'uso nell'applicazione

Per eseguire una singola stima, è necessario creare un [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602). [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe. Inoltre, è necessario crearne un'istanza ovunque sia necessario all'interno dell'applicazione. Con la crescita dell'applicazione, questo processo può diventare non gestibile. Per migliorare le prestazioni e thread safety, utilizzare una combinazione di inserimento delle dipendenze e il servizio `PredictionEnginePool`, che consente di creare un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di oggetti [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) per l'utilizzo nell'applicazione.

Il collegamento seguente fornisce ulteriori informazioni se si desidera ottenere ulteriori informazioni sull' [inserimento delle dipendenze in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).

1. Aprire la classe *Startup.cs* e aggiungere l'istruzione using seguente all'inizio del file:

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. Aggiungere il codice seguente al metodo *ConfigureServices*:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    }
    ```

A un livello elevato, questo codice inizializza automaticamente gli oggetti e i servizi per un uso successivo quando richiesto dall'applicazione anziché eseguire manualmente questa operazione.

I modelli di apprendimento automatico non sono statici. Al momento della disponibilità dei nuovi dati di training, il modello viene nuovamente sottoposto a training e ridistribuito. Un modo per ottenere la versione più recente del modello nell'applicazione consiste nel ridistribuire l'intera applicazione. Questa operazione introduce tuttavia i tempi di inattività dell'applicazione. Il servizio `PredictionEnginePool` fornisce un meccanismo per ricaricare un modello aggiornato senza interrompere l'applicazione.

Impostare il parametro `watchForChanges` su `true` e il `PredictionEnginePool` avvia un [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) in ascolto delle notifiche di modifica file System e genera eventi quando viene apportata una modifica al file. In questo modo viene richiesto all'`PredictionEnginePool` di ricaricare automaticamente il modello.

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

## <a name="create-predict-controller"></a>Creare il controller Predict

Per elaborare le richieste HTTP in ingresso, creare un controller.

1. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *Controllers* e quindi scegliere **Aggiungi > Controller**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Controller API - Vuoto** e selezionare **Aggiungi**.
1. Nel prompt impostare il campo **Nome controller** su *PredictController.cs*. Selezionare quindi il pulsante Aggiungi. Il file *PredictController.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *PredictController.cs*:

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *PredictController.cs*:

    ```csharp
    public class PredictController : ControllerBase
    {
        private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

        public PredictController(PredictionEnginePool<SentimentData,SentimentPrediction> predictionEnginePool)
        {
            _predictionEnginePool = predictionEnginePool;
        }

        [HttpPost]
        public ActionResult<string> Post([FromBody] SentimentData input)
        {
            if(!ModelState.IsValid)
            {
                return BadRequest();
            }

            SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

Questo codice assegna `PredictionEnginePool` passandolo al costruttore del controller ottenuto tramite l'inserimento delle dipendenze. Quindi, il metodo di `Post` del controller di `Predict` utilizza il `PredictionEnginePool` per eseguire stime utilizzando il `SentimentAnalysisModel` registrato nella classe `Startup` e restituisce i risultati all'utente in caso di esito positivo.

## <a name="test-web-api-locally"></a>Testare l'API Web in locale

Dopo aver completato la configurazione, è possibile testare l'applicazione.

1. Eseguire l'applicazione.
1. Aprire PowerShell e immettere il codice seguente, dove PORT è la porta su cui l'applicazione è in ascolto.

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    In caso di esito positivo, l'output sarà simile al testo seguente:

    ```powershell
    Negative
    ```

La procedura è stata completata. Il modello per effettuare previsioni in Internet usando un'API Web ASP.NET Core è stato reso disponibile.

## <a name="next-steps"></a>Passaggi successivi

- [Distribuire in Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)

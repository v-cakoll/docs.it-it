---
title: Fornire il modello di Machine Learning nell'API Web ASP.NET Core
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET tramite Internet usando l'API Web ASP.NET Core
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 07b751caff8ef0ca9a23bed68ddf88feb7b5ae4f
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "57856703"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a>Procedura: Fornire il modello di Machine Learning tramite l'API Web ASP.NET Core

Questa procedura illustra come fornire un modello di Machine Learning ML.NET predefinito nel Web usando un'API Web ASP.NET. In questo modo, gli utenti possono accedere all'API a scopo di previsione tramite i metodi HTTP standard.

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.
- PowerShell.
- Modello con training preliminare.
    - Usare l'[esercitazione sull'analisi del sentiment con ML.NET](../tutorials/sentiment-analysis.md) per creare il proprio modello.
    - Scaricare questo [modello di Machine Learning per l'analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)

## <a name="create-aspnet-core-web-api-project"></a>Creare il progetto per l'API Web ASP.NET Core

1. Aprire Visual Studio 2017. Dalla barra dei menu scegliere **File > Nuovo > Progetto**. Nella finestra di dialogo Nuovo progetto selezionare il nodo **Visual C#** seguito dal nodo **Web**. Selezionare quindi il modello di progetto **Applicazione Web ASP.NET Core**. Nella casella di testo **Nome** digitare "SentimentAnalysisWebAPI" e quindi selezionare il pulsante **OK**.
1. Nella finestra in cui sono visualizzati i diversi tipi di progetti ASP.NET Core selezionare **API** e quindi fare clic su **OK**.
1. Nel progetto creare una directory denominata *MLModels* in cui salvare i file dei modelli di Machine Learning predefiniti:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella. Digitare "MLModels" e premere INVIO.

1. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante Installa. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.

### <a name="add-model-to-aspnet-core-web-api-project"></a>Aggiungere il modello al progetto per l'API Web ASP.NET Core

1. Copiare il modello predefinito nella directory *MLModels*
1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file ZIP del modello e scegliere Proprietà. In Avanzate impostare il valore di Copia nella directory di output su Copia se più recente.

## <a name="build-data-models"></a>Creare modelli di dati

È necessario creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere Aggiungi > Nuova cartella. Digitare "DataModels" e premere **INVIO**.

2. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere Aggiungi > Nuovo elemento.
3. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*. Selezionare quindi il pulsante **Aggiungi**. Il file *SentimentData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file **SentimentData.cs**:

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.
5. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*. Selezionare quindi il pulsante Aggiungi. Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *SentimentPrediction.cs*:

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="create-prediction-service"></a>Creare il servizio di previsione

Per organizzare e riutilizzare la logica di previsione nell'intera applicazione, creare un servizio di previsione.

1. Nel progetto creare una directory denominata *Services* in cui archiviare i servizi usati dall'applicazione:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi > Nuova cartella**. Digitare "Services" e premere **INVIO**.

1. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *Services* e quindi scegliere **Aggiungi > Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e modificare il valore del campo **Nome** impostando *PredictionService.cs*. Selezionare quindi il pulsante **Aggiungi**. Il file *PredictionService.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *PredictionService.cs*:

```csharp
using System;
using System.IO;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *PredictionService.cs*:

```csharp
public class PredictionService
{
    private readonly PredictionEngine<SentimentData, SentimentPrediction> _predictionEngine;
    public PredictionService(PredictionEngine<SentimentData,SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine;
    }

    public string Predict(SentimentData input)
    {
        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return isToxic;

    }
}
```

## <a name="register-predictions-service-for-use-in-application"></a>Registrare il servizio di previsione per usarlo nell'applicazione

Per usare il servizio di previsione nell'applicazione, lo si dovrà creare ogni volta che sarà necessario. In tal caso, una procedura consigliata da prendere in considerazione è l'inserimento delle dipendenze in ASP.NET.

Il collegamento seguente fornisce altre informazioni sull'[inserimento delle dipendenze](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).

1. Aprire la classe *Startup.cs* e aggiungere l'istruzione using seguente all'inizio del file:

```csharp
using System.IO;
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Configuration;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

1. Aggiungere le righe di codice seguenti al metodo *ConfigureServices*:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddSingleton<MLContext>();
    services.AddSingleton<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
    {
        MLContext mlContext = ctx.GetRequiredService<MLContext>();
        string modelFilePathName = "MLModels/sentiment_model.zip";

        //Load model from file
        ITransformer model;
        using (var stream = File.OpenRead(modelFilePathName))
        {
            model = mlContext.Model.Load(stream);
        }

        // Return prediction engine
        return model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);
    });
    services.AddSingleton<PredictionService>();
}
```

In generale, questo codice inizializza automaticamente gli oggetti e i servizi quando vengono richiesti dall'applicazione invece di doverlo fare manualmente.

## <a name="create-predict-controller"></a>Creare il controller per le previsioni

Per elaborare le richieste HTTP in ingresso, è necessario creare un controller.

1. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *Controllers* e quindi scegliere **Aggiungi > Controller**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Controller API - Vuoto** e selezionare **Aggiungi**.
1. Nel prompt impostare il campo **Nome controller** su *PredictController.cs*. Selezionare quindi il pulsante Aggiungi. Il file *PredictController.cs* viene aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *PredictController.cs*:

```csharp
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file *PredictController.cs*:

```csharp
public class PredictController : ControllerBase
{

    private readonly PredictionService _predictionService;

    public PredictController(PredictionService predictionService)
    {
        _predictionService = predictionService; //Define prediction service
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }
        return Ok(_predictionService.Predict(input));
    }

}
```

Il servizio di previsione viene quindi assegnato passandolo al costruttore del controller ottenuto tramite l'inserimento delle dipendenze. Nel metodo POST di questo controller il servizio di previsione viene poi usato per eseguire previsioni e restituire i risultati all'utente in caso di esito positivo.

## <a name="test-web-api-locally"></a>Testare l'API Web in locale

Dopo aver completato la configurazione, è possibile testare l'applicazione.

1. Eseguire l'applicazione.
1. Aprire PowerShell e immettere il codice seguente, dove PORT è la porta su cui l'applicazione è in ascolto.

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

In caso di esito positivo, l'output sarà simile al testo seguente:

```powershell
Toxic
```

La procedura è stata completata. È stato creato il modello per eseguire previsioni tramite Internet usando un'API ASP.NET Core.

## <a name="next-steps"></a>Passaggi successivi

- [Distribuire in Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)
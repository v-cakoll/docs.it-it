---
title: Distribuire il modello ML.NET in Funzioni di Azure
description: Fornire il modello di Machine Learning per l'analisi del sentiment ML.NET per le previsioni tramite Internet usando Funzioni di Azure
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4681b37da64097dd8e537b4c956917277ecff96b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330636"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a>Procedura: Usare il modello ML.NET in Funzioni di Azure

Questa procedura illustra come si possono eseguire singole previsioni usando un modello di Machine Learning ML.NET predefinito tramite Internet in un ambiente serverless come Funzioni di Azure.

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa procedura e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" e "Sviluppo di Azure" installato. 
- [Strumenti di Funzioni di Azure](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- PowerShell
- Modello con training preliminare. 
    - Usare l'[esercitazione sull'analisi del sentiment con ML.NET](../tutorials/sentiment-analysis.md) per creare il proprio modello.
    - Scaricare questo [modello di Machine Learning per l'analisi del sentiment con training preliminare](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)

## <a name="create-azure-functions-project"></a>Creare il progetto di Funzioni di Azure

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **Cloud**. Selezionare quindi il modello di progetto **Funzioni di Azure**. Nella casella di testo **Nome** digitare "SentimentAnalysisFunctionsApp" e quindi selezionare il pulsante **OK**.
1. Nella finestra di dialogo **Nuovo progetto** aprire l'elenco a discesa sopra le opzioni del progetto e selezionare **Azure Functions v2 (.NET Core)** (Funzioni di Azure v2 - .NET Core). Selezionare quindi il progetto **Trigger HTTP** e infine fare clic su **OK**.
1. Creare una directory denominata *MLModels* nel progetto per salvare il modello:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**. Digitare "MLModels" e premere INVIO.

1. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

## <a name="add-pre-built-model-to-project"></a>Aggiungere il modello predefinito al progetto

1. Copiare il modello predefinito nella cartella *MLModels*.
1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file del modello predefinito e scegliere **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

## <a name="create-function-to-analyze-sentiment"></a>Creare la funzione per analizzare il sentiment

Creare una classe per prevedere il sentiment. Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.

1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Funzione di Azure** e impostare il campo **Nome** su *AnalyzeSentiment.cs*. Selezionare quindi il pulsante **Aggiungi**.

1. Nella finestra di dialogo **Nuova funzione di Azure** selezionare **Trigger HTTP**. Fare quindi clic su **OK**.

    Il file *AnalyzeSentiment.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio del file *GitHubIssueData.cs*:

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
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using Microsoft.ML.Data;
using MLNETServerless.DataModels;
```

### <a name="create-data-models"></a>Creare i modelli di dati

È necessario creare alcune classi per i dati di input e le stime. Aggiungere una nuova classe al progetto:

1. Creare una directory denominata *DataModels* nel progetto per salvare i modelli di dati: In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi > Nuova cartella**. Digitare "DataModels" e premere INVIO.
2. In Esplora soluzioni fare clic con il pulsante destro del mouse sulla directory *DataModels* e quindi scegliere **Aggiungi > Nuovo elemento**.
3. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentData.cs*. Selezionare quindi il pulsante **Aggiungi**. Il file *SentimentData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentData.cs*:

```csharp
using Microsoft.ML.Data;
```

Rimuovere la definizione di classe esistente e aggiungere il codice seguente al file SentimentData.cs:

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
5. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *SentimentPrediction.cs*. Selezionare quindi il pulsante **Aggiungi**. Il file *SentimentPrediction.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione using seguente all'inizio del file *SentimentPrediction.cs*:

```csharp
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

### <a name="add-prediction-logic"></a>Aggiungere la log della previsione

Sostituire l'implementazione esistente del metodo *Run* nella classe *AnalyzeSentiment* con il codice seguente:

```csharp
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function,"post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        //Create Context
        MLContext mlContext = new MLContext();

        //Load Model
        using (var fs = File.OpenRead("MLModels/sentiment_model.zip"))
        {
            model = mlContext.Model.Load(fs);
        }

        //Parse HTTP Request Body
        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

        //Create Prediction Engine
        PredictionEngine<SentimentData, SentimentPrediction> predictionEngine = model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);

        //Make Prediction
        SentimentPrediction prediction = predictionEngine.Predict(data);

        //Convert prediction to string
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        //Return Prediction
        return (ActionResult)new OkObjectResult(isToxic);
    }
}
```

## <a name="test-locally"></a>Eseguire il test in locale

Dopo aver completato la configurazione, è possibile testare l'applicazione:

1. Esecuzione dell'applicazione
1. Aprire PowerShell e immettere il codice nel prompt, dove PORT è la porta su cui l'applicazione è in esecuzione. La porta è in genere la 7071. 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

In caso di esito positivo, l'output sarà simile al testo seguente:

```powershell
Toxic
```

La procedura è stata completata. È stato creato il modello per eseguire previsioni tramite Internet usando una funzione di Azure.

## <a name="next-steps"></a>Passaggi successivi

- [Distribuire in Azure](/azure/azure-functions/functions-develop-vs#publish-to-azure)
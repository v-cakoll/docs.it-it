---
title: 'Esercitazione: previsione della richiesta di noleggio biciclette'
description: Questa esercitazione illustra come prevedere la domanda per un servizio di noleggio di biciclette usando l'analisi della serie temporale univariata e ML.NET.
ms.date: 11/07/2019
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 026421d7b1b2a0e39118ae712780ca7fc8f6e444
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921248"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a>Esercitazione: prevedere la richiesta del servizio di noleggio biciclette con l'analisi delle serie temporali e ML.NET

Informazioni su come prevedere la domanda per un servizio di noleggio di biciclette usando l'analisi della serie temporale univariata nei dati archiviati in un database di SQL Server con ML.NET.

In questa esercitazione si imparerà a:
> [!div class="checklist"]
>
> * Informazioni sul problema
> * Caricare dati da un database
> * Creare un modello di previsione
> * Valutare il modello di previsione
> * Salvare un modello di previsione
> * Usare un modello di previsione

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.

## <a name="time-series-forecasting-sample-overview"></a>Panoramica dell'esempio di previsione delle serie temporali

Questo esempio è un'  **C# applicazione console .NET Core** che prevede la richiesta di noleggi di biciclette usando un algoritmo di analisi della serie temporale univariato noto come analisi a spettro singolo. Il codice per questo esempio è disponibile nel repository [DotNet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) in GitHub.

## <a name="understand-the-problem"></a>Informazioni sul problema

Per eseguire un'operazione efficiente, gestione inventario gioca un ruolo fondamentale. La presenza di una quantità eccessiva di prodotti in magazzino significa che i prodotti non venduti seduti sugli scaffali non generano ricavi. Il fatto di avere un prodotto troppo piccolo porta a perdere le vendite e i clienti che acquistano da concorrenti. Quindi, la domanda costante è, qual è la quantità ottimale di inventario da usare? L'analisi delle serie temporali consente di fornire una risposta a queste domande osservando i dati cronologici, identificando i modelli e usando queste informazioni per prevedere i valori in futuro.

La tecnica per analizzare i dati usati in questa esercitazione è l'analisi della serie temporale univariata. L'analisi della serie temporale univariata esamina un'unica osservazione numerica in un periodo di tempo a intervalli specifici, ad esempio le vendite mensili.

L'algoritmo usato in questa esercitazione è [Single Spectrum Analysis (SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf). La funzione SSA scompone una serie temporale in un set di componenti principali. Questi componenti possono essere interpretati come parti di un segnale che corrispondono a tendenze, rumore, stagionalità e molti altri fattori. Quindi, questi componenti vengono ricostruiti e usati per prevedere i valori in futuro.

## <a name="create-console-application"></a>Creare un'applicazione console

1. Creare una nuova  **C# applicazione console .NET Core** denominata "BikeDemandForecasting".
1. Installare il pacchetto NuGet **Microsoft.ml** Version **1.4.0**
    1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.
    1. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda **Sfoglia** , cercare **Microsoft.ml**.
    1. Selezionare la casella di controllo **Includi versione preliminare** .
    1. Selezionare il pulsante **Installa**.
    1. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.
    1. Ripetere questi passaggi per **System. Data. SqlClient** versione **4.7.0** e **Microsoft. ml. TimeSeries** versione **1.4.0**.

### <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

1. Creare una directory denominata *Data*.
1. Scaricare il [file di database *DailyDemand. MDF* ](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) e salvarlo nella directory *dei dati* .

> [!NOTE]
> I dati usati in questa esercitazione provengono dal set di dati [UCI bike sharing](https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset). Federico-T, Hadi e Gama, Joao,' Event Labeling combining Ensemble Detectors and background Knowledge ', Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [collegamento Web](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).

Il set di dati originale contiene diverse colonne che corrispondono a stagionalità e meteo. Per brevità e perché l'algoritmo usato in questa esercitazione richiede solo i valori di una singola colonna numerica, il set di dati originale è stato condensato in modo da includere solo le colonne seguenti:

- **dteday**: data dell'osservazione.
- **year**: anno codificato dell'osservazione (0 = 2011, 1 = 2012).
- **CNT**: numero totale di noleggi di biciclette per quel giorno.

Il set di dati originale viene mappato a una tabella di database con lo schema seguente in un database SQL Server.

```SQL
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

Di seguito è riportato un esempio dei dati:

| RentalDate | Anno | TotalRentals |
| --- | --- | --- |
|1/1/2011|0|985|
|1/2/2011|0|801|
|1/3/2011|0|1349|

### <a name="create-input-and-output-classes"></a>Creare classi di input e output

1. Aprire il file *Program.cs* e sostituire le istruzioni `using` esistenti con il codice seguente:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. Creare `ModelInput` classe. Sotto la classe `Program` aggiungere il codice seguente.

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    La classe `ModelInput` contiene le colonne seguenti:

    - **RentalDate**: data dell'osservazione.
    - **Year**: anno codificato dell'osservazione (0 = 2011, 1 = 2012).
    - **TotalRentals**: numero totale di noleggi di biciclette per quel giorno.

1. Creare `ModelOutput` classe al di sotto della `ModelInput` classe appena creata.

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    La classe `ModelOutput` contiene le colonne seguenti:

    - **ForecastedRentals**: i valori stimati per il periodo previsto.
    - **LowerBoundRentals**: valori minimi stimati per il periodo previsto.
    - **UpperBoundRentals**: valori massimi stimati per il periodo previsto.

### <a name="define-paths-and-initialize-variables"></a>Definire i percorsi e inizializzare le variabili

1. All'interno del metodo `Main` definire le variabili per archiviare il percorso dei dati, la stringa di connessione e il percorso in cui salvare il modello sottoposto a training.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. Inizializzare la variabile `mlContext` con una nuova istanza di [`MLContext`](xref:Microsoft.ML.MLContext) aggiungendo la riga seguente al metodo `Main`.

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    La classe [`MLContext`](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ml.NET e l'inizializzazione di mlContext crea un nuovo ambiente ml.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

## <a name="load-the-data"></a>Caricare i dati

1. Creare `DatabaseLoader` che carica i record di tipo `ModelInput`.

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. Definire la query per caricare i dati dal database.

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    Gli algoritmi ML.NET prevedono che i dati siano di tipo [`Single`](xref:System.Single). Pertanto, i valori numerici provenienti dal database che non sono di tipo [`Real`](xref:System.Data.SqlDbType), un valore a virgola mobile e precisione singola, devono essere convertiti in [`Real`](xref:System.Data.SqlDbType).

    Le colonne `Year` e `TotalRental` sono entrambi tipi integer nel database. Utilizzando la `CAST` funzione predefinita, viene eseguito il cast a `Real`.

1. Creare una `DatabaseSource` per connettersi al database ed eseguire la query.

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. Caricare i dati in un `IDataView`.

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. Il set di dati contiene due anni di dati. Solo i dati del primo anno vengono utilizzati per il training, il secondo anno viene considerato per confrontare i valori effettivi rispetto alla previsione prodotta dal modello. Filtrare i dati utilizzando la trasformazione [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) .

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    Per il primo anno, solo i valori della colonna `Year` inferiore a 1 vengono selezionati impostando il parametro `upperBound` su 1. Viceversa, per il secondo anno vengono selezionati i valori maggiori o uguali a 1 impostando il parametro `lowerBound` su 1.

## <a name="define-time-series-analysis-pipeline"></a>Definire la pipeline di analisi della serie temporale

1. Definire una pipeline che usa [SsaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) per prevedere i valori in un set di dati di serie temporali.

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    Il `forecastingPipeline` accetta 365 punti dati per il primo anno ed esempi oppure suddivide il set di dati di serie temporali in intervalli di 30 giorni (mensili) come specificato dal parametro `seriesLength`. Ognuno di questi esempi viene analizzato tramite una finestra settimanale o di 7 giorni. Quando si determina il valore previsto per il periodo di tempo successivo, vengono utilizzati i valori dei sette giorni precedenti per eseguire una stima. Il modello è impostato in modo da prevedere sette periodi nel futuro in base a quanto definito dal parametro `horizon`. Poiché una previsione è un'ipotesi informata, non è sempre accurata al 100%. È quindi opportuno conoscere l'intervallo di valori negli scenari migliori e peggiori in base a quanto definito dai limiti superiore e inferiore. In questo caso, il livello di confidenza per i limiti inferiore e superiore è impostato su 95%. Il livello di confidenza può essere aumentato o diminuito di conseguenza. Maggiore è il valore, più ampio è l'intervallo tra i limiti superiore e inferiore per raggiungere il livello di confidenza desiderato.

1. Utilizzare il metodo [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*) per eseguire il training del modello e adattare i dati al `forecastingPipeline`definito in precedenza.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a>Valutare il modello

Valutare le prestazioni del modello tramite la previsione dei dati dell'anno successivo e il confronto con i valori effettivi.

1. Sotto il metodo `Main` creare un nuovo metodo di utilità denominato `Evaluate`.

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. All'interno del `Evaluate` metodo, prevedere i dati del secondo anno utilizzando il metodo [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) con il modello sottoposto a training.

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. Ottenere i valori effettivi dai dati tramite il metodo [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) .

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. Ottenere i valori di previsione usando il metodo [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) .

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. Calcolare la differenza tra i valori effettivi e quelli previsti, comunemente indicati come errori.

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. Misurare le prestazioni calcolando i valori di errore assoluto medio e radice media di errore quadratico.

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    Per valutare le prestazioni, vengono usate le metriche seguenti:

    - **Errore assoluto medio**: misura il modo in cui le stime di chiusura corrispondono al valore effettivo. Questo valore è compreso tra 0 e infinito. Più vicino a 0, più è alta la qualità del modello.
    - **Radice errore quadratico medio**: riepiloga l'errore nel modello. Questo valore è compreso tra 0 e infinito. Più vicino a 0, più è alta la qualità del modello.

1. Inviare le metriche alla console.

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. Usare il metodo `Evaluate` all'interno del metodo `Main`.

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a>Salvare il modello

Se si è soddisfatti del modello, salvarlo per usarlo in seguito in altre applicazioni.

1. Nel metodo `Main` creare una [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602). [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602) è un metodo pratico per eseguire stime singole.

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. Salvare il modello in un file denominato `MLModel.zip` come specificato dalla variabile `modelPath` definita in precedenza. Utilizzare il metodo [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*) per salvare il modello.

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a>Usare il modello per prevedere la domanda

1. Sotto il metodo `Evaluate` creare un nuovo metodo di utilità denominato `Forecast`.

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. All'interno del metodo `Forecast` usare il metodo [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*) per prevedere i noleggi per i sette giorni successivi.

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. Allinea i valori effettivi e di previsione per sette punti.

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. Scorrere l'output di previsione e visualizzarlo nella console.

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a>Esecuzione dell'applicazione

1. All'interno del metodo `Main`, chiamare il metodo `Forecast`.

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. Eseguire l'applicazione. Viene visualizzato un output simile al seguente nella console. Per brevità, l'output è stato condensato.

    ```text
    Evaluation Metrics
    ---------------------
    Mean Absolute Error: 726.416
    Root Mean Squared Error: 987.658

    Rental Forecast
    ---------------------
    Date: 1/1/2012
    Actual Rentals: 2294
    Lower Estimate: 1197.842
    Forecast: 2334.443
    Upper Estimate: 3471.044

    Date: 1/2/2012
    Actual Rentals: 1951
    Lower Estimate: 1148.412
    Forecast: 2360.861
    Upper Estimate: 3573.309
    ```

L'ispezione dei valori effettivi e previsti Mostra le relazioni seguenti:

![Confronto tra previsioni effettive di Visual Studio](./media/time-series-demand-forecasting/forecast.png)

Sebbene i valori previsti non prevedano il numero esatto di affitti, forniscono un intervallo più limitato di valori che consentono a un'operazione di ottimizzare l'uso delle risorse.

La procedura è stata completata. A questo punto è stato creato un modello di Machine Learning di serie temporali per prevedere la richiesta di noleggio di biciclette.

Il codice sorgente per questa esercitazione è reperibile nel repository [DotNet/machinelearning-Samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) .

## <a name="next-steps"></a>Passaggi successivi

- [Attività di Machine Learning in ML.NET](../resources/tasks.md)
- [Migliorare l'accuratezza del modello](../resources/improve-machine-learning-model-ml-net.md)

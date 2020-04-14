---
title: 'Tutorial: Prevedere la domanda di noleggio biciclette - serie di tempo'
description: Questa esercitazione illustra come prevedere la domanda per un servizio di noleggio biciclette utilizzando l'analisi di serie temporali univariate e ML.NET.
ms.date: 11/07/2019
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 962c40ea0536d6b6057d936cfc4b95a49ddadbf8
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243284"
---
# <a name="tutorial-forecast-bike-rental-service-demand-with-time-series-analysis-and-mlnet"></a>Tutorial: Prevedere la domanda di servizio di noleggio biciclette con analisi di serie temporali e ML.NET

Informazioni su come prevedere la domanda di un servizio di noleggio biciclette utilizzando l'analisi di serie temporali univariate sui dati archiviati in un database di SQL Server con ML.NET.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> * Informazioni sul problema
> * Caricare dati da un databaseLoad data from a database
> * Creare un modello di previsione
> * Valutare il modello di previsione
> * Salvare un modello di previsione
> * Utilizzare un modello di previsione

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2017 versione 15.6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro ".NET Core cross-platform development" installato.

## <a name="time-series-forecasting-sample-overview"></a>Panoramica dell'esempio di previsione di serie temporali

Questo esempio è **un'applicazione console .NET Core di C.NET** che prevede la domanda di noleggi di biciclette utilizzando un algoritmo di analisi di serie temporali univariato noto come Single Spectrum Analysis. Il codice per questo esempio è disponibile nel repository dotnet/machinelearning-samples in GitHub.The code for this sample can be found on the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) repository on GitHub.

## <a name="understand-the-problem"></a>Informazioni sul problema

Per eseguire un'operazione efficiente, la gestione dell'inventario svolge un ruolo chiave. Avere troppo di un prodotto in magazzino significa prodotti invenduti seduti sugli scaffali senza generare alcun reddito. Avere troppo poco prodotto porta a perdere vendite e clienti l'acquisto da concorrenti. Pertanto, la domanda costante è, qual è la quantità ottimale di inventario da tenere a portata di mano? L'analisi delle serie temporali consente di fornire una risposta a queste domande esaminando i dati cronologici, identificando i modelli e utilizzando queste informazioni per prevedere i valori in futuro.

La tecnica per l'analisi dei dati utilizzata in questa esercitazione è l'analisi univariate di serie temporali. L'analisi univariate di serie temporali dà un'occhiata a una singola osservazione numerica in un periodo di tempo a intervalli specifici come le vendite mensili.

L'algoritmo utilizzato in questa esercitazione è [Single Spectrum Analysis(SSA)](http://ssa.cf.ac.uk/zhigljavsky/pdfs/SSA/SSA_encyclopedia.pdf). SSA funziona scomponendo una serie temporale in un insieme di componenti principali. Questi componenti possono essere interpretati come le parti di un segnale che corrispondono a tendenze, rumore, stagionalità e molti altri fattori. Quindi, questi componenti vengono ricostruiti e utilizzati per prevedere i valori in futuro.

## <a name="create-console-application"></a>Creare un'applicazione console

1. Creare una nuova **applicazione console di .NET Core** di C, denominata "BikeDemandForecasting".
1. Installare **Microsoft.ML** pacchetto NuGet versione **1.4.0Install a version 1.4.0** NuGet package
    1. In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**.
    1. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda **Sfoglia,** cercare **Microsoft.ML**.
    1. Selezionare la casella di **controllo Includi versione non definitiva.**
    1. Selezionare il pulsante **Installa**.
    1. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo Accettazione della licenza se si accettano le condizioni di licenza per i pacchetti elencati.
    1. Ripetere questi passaggi per **System.Data.SqlClient** versione **4.7.0** e **Microsoft.ML.TimeSeries** versione **1.4.0**.

### <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

1. Creare una directory denominata *Data*.
1. Scaricare il file di database [ *DailyDemand.mdf* ](https://github.com/dotnet/machinelearning-samples/raw/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Data/DailyDemand.mdf) e salvarlo nella directory *Data.*

> [!NOTE]
> I dati utilizzati in questa esercitazione provengono dal set di dati [UCI Bike Sharing](http://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset). Fanaee-T, Hadi e Gama, Joao, "Etichettatura degli eventi che combinano rilevatori di ensemble e conoscenze di base", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, [Web Link](https://link.springer.com/article/10.1007%2Fs13748-013-0040-3).

Il set di dati originale contiene diverse colonne corrispondenti alla stagionalità e al tempo. Per brevità e poiché l'algoritmo usato in questa esercitazione richiede solo i valori di una singola colonna numerica, il set di dati originale è stato condensato per includere solo le colonne seguenti:For brevity and because the algorithm used in this tutorial only requires the values from a single numerical column, the original dataset has been condensed to include only the following columns:

- **dteday**: La data dell'osservazione.
- **anno**: L'anno codificato dell'osservazione (0-2011, 1-2012).
- **cnt**: Il numero totale di noleggi di biciclette per quel giorno.

Il set di dati originale viene mappato a una tabella di database con lo schema seguente in un database di SQL Server.The original dataset is mapped to a database table with the following schema in a SQL Server database.

```SQL
CREATE TABLE [Rentals] (
    [RentalDate] DATE NOT NULL,
    [Year] INT NOT NULL,
    [TotalRentals] INT NOT NULL
);
```

Di seguito è riportato un esempio di dati:

| RentalDate | Year | TotaleNoRentals |
| --- | --- | --- |
|1/1/2011|0|985|
|1/2/2011|0|801|
|1/3/2011|0|1349|

### <a name="create-input-and-output-classes"></a>Creare classi di input e outputCreate input and output classes

1. Aprire *Program.cs* file e `using` sostituire le istruzioni esistenti con quanto segue:

    [!code-csharp [ProgramUsings](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L1-L8)]

1. Creare la classe `ModelInput`. Sotto `Program` la classe, aggiungere il codice seguente.

    [!code-csharp [ModelInputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L120-L127)]

    La `ModelInput` classe contiene le seguenti colonne:

    - **RentalDate**: La data dell'osservazione.
    - **Anno**: L'anno codificato dell'osservazione (0-2011, 1-2012).
    - **TotalRentals**: Il numero totale di noleggi di biciclette per quel giorno.

1. Creare `ModelOutput` la classe `ModelInput` sotto la classe appena creata.

    [!code-csharp [ModelOutputClass](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L129-L136)]

    La `ModelOutput` classe contiene le seguenti colonne:

    - **ForecastedRentals**: I valori previsti per il periodo previsto.
    - **LowerBoundRentals:** valori minimi previsti per il periodo previsto.
    - **UpperBoundRentals: valori massimi previsti**per il periodo previsto.

### <a name="define-paths-and-initialize-variables"></a>Definire percorsi e inizializzare le variabiliDefine paths and initialize variables

1. All'interno del `Main` metodo, definire le variabili per archiviare la posizione dei dati, la stringa di connessione e dove salvare il modello sottoposto a training.

    [!code-csharp [DefinePaths](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L16-L19)]

1. Inizializzare `mlContext` la variabile con [`MLContext`](xref:Microsoft.ML.MLContext) una nuova istanza `Main` di aggiungendo la riga seguente al metodo.

    [!code-csharp [MLContext](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L21)]

    La [`MLContext`](xref:Microsoft.ML.MLContext) classe è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di mlContext crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

## <a name="load-the-data"></a>Caricare i dati

1. Creare `DatabaseLoader` che carica `ModelInput`i record di tipo .

    [!code-csharp [CreateDBLoader](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L23)]

1. Definire la query per caricare i dati dal database.

    [!code-csharp [DefineSQLQuery](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L25)]

    ML.NET algoritmi prevedono che [`Single`](xref:System.Single)i dati siano di tipo . Pertanto, i valori numerici provenienti [`Real`](xref:System.Data.SqlDbType)dal database che non sono di tipo , [`Real`](xref:System.Data.SqlDbType)un valore a virgola mobile a precisione singola, devono essere convertiti in .

    Le `Year` `TotalRental` colonne e sono entrambi tipi integer nel database. Utilizzando `CAST` la funzione incorporata, è `Real`stato eseguito il cast in .

1. Creare `DatabaseSource` un per connettersi al database ed eseguire la query.

    [!code-csharp [CreateDBSource](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L27-L29)]

1. Caricare i dati in un'interfaccia `IDataView`.

    [!code-csharp [LoadData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L31)]

1. Il set di dati contiene due anni di dati. Per il training vengono utilizzati solo i dati del primo anno, il secondo anno viene bloccato per confrontare i valori effettivi con quelli prodotti dal modello. Filtrare i [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) dati utilizzando la trasformazione.

    [!code-csharp [SplitData](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L33-L34)]

    Per il primo anno, solo `Year` i valori nella colonna `upperBound` minore di 1 vengono selezionati impostando il parametro su 1. Al contrario, per il secondo anno, i valori maggiori `lowerBound` o uguali a 1 vengono selezionati impostando il parametro su 1.

## <a name="define-time-series-analysis-pipeline"></a>Definire la pipeline di analisi delle serie temporaliDefine time series analysis pipeline

1. Definire una pipeline che usa [ssaForecastingEstimator](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator) per prevedere i valori in un set di dati di serie temporali.

    [!code-csharp [DefinePipeline](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L36-L45)]

    Prende `forecastingPipeline` 365 punti dati per il primo anno e campiona o divide il set di dati `seriesLength` della serie temporale in intervalli di 30 giorni (mensili) come specificato dal parametro. Ognuno di questi campioni viene analizzato attraverso una finestra settimanale o di 7 giorni. Quando si determina il valore previsto per i periodi successivi, i valori dei sette giorni precedenti vengono utilizzati per eseguire una stima. Il modello è impostato per prevedere sette periodi `horizon` nel futuro come definito dal parametro. Poiché una previsione è un'ipotesi informata, non è sempre accurata al 100%. Pertanto, è bene conoscere l'intervallo di valori negli scenari migliori e peggiori definiti dai limiti superiore e inferiore. In questo caso, il livello di attendibilità per i limiti inferiore e superiore è impostato su 95%. Il livello di confidenza può essere aumentato o diminuito di conseguenza. Più alto è il valore, più ampio è l'intervallo tra i limiti superiore e inferiore per raggiungere il livello di confidenza desiderato.

1. Utilizzare [`Fit`](xref:Microsoft.ML.Transforms.TimeSeries.SsaForecastingEstimator.Fit*) il metodo per eseguire il training del `forecastingPipeline`modello e adattare i dati all'oggetto definito in precedenza.

    [!code-csharp [TrainModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L47)]

## <a name="evaluate-the-model"></a>Valutare il modello

Valutare le prestazioni del modello prevedendo i dati dell'anno prossimo e confrontandoli con i valori effettivi.

1. Sotto `Main` il metodo, creare un `Evaluate`nuovo metodo di utilità denominato .

    ```csharp
    static void Evaluate(IDataView testData, ITransformer model, MLContext mlContext)
    {

    }
    ```

1. All'interno del `Evaluate` metodo, prevedere i dati [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) del secondo anno utilizzando il metodo con il modello sottoposto a training.

    [!code-csharp [EvaluateForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L62)]

1. Ottenere i valori effettivi dai [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) dati utilizzando il metodo .

    [!code-csharp [GetActualRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L65-L67)]

1. Ottenere i valori di [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) previsione utilizzando il metodo .

    [!code-csharp [GetForecastRentals](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L70-L72)]

1. Calcolare la differenza tra i valori effettivi e quelli di previsione, comunemente indicati come errore.

    [!code-csharp [CalculateError](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L75)]

1. Misurare le prestazioni calcolando i valori Di errore assoluto medio e Errore al quadrato radice.

    [!code-csharp [CalculateMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L78-L79)]

    Per valutare le prestazioni, vengono utilizzate le metriche seguenti:To evaluate performance, the following metrics are used:

    - **Errore assoluto medio**: misura il grado di stima ravvicinata al valore effettivo. Questo valore è compreso tra 0 e infinito. Più vicino a 0, migliore è la qualità del modello.
    - **Root Mean Squared Error**: Riepiloga l'errore nel modello. Questo valore è compreso tra 0 e infinito. Più vicino a 0, migliore è la qualità del modello.

1. Eseguire l'output delle metriche nella console.

    [!code-csharp [OutputMetrics](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L82-L85)]

1. Utilizzare `Evaluate` il metodo `Main` all'interno del metodo .

    [!code-csharp [EvaluateModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L49)]

## <a name="save-the-model"></a>Salvare il modello

Se si è soddisfatti del modello, salvarlo per un utilizzo successivo in altre applicazioni.

1. Nel `Main` metodo creare [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602)un file . [`TimeSeriesPredictionEngine`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602)è un metodo pratico per fare singole previsioni.

    [!code-csharp [CreateTimeSeriesEngine](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L51)]

1. Salvare il modello in `MLModel.zip` un file denominato `modelPath` come specificato dalla variabile definita in precedenza. Utilizzare [`Checkpoint`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.CheckPoint*) il metodo per salvare il modello.

    [!code-csharp [SaveModel](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L52)]

## <a name="use-the-model-to-forecast-demand"></a>Utilizzare il modello per prevedere la domanda

1. Sotto `Evaluate` il metodo, creare un `Forecast`nuovo metodo di utilità denominato .

    ```csharp
    static void Forecast(IDataView testData, int horizon, TimeSeriesPredictionEngine<ModelInput, ModelOutput> forecaster, MLContext mlContext)
    {

    }
    ```

1. All'interno del `Forecast` [`Predict`](xref:Microsoft.ML.Transforms.TimeSeries.TimeSeriesPredictionEngine%602.Predict*) metodo, utilizzare il metodo per prevedere gli affitti per i prossimi sette giorni.

    [!code-csharp [SingleForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L91)]

1. Allineare i valori effettivi e di previsione per sette periodi.

    [!code-csharp [GetForecastOutput](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L93-L108)]

1. Scorrere l'output di previsione e visualizzarlo nella console.

    [!code-csharp [DisplayForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L111-L116)]

## <a name="run-the-application"></a>Eseguire l'applicazione

1. All'interno del `Main` `Forecast` metodo, chiamare il metodo .

    [!code-csharp [BuildForecast](~/machinelearning-samples/samples/csharp/getting-started/Forecasting_BikeSharingDemand/BikeDemandForecasting/Program.cs#L54)]

1. Eseguire l'applicazione. L'output simile a quello riportato di seguito dovrebbe essere visualizzato nella console. Per brevità, l'output è stato condensato.

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

L'ispezione dei valori effettivi e previsti mostra le seguenti relazioni:

![Confronto effettivo rispetto a previsione](./media/time-series-demand-forecasting/forecast.png)

Mentre i valori previsti non prevedono il numero esatto di noleggi, forniscono una gamma più ristretta di valori che consente a un'operazione di ottimizzare l'uso delle risorse.

Congratulazioni! Ora hai creato con successo un modello di apprendimento automatico di serie temporali per prevedere la domanda di noleggio biciclette.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/machinelearning-samples.You](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/Forecasting_BikeSharingDemand) can find the source code for this tutorial at the dotnet/machinelearning-samples repository.

## <a name="next-steps"></a>Passaggi successivi

- [Attività di apprendimento automatico in ML.NET](../resources/tasks.md)
- [Migliorare l'accuratezza del modello](../resources/improve-machine-learning-model-ml-net.md)

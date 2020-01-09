---
title: 'Esercitazione: stimare i prezzi tramite regressione'
description: Questa esercitazione illustra come compilare un modello di regressione usando ML.NET per stimare i prezzi, in particolare le tariffe dei taxi di New York.
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0516
ms.openlocfilehash: e4014dbdfb81af65c35d2f7693ef2c57885303ff
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711623"
---
# <a name="tutorial-predict-prices-using-regression-with-mlnet"></a>Esercitazione: stimare i prezzi usando la regressione con ML.NET

Questa esercitazione illustra come creare un [modello di regressione](../resources/glossary.md#regression) usando ML.NET per stimare i prezzi, in particolare le tariffe dei taxi di New York.

In questa esercitazione si imparerà a:
> [!div class="checklist"]
>
> * Preparare e identificare i dati
> * Caricare e trasformare i dati
> * Scegliere un algoritmo di apprendimento
> * Eseguire il training del modello
> * Valutare il modello
> * Usare il modello per le stime

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Creare un'**applicazione console di .NET Core** con nome "TaxiFarePrediction".

1. Creare una directory *Data* nel progetto per archiviare il set di dati e i file di modello.

1. Installare il pacchetto NuGet **Microsoft.ML**:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine del pacchetto, selezionare la scheda **Sfoglia**, trovare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati. Eseguire la stessa operazione per il pacchetto NuGet **Microsoft.ML.FastTree**.

## <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

1. Scaricare i set di dati [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) e [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) e salvarli nella cartella *Data* creata nel passaggio precedente. Questi set di dati vengono usati per eseguire il training del modello di machine learning e quindi valutarne l'accuratezza. Questi set di dati sono originariamente ricavati dal [set di dati NYC TLC Taxi Trip](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page).

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse su ognuno dei file \*.csv e scegliere **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

1. Aprire il set di dati **taxi-fare-train.csv** e controllare le intestazioni di colonna nella prima riga. Esaminare ognuna delle colonne. Identificare i dati e decidere quali colonne sono **funzionalità** e qual è l'**etichetta**.

`label` è la colonna sulla quale eseguire le stime. Gli elementi `Features` identificati sono gli input assegnati al modello per la stima di `Label`.

Il set di dati fornito contiene le colonne seguenti:

* **vendor_id:** l'ID della società di taxi è una funzionalità.
* **rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.
* **passenger_count:** il numero di passeggeri è una funzionalità.
* **trip_time_in_secs:** il tempo impiegato per il viaggio. Si vuole stimare la tariffa del viaggio prima del termine. A questo punto, non si sa quanto tempo è necessario per il viaggio. Il tempo non è pertanto una funzionalità e si escluderà questa colonna dal modello.
* **trip_distance:** la distanza del viaggio è una funzionalità.
* **payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.
* **fare_amount:** la tariffa totale per il viaggio in taxi è l'etichetta.

## <a name="create-data-classes"></a>Creare classi di dati

Creare le classi per i dati di input e le stime:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TaxiTrip.cs*. Selezionare quindi il pulsante **Aggiungi**.
1. Aggiungere le direttive `using` seguenti al nuovo file:

   [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `TaxiTrip` e `TaxiTripFarePrediction`, al file *TaxiTrip.cs*:

[!code-csharp[DefineTaxiTrip](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` è la classe dei dati di input e contiene le definizioni per ognuna delle colonne del set di dati. Usare l'attributo <xref:Microsoft.ML.Data.LoadColumnAttribute> per specificare gli indici delle colonne di origine nel set di dati.

La classe `TaxiTripFarePrediction` rappresenta i risultati previsti. Dispone di un singolo campo float, `FareAmount`, con un attributo `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> applicato. Nel caso dell'attività di regressione, la colonna **Score** contiene i valori delle etichette stimate.

> [!NOTE]
> Usare il tipo `float` per rappresentare i valori a virgola mobile nelle classi di dati di input e di previsione.

### <a name="define-data-and-model-paths"></a>Definire i percorsi dei dati e del modello

Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

È necessario creare tre campi per i percorsi dei file con i set di dati e del file per il salvataggio del modello:

* `_trainDataPath` contiene il percorso del file con il set di dati usato per il training del modello.
* `_testDataPath` contiene il percorso del file con il set di dati usato per la valutazione del modello.
* `_modelPath` contiene il percorso del file in cui è archiviato il modello sottoposto a training.

Aggiungere il codice seguente immediatamente sopra il metodo `Main` per specificare questi percorsi e per la variabile `_textLoader`:

[!code-csharp[InitializePaths](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

Tutte le operazioni di ML.NET iniziano nella [classe MLContext](xref:Microsoft.ML.MLContext). L'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro di creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile `mlContext`:

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

Aggiungere il codice seguente come riga successiva nel metodo `Main` per chiamare il metodo `Train`:

[!code-csharp[Train](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

Il metodo `Train()` esegue le attività seguenti:

* Carica i dati.
* Estrae e trasforma i dati.
* Esegue il training del modello.
* Restituisce il modello.

Il metodo `Train` esegue il training del modello. Creare il metodo subito sotto `Main` usando il codice seguente:

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

## <a name="load-and-transform-data"></a>Caricare e trasformare i dati

ML.NET usa la [classe IDataView](xref:Microsoft.ML.IDataView) come un modo efficiente e flessibile per descrivere i dati tabulari numerici o di testo. `IDataView` può caricare file testo o in tempo reale (ad esempio, file di database SQL o di log). Aggiungere il codice seguente come prima riga del metodo `Train()`:

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

Per stimare la tariffa per le corse dei taxi, il `FareAmount` colonna è il `Label` che verrà stimato (l'output del modello). Usare la classe Transformation `CopyColumnsEstimator` per copiare `FareAmount`e aggiungere il codice seguente:

[!code-csharp[CopyColumnsEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

Poiché l'algoritmo che esegue il training del modello richiede funzionalità **numeriche**, è necessario trasformare i dati relativi alle categorie (`VendorId`, `RateCode` e `PaymentType`) in numeri (`VendorIdEncoded`, `RateCodeEncoded` e `PaymentTypeEncoded`). Per fare ciò usare la classe di trasformazione [OneHotEncodingTransformer](xref:Microsoft.ML.Transforms.OneHotEncodingTransformer), che assegna valori chiave numerica diversi ai differenti valori in ognuna delle colonne e quindi aggiungere il codice seguente:

[!code-csharp[OneHotEncodingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando la classe di trasformazione `mlContext.Transforms.Concatenate`. Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**. Aggiungere il codice seguente:

[!code-csharp[ColumnConcatenatingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a>Scegliere un algoritmo di apprendimento

Questo problema riguarda la stima del costo di una corsa in taxi nella città di New York. A prima vista, potrebbe sembrare dipendere semplicemente dalla distanza percorsa. Tuttavia, le società di taxi di New York applicano un addebito per quantità variabili di altri fattori, come i passeggeri aggiuntivi o il pagamento tramite carta di credito anziché in contanti. Si vuole stimare il valore del prezzo, ovvero un valore reale, in base ad altri fattori nel set di dati. Per fare ciò, scegliere un'attività di apprendimento automatico di tipo [regressione](../resources/glossary.md#regression).

Aggiungere l'attività di apprendimento automatico [FastTreeRegressionTrainer](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer) alle definizioni di trasformazione dei dati aggiungendo il codice seguente come riga successiva in `Train()`:

[!code-csharp[FastTreeRegressionTrainer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a>Eseguire il training del modello

Adattare il modello all'elemento di training `dataview` e restituire il modello sottoposto a training aggiungendo la seguente riga di codice al metodo `Train()`:

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

Il metodo [Fit()](xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) esegue il training del modello trasformando il set di dati e applicando il training.

Restituire il modello di cui è stato eseguito il training con la riga di codice seguente nel metodo `Train()`:

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Return the model")]

## <a name="evaluate-the-model"></a>Valutare il modello

In seguito valutare le prestazioni del modello con i dati di test, per la convalida e il controllo di qualità. Creare il metodo `Evaluate()` subito dopo `Train()` con il codice seguente:

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

Il metodo `Evaluate` esegue le attività seguenti:

* Carica il set di dati di test.
* Crea l'analizzatore della regressione.
* Valuta il modello e crea le metriche.
* Visualizza le metriche.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Train`, usando il codice seguente:

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

Caricare il set di dati di test usando il metodo [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%2A). Valutare il modello usando il set di dati come controllo di qualità tramite l'aggiunta del codice seguente nel metodo `Evaluate`:

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

Quindi trasformare i dati `Test` aggiungendo il codice seguente a `Evaluate()`:

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

Il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) esegue stime per le righe di input della serie di dati di test.

Il metodo `RegressionContext.Evaluate` calcola le metriche di qualità per l'istanza di `PredictionModel` usando il set di dati specificato. Restituisce un oggetto <xref:Microsoft.ML.Data.RegressionMetrics> che contiene le metriche complessive calcolate dagli analizzatori della regressione.

Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche. Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

Dopo aver impostato la previsione, il metodo [Evaluate()](xref:Microsoft.ML.RegressionCatalog.Evaluate%2A) valuta il modello confrontando i valori stimati con gli oggetti `Labels` effettivi presenti nel set di dati di test e restituisce le metriche relative alle prestazioni del modello.

Aggiungere il codice seguente per valutare il modello e produrre le metriche di valutazione:

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

[RSquared](../resources/glossary.md#coefficient-of-determination) è un'altra metrica di valutazione dei modelli di regressione. Accetta valori compresi tra 0 e 1. I valori più vicini a 1 producono modelli migliori. Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RSquared:

[!code-csharp[DisplayRSquared](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

[RMS](../resources/glossary.md#root-of-mean-squared-error-rmse) è una delle metriche di valutazione del modello di regressione. Più basso è il valore, migliore è il modello. Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RMS:

[!code-csharp[DisplayRMS](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a>Usare il modello per le stime

Creare il metodo `TestSinglePrediction` subito dopo il metodo `Evaluate`, usando il codice seguente:

```csharp
private static void TestSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

Il metodo `TestSinglePrediction` esegue le attività seguenti:

* Crea un singolo commento di dati di test.
* Esegue la stima dell'importo della tariffa in base ai dati di test.
* Combina i dati di test e le stime per i report.
* Visualizza i risultati stimati.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:

[!code-csharp[CallTestSinglePrediction](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

Usare `PredictionEngine` per stimare l'importo della tariffa aggiungendo il codice seguente a `TestSinglePrediction()`:

[!code-csharp[MakePredictionEngine](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]

[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) non è thread-safe. È accettabile usare in ambienti a thread singolo o prototipi. Per migliorare le prestazioni e thread safety negli ambienti di produzione, usare il servizio `PredictionEnginePool`, che consente di creare un [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da usare nell'applicazione. Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

> [!NOTE]
> L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

In questa esercitazione viene usato un solo viaggio di test all'interno di questa classe. Successivamente, è possibile aggiungere altri scenari da sperimentare con il modello. Aggiungere una corsa per testare la stima dei costi del modello sottoposto a training nel metodo `TestSinglePrediction()` creando un'istanza di `TaxiTrip`:

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

Successivamente eseguire la stima della tariffa in base a una singola istanza dei dati relativi al viaggio in taxi e passarla a `PredictionEngine` aggiungendo il codice seguente come righe successive di codice nel metodo `TestSinglePrediction()`:

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) esegue una stima su una singola istanza di dati.

Per visualizzare la tariffa stimata della corsa specificata, aggiungere il codice seguente nel metodo `TestSinglePrediction`:

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

Eseguire il programma per visualizzare la tariffa del taxi stimata per il test case.

La procedura è stata completata. È stato creato un modello di machine learning per la stima delle tariffe delle corse in taxi e ne è stata valutata l'accuratezza, quindi il modello è stato usato per produrre stime. È possibile trovare il codice sorgente per questa esercitazione nel repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:

> [!div class="checklist"]
>
> * Preparare e identificare i dati
> * Creare una pipeline di apprendimento
> * Caricare e trasformare i dati
> * Scegliere un algoritmo di apprendimento
> * Eseguire il training del modello
> * Valutare il modello
> * Usare il modello per le stime

Passare all'esercitazione successiva per altre informazioni.

> [!div class="nextstepaction"]
> [Clustering Iris](iris-clustering.md)

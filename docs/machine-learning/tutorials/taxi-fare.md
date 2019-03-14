---
title: Eseguire una stima dei prezzi usando un algoritmo di apprendimento basato sulla regressione con ML.NET
description: Eseguire una stima dei prezzi usando un algoritmo di apprendimento basato sulla regressione con ML.NET.
author: aditidugar
ms.author: johalex
ms.date: 03/05/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 543411f58f2d7c5c4e8658bd90cf52c7a3291ec3
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678393"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a>Esercitazione: Eseguire una stima dei prezzi usando un algoritmo di apprendimento basato sulla regressione con ML.NET

Questa esercitazione illustra come usare ML.NET per creare un [modello di regressione](../resources/glossary.md#regression) per la stima dei prezzi, precisamente delle tariffe dei taxi a New York.

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa esercitazione e l'esempio correlato usano attualmente **ML.NET versione 0.10**. Per altre informazioni, vedere le note sulla versione nel [repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> * Informazioni sul problema
> * Selezionare l'attività di apprendimento automatico appropriata
> * Preparare e identificare i dati
> * Creare una pipeline di apprendimento
> * Caricare e trasformare i dati
> * Scegliere un algoritmo di apprendimento
> * Eseguire il training del modello
> * Valutare il modello
> * Usare il modello per le stime

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.

## <a name="understand-the-problem"></a>Informazioni sul problema

Questo problema riguarda la stima della tariffa di un viaggio in taxi a New York. A prima vista, potrebbe sembrare dipendere semplicemente dalla distanza percorsa. Tuttavia, le società di taxi di New York applicano un addebito per quantità variabili di altri fattori, come i passeggeri aggiuntivi o il pagamento tramite carta di credito anziché in contanti.

## <a name="select-the-appropriate-machine-learning-task"></a>Selezionare l'attività di apprendimento automatico appropriata

Si vuole stimare il valore del prezzo, ovvero un valore reale, in base ad altri fattori nel set di dati. Per fare ciò, scegliere un'attività di apprendimento automatico di tipo [regressione](../resources/glossary.md#regression).

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**. Selezionare quindi il modello di progetto **App console (.NET Core)**. Nella casella di testo **Nome** digitare "TaxiFarePrediction" e quindi selezionare il pulsante **OK**.

1. Creare una directory denominata *Dati* nel progetto per salvare i file del set di dati e del modello:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**. Digitare "Data" e premere INVIO.

1. Installare il pacchetto NuGet **Microsoft.ML**:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda **Sfoglia**, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

## <a name="prepare-and-understand-the-data"></a>Preparare e identificare i dati

1. Scaricare i set di dati [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) e [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) e salvarli nella cartella *Data* creata nel passaggio precedente. Questi set di dati vengono usati per eseguire il training del modello di machine learning e quindi valutarne l'accuratezza. Questi set di dati sono originariamente ricavati dal [set di dati NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse su ognuno dei file \*.csv e scegliere **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

1. Aprire il set di dati **taxi-fare-train.csv** e controllare le intestazioni di colonna nella prima riga. Esaminare ognuna delle colonne. Identificare i dati e decidere quali colonne sono **funzionalità** e qual è l'**etichetta**.

L'**etichetta** è l'identificatore della colonna che si vuole stimare. Le **funzionalità** identificate vengono usate per stimare l'etichetta.

Il set di dati fornito contiene le colonne seguenti:

* **vendor_id:** l'ID della società di taxi è una funzionalità.
* **rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.
* **passenger_count:** il numero di passeggeri è una funzionalità.
* **trip_time_in_secs:** il tempo impiegato per il viaggio. Si vuole stimare la tariffa del viaggio prima del termine. Al momento non si conosce la durata del viaggio. Il tempo non è pertanto una funzionalità e si escluderà questa colonna dal modello.
* **trip_distance:** la distanza del viaggio è una funzionalità.
* **payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.
* **fare_amount:** la tariffa totale corrisposta per il viaggio in taxi è l'etichetta.

## <a name="create-data-classes"></a>Creare classi di dati

Creare le classi per i dati di input e le stime:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TaxiTrip.cs*. Selezionare quindi il pulsante **Aggiungi**.
1. Aggiungere le direttive `using` seguenti al nuovo file:

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `TaxiTrip` e `TaxiTripFarePrediction`, al file *TaxiTrip.cs*:

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` è la classe dei dati di input e contiene le definizioni per ognuna delle colonne del set di dati. Usare l'attributo <xref:Microsoft.ML.Data.ColumnAttribute> per specificare gli indici delle colonne di origine nel set di dati.

La classe `TaxiTripFarePrediction` rappresenta i risultati previsti. Ha un singolo campo float, `FareAmount`, a cui è applicato un attributo `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute>. Nel caso dell'attività di regressione, la colonna **Score** contiene i valori delle etichette previsti.

> [!NOTE]
> Usare il tipo `float` per rappresentare i valori a virgola mobile nelle classi di dati di input e di previsione.

## <a name="define-data-and-model-paths"></a>Definire i percorsi dei dati e del modello

Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

È necessario creare tre campi per i percorsi dei file con i set di dati e del file per il salvataggio del modello, oltre a una variabile globale per l'istanza di `TextLoader`:

* `_trainDataPath` contiene il percorso del file con il set di dati usato per il training del modello.
* `_testDataPath` contiene il percorso del file con il set di dati usato per la valutazione del modello.
* `_modelPath` contiene il percorso del file in cui è archiviato il modello sottoposto a training.
* `_textLoader` è l'istanza della classe <xref:Microsoft.ML.Data.TextLoader> usata per caricare e trasformare i set di dati.

Aggiungere il codice seguente immediatamente sopra il metodo `Main` per specificare questi percorsi e per la variabile `_textLoader`:

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

Quando si crea un modello con ML.NET, si inizia creando un contesto di apprendimento automatico. A livello concettuale questa operazione è paragonabile all'uso di `DbContext` in Entity Framework. L'ambiente offre un contesto per il processo di apprendimento automatico che può essere usato per il rilevamento e la registrazione di eccezioni.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

Creare una variabile denominata `mlContext` e inizializzarla con una nuova istanza di `MLContext`.  Sostituire la riga `Console.WriteLine("Hello World!")` con il codice seguente nel metodo `Main`:

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

Successivamente, per configurare il caricamento dei dati, inizializzare la variabile globale `_textLoader` in modo da poterla riutilizzare. Quando si crea un'istanza di `TextLoader` si passa il contesto necessario e la classe <xref:Microsoft.ML.Data.TextLoader.Arguments>che consente la personalizzazione. Specificare lo schema di dati passando una matrice di oggetti <xref:Microsoft.ML.Data.TextLoader.Column> all'istanza di `TextLoader` contenente tutti i nomi delle colonne e i relativi tipi. Lo schema di dati è stato definito in precedenza quando si è creata la classe `TaxiTrip`.

La classe `TextLoader` restituisce un'istanza di <xref:Microsoft.ML.Data.TextLoader> completamente inizializzata.  

Per inizializzare la variabile globale `_textLoader` in modo da riutilizzarla per i set di dati necessari, aggiungere il codice seguente dopo l'inizializzazione di `mlContext`:

[!code-csharp[initTextLoader](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Initialize the TextLoader")]

Aggiungere il codice seguente come riga successiva nel metodo `Main` per chiamare il metodo `Train`:

[!code-csharp[Train](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

Il metodo `Train` esegue le attività seguenti:

* Carica i dati.
* Estrae e trasforma i dati.
* Esegue il training del modello.
* Salva il modello come file con estensione zip.
* Restituisce il modello.

Il metodo `Train` esegue il training del modello. Creare il metodo subito sotto `Main` usando il codice seguente:

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

In questo modo vengono passati due parametri al metodo `Train`: `MLContext` per il contesto (`mlContext`) e una stringa per il percorso del set di dati (`dataPath`). Questo metodo verrà usato di nuovo per il caricamento dei set di dati.

## <a name="load-and-transform-data"></a>Caricare e trasformare i dati

Si caricheranno i dati usando la variabile globale `_textLoader` con il parametro `dataPath`. Verrà restituita un'istanza di <xref:Microsoft.Data.DataView.IDataView>. Come input e output delle trasformazioni, una `IDataView` è il tipo di pipeline di dati fondamentale, paragonabile a `IEnumerable` per `LINQ`.

In ML.NET i dati sono simili a una visualizzazione SQL. Vengono valutati in modalità differita, sono schematizzati ed eterogenei. L'oggetto è la prima parte della pipeline e carica i dati. Per questa esercitazione, carica un set di dati con le informazioni sulle corse in taxi che sono utili per eseguire una stima delle tariffe. Queste informazioni vengono usate per creare il modello ed eseguirne il training.

 Aggiungere il codice seguente come prima riga del metodo `Train`:

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

Nei passaggi successivi si fa riferimento alle colonne in base ai nomi definiti nella classe `TaxiTrip`.

Quando vengono eseguiti il training e la valutazione del modello, i valori nella colonna **Label** vengono considerati per impostazione predefinita come valori corretti da stimare. Dato che si vuole stimare la tariffa del viaggio in taxi, copiare la colonna `FareAmount` nella colonna **Label**. A tale scopo, usare la classe di trasformazione `CopyColumnsEstimator` e aggiungere il codice seguente:

[!code-csharp[CopyColumnsEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

Poiché l'algoritmo che esegue il training del modello richiede funzionalità **numeriche**, è necessario trasformare i dati relativi alle categorie (`VendorId`, `RateCode` e `PaymentType`) in numeri. A questo scopo, usare la classe di trasformazione `OneHotEncodingEstimator`, che assegna valori chiave numerici diversi ai vari valori in ogni colonna e aggiunge il codice seguente:

[!code-csharp[OneHotEncodingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando la classe di trasformazione `ColumnConcatenatingEstimator`. Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**. Aggiungere il codice seguente:

[!code-csharp[ColumnConcatenatingEstimator](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a>Scegliere un algoritmo di apprendimento

Dopo aver aggiunto i dati alla pipeline e averli trasformati nel formato di input corretto, si seleziona un **algoritmo di apprendimento**. L'algoritmo di apprendimento esegue il training del modello. Per questo problema è stata scelta un'attività di **regressione** ed è quindi necessario usare un algoritmo di apprendimento `FastTreeRegressionTrainer`, che è uno degli algoritmi di apprendimento basati sulla regressione disponibili in ML.NET.

L'algoritmo di apprendimento `FastTreeRegressionTrainer` utilizza la tecnica di gradient boosting. L'incremento dei gradienti è una tecnica di apprendimento automatico per i problemi di regressione. Compila ogni albero di regressione tenendo conto dei singoli passaggi. Usa una funzione di perdita predefinita per misurare l'errore in ogni passaggio e correggerlo in quello successivo. Il risultato è un modello di stima che è effettivamente un insieme dei modelli di stima più deboli. Per altre informazioni sull'incremento dei gradienti, vedere [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regressione dell'albero delle decisioni con incremento).

Aggiungere il codice seguente nel metodo `Train` per includere l'algoritmo `FastTreeRegressionTrainer` nel codice di elaborazione dei dati aggiunto nel passaggio precedente:

[!code-csharp[FastTreeRegressionTrainer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a>Eseguire il training del modello

Il passaggio finale consiste nel training del modello. Il training del modello, <xref:Microsoft.ML.Data.TransformerChain>, viene eseguito in base al set di dati caricato e trasformato. Dopo aver definito l'algoritmo di stima, si esegue il training del modello usando il metodo <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> e fornendo i dati di training già caricati. Viene così restituito un modello da usare per le stime. `pipeline.Fit()` esegue il training della pipeline e restituisce un oggetto `Transformer` in base alla `DataView` passata. L'esperimento non viene eseguito finché questa operazione non è stata completata.

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

L'operazione è ora completata. È stato eseguito il training di un modello di apprendimento automatico in grado di prevedere le tariffe dei taxi a New York. A questo punto occorre determinare il livello di accuratezza del modello e imparare a usarlo per stimare i valori delle tariffe dei taxi.

### <a name="save-the-model"></a>Salvare il modello

A questo punto, si ha un modello di tipo <xref:Microsoft.ML.Data.TransformerChain> che può essere integrato nelle applicazioni .NET nuove o esistenti. Per salvare il modello in un file con estensione zip, aggiungere il codice seguente alla fine del metodo `Train`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a>Salvare il modello come file con estensione zip

Creare il metodo `SaveModelAsFile` subito dopo il metodo `Train`, usando il codice seguente:

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

Il metodo `SaveModelAsFile` esegue le attività seguenti:

* Salva il modello come file con estensione zip.

È necessario creare un metodo per salvare il modello in modo da poterlo riutilizzare in altre applicazioni. L'interfaccia `ITransformer` ha un metodo <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> che accetta il campo globale `_modelPath` e un'istanza della classe <xref:System.IO.Stream>. Poiché si vuole salvare il modello come file con estensione zip, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `SaveTo`. Aggiungere il codice seguente al metodo `SaveModelAsFile` come riga successiva:

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

È anche possibile visualizzare il percorso in cui è stato salvato il file scrivendo un messaggio della console con il campo `_modelPath` tramite il codice seguente:

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a>Valutare il modello

La valutazione è il processo di verifica dell'efficacia del modello nella stima dei valori delle etichette. È importante che il modello formuli stime corrette su dati che non sono stati usati per eseguire il training del modello stesso. Un modo per eseguire questa operazione è suddividere i dati in training set e set di dati di test, come descritto in questa esercitazione. Ora che è stato eseguito il training del modello sui dati di training, è possibile verificarne le prestazioni sui dati di test.

Il metodo `Evaluate` valuta il modello. Per creare tale metodo, aggiungere il codice seguente dopo il metodo `Train`:

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

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

Si caricherà il set di dati di test usando la variabile globale `_textLoader` inizializzata in precedenza con il campo globale `_testDataPath`. È possibile valutare il modello usando questo set di dati come controllo di qualità. Aggiungere al metodo `Evaluate` il codice seguente:

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

Si userà quindi il parametro `model` di apprendimento automatico (un oggetto Transformer) per l'input di caratteristiche e la generazione di stime. Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

Il metodo `RegressionContext.Evaluate` calcola le metriche di qualità per l'istanza di `PredictionModel` usando il set di dati specificato. Restituisce un oggetto <xref:Microsoft.ML.Data.RegressionMetrics> che contiene le metriche complessive calcolate dagli analizzatori della regressione. Per visualizzare tali elementi per determinare la qualità del modello, è prima necessario ottenere le metriche. Aggiungere il codice seguente al metodo `Evaluate` come riga successiva:

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

Aggiungere il codice seguente per valutare il modello e produrre le metriche di valutazione:

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

[RSquared](../resources/glossary.md#coefficient-of-determination) è un'altra metrica di valutazione dei modelli di regressione. Accetta valori compresi tra 0 e 1. I valori più vicini a 1 producono modelli migliori. Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RSquared:

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) è una delle metriche di valutazione del modello di regressione. Più basso è il valore, migliore è il modello. Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RMS:

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a>Usare il modello per le stime


## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a>Stimare il risultato dei dati di test con il modello e un singolo commento

Creare il metodo `TestSinglePrediction` subito dopo il metodo `Evaluate`, usando il codice seguente:

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

Il metodo `TestSinglePrediction` esegue le attività seguenti:

* Crea un singolo commento di dati di test.
* Esegue la stima dell'importo della tariffa in base ai dati di test.
* Combina i dati di test e le stime per i report.
* Visualizza i risultati stimati.

Aggiungere una chiamata al nuovo metodo dal metodo `Main`, subito sotto la chiamata al metodo `Evaluate`, usando il codice seguente:

[!code-csharp[CallTestSinglePrediction](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

Poiché si vuole caricare il modello dal file con estensione zip salvato, si creerà l'oggetto `FileStream` subito prima di chiamare il metodo `Load`. Aggiungere il codice seguente al metodo `TestSinglePrediction` come riga successiva:

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

`model` è un oggetto `transformer` che opera su molte righe di dati, ma in un ambiente produzione è spesso necessario eseguire stime su singoli esempi. <xref:Microsoft.ML.PredictionEngine%602> è un wrapper che viene restituito dal metodo `CreatePredictionEngine`. A questo punto si aggiunge il codice seguente per creare `PredictionEngine` come riga successiva nel metodo `TestSinglePrediction`:

[!code-csharp[MakePredictionEngine](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]
  
In questa esercitazione viene usato un solo viaggio di test all'interno di questa classe. Successivamente, è possibile aggiungere altri scenari da sperimentare con il modello. Aggiungere una corsa per testare la stima dei costi del modello sottoposto a training nel metodo `TestSinglePrediction` creando un'istanza di `TaxiTrip`:

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

 È possibile usare questa corsa per stimare la tariffa in base a una singola istanza dei dati relativi alle corse in taxi. Per ottenere una stima, usare <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> sui dati. Si noti che i dati di input sono una stringa e che il modello include l'estrazione delle funzionalità. La pipeline è sincronizzata durante il training e la stima. Non è necessario scrivere codice di pre-elaborazione/estrazione delle funzionalità specifico per le stime e la stessa API gestisce sia le stime in batch che quelle eseguite una sola volta.

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

Per visualizzare la tariffa stimata della corsa specificata, aggiungere il codice seguente nel metodo `TestSinglePrediction`:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

Eseguire il programma per visualizzare la tariffa del taxi stimata per il test case.

La procedura è stata completata. È stato creato un modello di machine learning per la stima delle tariffe delle corse in taxi e ne è stata valutata l'accuratezza, quindi il modello è stato usato per produrre stime. È possibile trovare il codice sorgente per questa esercitazione nel repository GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> * Informazioni sul problema
> * Selezionare l'attività di apprendimento automatico appropriata
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

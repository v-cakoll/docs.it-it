---
title: Usare ML.NET per stimare le tariffe dei taxi a New York (regressione)
description: Informazioni su come usare ML.NET in uno scenario di regressione.
author: aditidugar
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bfae97d65ec192e9289841c82d84807b4937b09a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183815"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a>Esercitazione: Usare ML.NET per stimare le tariffe dei taxi a New York (regressione)

> [!NOTE]
> Questo argomento si riferisce a ML.NET, che è attualmente in anteprima, e il materiale può essere soggetto a modifiche. Per altre informazioni, vedere l'[introduzione a ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Questa esercitazione illustra come usare ML.NET per creare un [modello di regressione](../resources/glossary.md#regression) per la stima delle tariffe dei taxi a New York.

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
* **fare_amount:** la tariffa totale per il viaggio in taxi è l'etichetta.

## <a name="create-data-classes"></a>Creare classi di dati

Creare le classi per i dati di input e le stime:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TaxiTrip.cs*. Selezionare quindi il pulsante **Aggiungi**.
1. Aggiungere le direttive `using` seguenti al nuovo file:

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `TaxiTrip` e `TaxiTripFarePrediction`, al file *TaxiTrip.cs*:

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` è la classe dei dati di input e contiene le definizioni per ognuna delle colonne del set di dati. Usare l'attributo [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) per specificare gli indici delle colonne di origine nel set di dati.

La classe `TaxiTripFarePrediction` rappresenta i risultati previsti. Ha un singolo campo float, `FareAmount`, a cui è applicato un attributo `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute). Nel caso dell'attività di regressione, la colonna **Score** contiene i valori delle etichette previsti.

> [!NOTE]
> Usare il tipo `float` per rappresentare i valori a virgola mobile nelle classi di dati di input e di previsione.

## <a name="define-data-and-model-paths"></a>Definire i percorsi dei dati e del modello

Tornare al file *Program.cs* e aggiungere tre campi per i percorsi dei file con i set di dati e del file per il salvataggio del modello:

* `_datapath` contiene il percorso del file con il set di dati usato per il training del modello.
* `_testdatapath` contiene il percorso del file con il set di dati usato per la valutazione del modello.
* `_modelpath` contiene il percorso del file in cui è archiviato il modello sottoposto a training.

Aggiungere il codice seguente immediatamente sopra il metodo `Main` per specificare questi percorsi:

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

Per consentire la compilazione del codice precedente, aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsingsForPaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Using statements for path definitions")]

## <a name="create-a-learning-pipeline"></a>Creare una pipeline di apprendimento

Aggiungere le direttive `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

Nel metodo `Main` sostituire `Console.WriteLine("Hello World!")` con il codice seguente:

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

Il metodo `Train` esegue il training del modello. Creare il metodo subito sotto `Main` usando il codice seguente:

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

La pipeline di apprendimento carica tutti i dati e gli algoritmi necessari per il training del modello. Aggiungere nel metodo `Train` il codice seguente:

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-data"></a>Caricare e trasformare i dati

Il primo passaggio da eseguire consiste nel caricare i dati dal training set. Nel caso di questo esempio il training set è archiviato nel file di testo con un percorso definito dal campo `_datapath`. Il file include l'intestazione con i nomi di colonna, quindi la prima riga deve essere ignorata durante il caricamento dei dati. Le colonne nel file sono separate da una virgola (","). Aggiungere nel metodo `Train` il codice seguente:

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(useHeader: true, separator: ','));
```

Nei passaggi successivi si fa riferimento alle colonne in base ai nomi definiti nella classe `TaxiTrip`.

Quando vengono eseguiti il training e la valutazione del modello, i valori nella colonna **Label** vengono considerati per impostazione predefinita come valori corretti da stimare. Dato che si vuole stimare la tariffa del viaggio in taxi, copiare la colonna `FareAmount` nella colonna **Label**. A questo scopo usare <xref:Microsoft.ML.Legacy.Transforms.ColumnCopier> e aggiungere il codice seguente:

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

Poiché l'algoritmo che esegue il training del modello richiede funzionalità **numeriche**, è necessario trasformare i dati relativi alle categorie (`VendorId`, `RateCode` e `PaymentType`) in numeri. A questo scopo usare <xref:Microsoft.ML.Legacy.Transforms.CategoricalOneHotVectorizer>, che assegna valori chiave numerici diversi ai diversi valori in ogni colonna e aggiunge il codice seguente:

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

L'ultimo passaggio della preparazione dei dati combina tutte le colonne di funzionalità nella colonna **Features** usando la classe di trasformazione <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator>. Per impostazione predefinita, un algoritmo di apprendimento elabora solo le funzionalità della colonna **Features**. Aggiungere il codice seguente:

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

Si noti che la colonna `TripTime`, che corrisponde alla colonna `trip_time_in_secs` nel file del set di dati, non è inclusa. È già stato determinato che non si tratta di una funzionalità di stima utile.

> [!NOTE]
> Questi passaggi devono essere aggiunti alla pipeline nell'ordine specificato in precedenza per garantire la corretta esecuzione.

## <a name="choose-a-learning-algorithm"></a>Scegliere un algoritmo di apprendimento

Dopo aver aggiunto i dati alla pipeline e averli trasformati nel formato di input corretto, selezionare un **algoritmo di apprendimento**. L'algoritmo di apprendimento esegue il training del modello. Per questo problema è stata scelta un'attività di **regressione**, quindi occorre aggiungere un algoritmo di apprendimento <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor>, che è uno degli algoritmi di apprendimento di regressione specificati da ML.NET.

L'algoritmo di apprendimento <xref:Microsoft.ML.Legacy.Trainers.FastTreeRegressor> utilizza l'incremento dei gradienti. L'incremento dei gradienti è una tecnica di apprendimento automatico per i problemi di regressione. Compila ogni albero di regressione tenendo conto dei singoli passaggi. Usa una funzione di perdita predefinita per misurare l'errore in ogni passaggio e correggerlo in quello successivo. Il risultato è un modello di stima che è effettivamente un insieme dei modelli di stima più deboli. Per altre informazioni sull'incremento dei gradienti, vedere [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regressione dell'albero delle decisioni con incremento).

Aggiungere il codice seguente nel metodo `Train` dopo il codice di elaborazione dei dati aggiunto nel passaggio precedente:

```csharp
pipeline.Add(new FastTreeRegressor());
```

Tutti i passaggi precedenti sono stati aggiunti alla pipeline come singole istruzioni, ma C# presenta un'utile sintassi di inizializzazione della raccolta che rende più semplice creare e inizializzare la pipeline. Sostituire il codice aggiunto finora al metodo `Train` con il codice seguente:

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a>Eseguire il training del modello

Il passaggio finale consiste nel training del modello. Fino a questo punto, non è stato eseguito alcun elemento nella pipeline. Il metodo `pipeline.Train<TInput, TOutput>` produce il modello che accetta un'istanza del tipo `TInput` e restituisce un'istanza del tipo `TOutput`. Aggiungere nel metodo `Train` il codice seguente:

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

L'operazione è ora completata. È stato eseguito il training di un modello di apprendimento automatico in grado di prevedere le tariffe dei taxi a New York. A questo punto occorre determinare il livello di accuratezza del modello e imparare a usarlo per stimare i valori delle tariffe dei taxi.

### <a name="save-the-model"></a>Salvare il modello

A questo punto, è disponibile un modello che può essere integrato in tutte le applicazioni .NET nuove o esistenti. Per salvare il modello in un file con estensione zip, aggiungere il codice seguente alla fine del metodo `Train`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

L'aggiunta dell'istruzione `await` alla chiamata `model.WriteAsync` significa che il metodo `Train` deve essere cambiato in un metodo asincrono che restituisce un'attività. Modificare la firma di `Train` come illustrato nel codice seguente:

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

Con la modifica del tipo restituito del metodo `Train`, è necessario aggiungere un `await` al codice che chiama `Train` nel metodo `Main`, come illustrato nel codice seguente:

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

L'uso di `await` nel metodo `Main` implica che il metodo `Main` deve avere il modificatore `async` e restituire un elemento `Task`:

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

È anche necessario aggiungere la direttiva `using` seguente all'inizio del file:

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

Poiché il metodo `async Main` è la funzionalità aggiunta in C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva. A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**. Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**. Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva). Selezionare il pulsante **OK** .

## <a name="evaluate-the-model"></a>Valutare il modello

La valutazione è il processo di verifica dell'efficacia del modello nella stima dei valori delle etichette. È importante che il modello formuli stime corrette su dati che non sono stati usati per eseguire il training del modello stesso. Un modo per eseguire questa operazione è suddividere i dati in training set e set di dati di test, come descritto in questa esercitazione. Ora che è stato eseguito il training del modello sui dati di training, è possibile verificarne le prestazioni sui dati di test.

Tornare al metodo `Main` e aggiungere il codice seguente dopo la chiamata al metodo `Train`:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

Il metodo `Evaluate` valuta il modello. Per creare tale metodo, aggiungere il codice seguente dopo il metodo `Train`:

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

Aggiungere il codice seguente nel metodo `Evaluate` per configurare il caricamento dei dati di test:

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

Aggiungere il codice seguente per valutare il modello e produrre le metriche di valutazione:

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) è una delle metriche di valutazione del modello di regressione. Più basso è il valore, migliore è il modello. Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RMS:

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

[RSquared](../resources/glossary.md#coefficient-of-determination) è un'altra metrica di valutazione dei modelli di regressione. Accetta valori compresi tra 0 e 1. I valori più vicini a 1 producono modelli migliori. Aggiungere il codice seguente nel metodo `Evaluate` per visualizzare il valore di RSquared:

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a>Usare il modello per le stime

Creare una classe per ospitare le istanze dei dati di test:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TestTrips.cs*. Selezionare quindi il pulsante **Aggiungi**.
1. Modificare la classe in modo da renderla statica, come nell'esempio seguente:

   [!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

In questa esercitazione viene usato un solo viaggio di test all'interno di questa classe. Successivamente, è possibile aggiungere altri scenari da sperimentare con il modello. Aggiungere il codice seguente nella classe `TestTrips`:

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

La tariffa effettiva del viaggio è 29,5. Usare 0 come segnaposto, in quanto il modello stimerà la tariffa.

Per stimare la tariffa del viaggio specificato, tornare al file *Program.cs* e aggiungere il codice seguente nel metodo `Main`:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

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

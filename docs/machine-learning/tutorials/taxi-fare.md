---
title: Usare ML.NET per stimare le tariffe dei taxi a New York (regressione)
description: Informazioni su come usare ML.NET in uno scenario di regressione.
author: aditidugar
ms.author: johalex
ms.date: 06/05/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 048ed1d38408c1ba4901c554cae33d5552c9e303
ms.sourcegitcommit: 5b0802832fb9ad684d34e69b8644a16a5b7c4810
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2018
ms.locfileid: "34860673"
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

* [Visual Studio 2017 15.6 o versione successiva](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.

## <a name="understand-the-problem"></a>Informazioni sul problema

Questo problema è incentrato sulla **stima della tariffa di un viaggio in taxi a New York**. A prima vista, potrebbe sembrare dipendere semplicemente dalla distanza percorsa. Tuttavia, le società di taxi di New York applicano un addebito per quantità variabili di altri fattori, come i passeggeri aggiuntivi o il pagamento tramite carta di credito anziché in contanti.

## <a name="select-the-appropriate-machine-learning-task"></a>Selezionare l'attività di apprendimento automatico appropriata

Per stimare le tariffe dei taxi, è innanzitutto necessario selezionare l'attività di apprendimento automatico appropriata. L'obiettivo è stimare valori reali (un valore double che rappresenta il prezzo) in base ad altri fattori nel set di dati. Si sceglie un'attività di [ **regressione**](../resources/glossary.md#regression).

Il processo di training del modello identifica i fattori nel set di dati più influenti per la stima del prezzo finale.

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Aprire Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo **Nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core**. Selezionare quindi il modello di progetto **App console (.NET Core)**. Nella casella di testo **Nome** digitare "TaxiFarePrediction" e quindi selezionare il pulsante **OK**.

2. Creare una directory denominata *Data* nel progetto per salvare i file del set di dati:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e selezionare **Aggiungi** > **Nuova cartella**. Digitare "Data" e premere INVIO.

3. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati.

### <a name="prepare-and-understand-your-data"></a>Preparare e identificare i dati

1. Scaricare i set di dati [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) e [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) e salvarli nella cartella *Data* creata in precedenza. Il set di dati Taxi Trip esegue il training del modello di apprendimento automatico e può essere usato per valutare il livello di accuratezza del modello. Questi set di dati sono originariamente ricavati dal [set di dati NYC TLC Taxi Trip](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).

2. In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione csv e selezionare **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Sempre**.

3. Aprire il set di dati **taxi-fare-train.csv** nell'editor di codice e controllare le intestazioni di colonna nella prima riga. Esaminare ognuna delle colonne. Comprendere i dati e decidere quali colonne sono **funzionalità** e qual è l'**etichetta**.

L'**etichetta** è l'identificatore della colonna che si sta tentando di stimare. Le **funzionalità** identificate vengono usate per stimare l'etichetta.

* **vendor_id:** l'ID della società di taxi è una funzionalità.
* **rate_code:** il tipo di tariffa del viaggio in taxi è una funzionalità.
* **passenger_count:** il numero di passeggeri è una funzionalità.
* **trip_time_in_secs:** il tempo impiegato per il viaggio. Non è possibile conoscere la durata del viaggio finché questo non viene completato. Questa colonna viene esclusa dal modello.
* **trip_distance:** la distanza del viaggio è una funzionalità.
* **payment_type:** il metodo di pagamento (contanti o carta di credito) è una funzionalità.
* **fare_amount:** la tariffa totale per il viaggio in taxi è l'etichetta.

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

È necessario creare tre variabili globali per contenere i percorsi dei file scaricati di recente e salvare il modello:

* `_datapath` contiene il percorso del set di dati usato per il training del modello.
* `_testdatapath` contiene il percorso del set di dati usato per valutare il modello.
* `_modelpath` contiene il percorso in cui è archiviato il modello sottoposto a training.

Aggiungere il codice seguente nella riga immediatamente sopra `Main` per specificare i file scaricati di recente:

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

Creare quindi le classi per i dati di input e le stime:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TaxiTrip.cs*. Selezionare quindi il pulsante **Aggiungi**.
1. Aggiungere al nuovo file le istruzioni `using` seguenti:

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `TaxiTrip` e `TaxiTripFarePrediction`, al file *TaxiTrip.cs*:

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` è la classe del set di dati di input e contiene le definizioni per ognuna delle colonne del set di dati. La classe `TaxiTripFarePrediction` viene usata per la stima dopo il training del modello. Ha un valore float singolo (`FareAmount`) e un attributo [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) `Score` applicato.

Tornare ora al file **Program.cs**. In `Main` sostituire `Console.WriteLine("Hello World!")` con il codice seguente:

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

Il metodo `Train` esegue il training del modello. Creare la funzione subito sotto `Main` con il codice seguente:

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a>Creare una pipeline di apprendimento

La pipeline di apprendimento carica tutti i dati e gli algoritmi necessari per il training del modello. Aggiungere nel metodo `Train()` il codice seguente:

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a>Caricare e trasformare i dati

Caricare quindi i dati nella pipeline. Fare riferimento all'elemento `_datapath` creato inizialmente e specificare il delimitatore del file CSV (,). Aggiungere il codice seguente nel metodo `Train()` sotto l'ultimo passaggio:

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

Si farà riferimento alle colonne senza i caratteri di sottolineatura nel codice creato. Copiare la colonna `FareAmount` in una nuova colonna denominata "Label" usando la funzione `ColumnCopier()`. Questa colonna è l'**etichetta**.

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

Eseguire alcune attività di **progettazione delle funzionalità** per trasformare i dati in modo da poterli usare in modo efficace per l'apprendimento automatico. Poiché l'algoritmo che esegue il training del modello richiede funzionalità **numeriche**, è necessario trasformare i dati relativi alle categorie (`VendorId`, `RateCode` e `PaymentType`) in numeri. La funzione `CategoricalOneHotVectorizer()` assegna una chiave numerica ai valori in ognuna di queste colonne. Trasformare i dati aggiungendo il codice seguente:

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

L'ultimo passaggio della preparazione dei dati combina tutte le **funzionalità** in un singolo vettore usando la funzione `ColumnConcatenator()`. Questo passaggio necessario consente all'algoritmo di elaborare facilmente le funzionalità. Aggiungere il codice seguente:

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

Si noti che la colonna `trip_time_in_secs` non è inclusa. È già stato determinato che non si tratta di una funzionalità di stima utile.

> [!NOTE]
> Questi passaggi devono essere aggiunti alla pipeline nell'ordine specificato in precedenza per la corretta esecuzione.

## <a name="choose-a-learning-algorithm"></a>Scegliere un algoritmo di apprendimento

Dopo aver aggiunto i dati alla pipeline e averli trasformati nel formato di input corretto, selezionare un **algoritmo di apprendimento**. L'algoritmo di apprendimento esegue il training del modello. È stata scelta un'**attività di regressione** per questo problema, pertanto è necessario aggiungere un algoritmo di apprendimento denominato `FastTreeRegressor()` alla pipeline che usa l'**incremento dei gradienti**.

L'incremento dei gradienti è una tecnica di apprendimento automatico per i problemi di regressione. Compila ogni albero di regressione tenendo conto dei singoli passaggi. Usa una funzione di perdita predefinita per misurare l'errore in ogni passaggio e correggerlo in quello successivo. Il risultato è un modello di stima che è effettivamente un insieme dei modelli di stima più deboli. Per altre informazioni sull'incremento dei gradienti, vedere [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression) (Regressione dell'albero delle decisioni con incremento).

Aggiungere il codice seguente nel metodo `Train()` dopo il codice di elaborazione dei dati aggiunto nel passaggio precedente:

```csharp
pipeline.Add(new FastTreeRegressor());
```

Tutti i passaggi precedenti sono stati aggiunti alla pipeline come singole istruzioni, ma C# presenta un'utile sintassi di inizializzazione della raccolta che rende più semplice creare e inizializzare la pipeline. Sostituire il codice aggiunto finora al metodo `Train()` con il codice seguente:

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a>Eseguire il training del modello

Il passaggio finale consiste nel training del modello. Fino a questo punto, non è stato eseguito alcun elemento nella pipeline. La funzione `pipeline.Train<T_Input, T_Output>()` accetta il tipo di classe predefinito `TaxiTrip` e restituisce un tipo `TaxiTripFarePrediction`. Aggiungere questo frammento di codice finale nella funzione `Train()`:

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

L'operazione è ora completata. È stato eseguito il training di un modello di apprendimento automatico in grado di prevedere le tariffe dei taxi a New York. Ora vediamo come comprendere il livello di accuratezza del modello e come usarlo.

## <a name="save-the-model"></a>Salvare il modello

Prima di procedere al passaggio successivo, salvare il modello in un file ZIP aggiungendo il codice seguente alla fine della funzione `Train()`:

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

L'aggiunta dell'istruzione `await` per la chiamata `model.WriteAsync()` significa che il metodo `Train()` deve essere cambiato in un metodo asincrono che restituisce un elemento `Task`. Modificare la firma di `Train` come illustrato nel codice seguente:

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

Con la modifica del tipo restituito del metodo `Train`, è necessario aggiungere un `await` al codice che chiama `Train` nel metodo `Main`, come illustrato nel codice seguente:

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

L'aggiunta di un `await` nel metodo `Main` implica che il metodo `Main` deve avere il modificatore `async` e restituire un elemento `Task`:

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

È inoltre necessario aggiungere la seguente istruzione using all'inizio del file:

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

Poiché il metodo `async Main` è una nuova funzionalità di C# 7.1 e la versione del linguaggio predefinita del progetto è C# 7.0, è necessario impostare la versione del linguaggio su C# 7.1 o versione successiva.
A tale scopo, fare clic con il pulsante destro del mouse sul nodo del progetto in **Esplora soluzioni** e scegliere **Proprietà**. Selezionare la scheda **Compilazione** e quindi il pulsante **Avanzate**. Nell'elenco a discesa selezionare **C# 7.1** (o versione successiva). Selezionare il pulsante **OK** .

## <a name="evaluate-the-model"></a>Valutare il modello

La valutazione è il processo di verifica del funzionamento del modello. È importante che il modello formuli stime corrette su dati che non sono stati usati quando è stato eseguito il training. Un modo per eseguire questa operazione è suddividere i dati in set di dati di training e di test, com'è stato descritto in questa esercitazione. Ora che è stato eseguito il training del modello sui dati di training, è possibile verificarne le prestazioni sui dati di test.

Tornare alla funzione `Main` e aggiungere il codice seguente dopo la chiamata al metodo `Train()`:

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

La funzione `Evaluate()` valuta il modello. Creare la funzione sotto `Train()`. Aggiungere il codice seguente:

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

Caricare i dati di test usando la funzione `TextLoader()`. Aggiungere nel metodo `Evaluate()` il codice seguente:

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

Aggiungere il codice seguente per valutare il modello e produrre le relative metriche:

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

RMS è una metrica per la valutazione dei problemi di regressione. Più è basso il valore, migliore è il modello. Aggiungere il codice seguente nella funzione `Evaluate()` per ottenere la metrica RMS per il modello.

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

RSquared è un'altra metrica per la valutazione dei problemi di regressione. RSquared ha un valore compreso tra 0 e 1. Più il valore è vicino a 1, migliore è il modello. Aggiungere il codice seguente nella funzione `Evaluate()` per ottenere il valore RSquared per il modello.

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a>Usare il modello per le stime

È quindi possibile creare una classe per gestire scenari di test che è possibile usare per verificare il corretto funzionamento del modello:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuovo elemento**.
1. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *TestTrips.cs*. Selezionare quindi il pulsante **Aggiungi**.
1. Modificare la classe in modo da renderla statica, come nell'esempio seguente:

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

In questa esercitazione viene usato un solo viaggio di test all'interno di questa classe. Successivamente, è possibile aggiungere altri scenari per sperimentare con questo esempio. Aggiungere il codice seguente nella classe `TestTrips`:

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

La tariffa effettiva di questo viaggio è 29,5, ma usare 0 come segnaposto. L'algoritmo di apprendimento automatico stimerà la tariffa.

Aggiungere il codice seguente nella funzione `Main`. Esegue il test del modello usando i dati di `TestTrip`:

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

Eseguire il programma per visualizzare la tariffa del taxi stimata per il test case.

La procedura è stata completata. È stato creato un modello di apprendimento automatico per la stima delle tariffe dei taxi, ne è stata valutata l'accuratezza ed è stato eseguito il testing. È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction).

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

Visitare il repository GitHub per ottenere altre informazioni ed esempi.
> [!div class="nextstepaction"]
> [Repository GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/)

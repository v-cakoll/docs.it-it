---
title: 'Esercitazione: creare un Movie Recommender-factoring della matrice'
description: In questa esercitazione viene illustrato come creare un sistema di raccomandazione di film con ML.NET in un'applicazione console .NET Core. I passaggi usano C# e Visual Studio 2019.
author: briacht
ms.date: 06/30/2020
ms.custom: mvc, title-hack-0516
ms.topic: tutorial
ms.openlocfilehash: 39c4aeef0b02a6bf47d78e6bf53cd42b4f592946
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86282099"
---
# <a name="tutorial-build-a-movie-recommender-using-matrix-factorization-with-mlnet"></a>Esercitazione: creare un Movie Recommender usando la factorzzazione della matrice con ML.NET

In questa esercitazione viene illustrato come creare un sistema di raccomandazione di film con ML.NET in un'applicazione console .NET Core. I passaggi usano C# e Visual Studio 2019.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> * Selezionare un algoritmo di Machine Learning
> * Preparare e caricare i dati
> * Creare un modello ed eseguirne il training
> * Valutare un modello
> * Distribuire e usare un modello

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).

## <a name="machine-learning-workflow"></a>Flusso di lavoro di apprendimento automatico

Per completare questa attività, così come qualsiasi altra attività ML.NET, si useranno i passaggi seguenti:

1. [Caricare i dati](#load-your-data)
2. [Creare il modello ed eseguirne il training](#build-and-train-your-model)
3. [Valutare il modello](#evaluate-your-model)
4. [Usare il modello](#use-your-model)

## <a name="prerequisites"></a>Prerequisiti

* [Visual studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o versione successiva o visual studio 2017 versione 15,6 o successiva con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.

## <a name="select-the-appropriate-machine-learning-task"></a>Selezionare l'attività di apprendimento automatico appropriata

I problemi relativi alla raccomandazione, ad esempio la raccomandazione di un elenco di film o di un elenco di prodotti correlati, possono essere affrontati in diversi modi, ma in questo caso si effettuerà la previsione della valutazione (da 1 a 5) che un utente assegnerà a un determinato film e si raccomanderà il film se è stato valutato al di sopra di una soglia definita (tanto più elevata è la valutazione, quanto più elevata sarà la probabilità che a un utente piaccia un determinato film).

## <a name="create-a-console-application"></a>Creare un'applicazione console

### <a name="create-a-project"></a>Creare un progetto

1. Aprire Visual Studio 2017. Scegliere **file**  >  **nuovo**  >  **progetto** dalla barra dei menu. Nella finestra di dialogo **nuovo progetto** selezionare il nodo **Visual C#** seguito dal nodo **.NET Core** . Selezionare quindi il modello di progetto **App Console (.NET Core)**. Nella casella di testo **Nome** digitare "MovieRecommender" e quindi selezionare il pulsante **OK**.

2. Creare una directory denominata *Data* nel progetto per archiviare il set di dati:

    In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **Nuova cartella**. Digitare "Data" e premere INVIO.

3. Installare i pacchetti NuGet **Microsoft.ML** e **Microsoft.ML.Recommender**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto e scegliere **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come Origine del pacchetto, selezionare la scheda **Sfoglia**, trovare **Microsoft.ML**, selezionare il pacchetto nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati. Ripetere questi passaggi per **Microsoft.ML.Recommender**.

4. Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

    [!code-csharp[UsingStatements](./snippets/movie-recommendation/csharp/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a>Scarica i tuoi dati

1. Scaricare i due set di dati e salvarli nella cartella *Data* precedentemente creata:

   * Fare clic con il pulsante destro del mouse su [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) e selezionare "Salva collegamento con nome..." o "Salva oggetto con nome..."
   * Fare clic con il pulsante destro del mouse su [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) e selezionare "Salva collegamento con nome..." o "Salva oggetto con nome..."

     Assicurarsi di salvare i file \*.csv nella cartella *Data* oppure, dopo averli salvati in un altro percorso, spostare i file \*.csv nella cartella *Data*.

2. In Esplora soluzioni fare clic con il pulsante destro del mouse su ognuno dei file \*con estensione csv e selezionare **Proprietà**. In **Avanzate**impostare il valore di **copia nella directory di output** su **copia se più recente**.

   ![GIF di un utente che seleziona copia se più recente in Visual Studio.](./media/movie-recommendation/copy-to-output-if-newer.gif)

## <a name="load-your-data"></a>Caricare i dati

Il primo passaggio del processo ML.NET è la preparazione e il caricamento dei dati di training e test del modello.

I dati delle valutazioni della raccomandazione vengono divisi in set di dati `Train` e `Test`. I dati `Train` vengono usati per il fit del modello. I dati `Test` vengono usati per effettuare previsioni con il modello sottoposto a training e valutarne le prestazioni. Per i dati `Train` e `Test` in genere si applica una suddivisione 80/20.

Di seguito è un'anteprima dei dati di \*file con estensione csv:

![Screenshot dell'anteprima del set di dati CVS.](./media/movie-recommendation/csv-file-dataset-preview.png)

Nel \*file con estensione csv, sono disponibili quattro colonne:

* `userId`
* `movieId`
* `rating`
* `timestamp`

Nel Machine Learning le colonne usate per effettuare una previsione sono denominate [Features](../resources/glossary.md#feature) (Caratteristiche) e la colonna con la previsione restituita è denominata [Label](../resources/glossary.md#label) (Etichetta).

In questo caso si vuole prevedere le valutazioni di film, quindi la colonna della valutazione è la colonna `Label`. Le altre tre colonne, `userId`, `movieId` e `timestamp`, sono tutte `Features` usate per la previsione di `Label`.

| Funzionalità      | Label         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

È possibile decidere quali `Features` vengono usate per la previsione di `Label`. È anche possibile usare metodi come la [funzionalità di permutazione di importanza](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md) per facilitare la selezione del migliore `Features` .

In questo caso è consigliabile eliminare la colonna `timestamp` come `Feature` perché il timestamp in realtà non influisce sulla valutazione di un determinato film da parte di un utente e quindi non contribuisce a effettuare una previsione più accurata:

| Funzionalità      | Label         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

È quindi necessario definire la struttura dei dati per la classe di input.

Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Aggiungi > Nuovo elemento**.

2. Nella **finestra di dialogo Aggiungi nuovo elemento** selezionare **Classe** e modificare il valore del campo **Nome** in *MovieRatingData.cs*. Selezionare quindi il pulsante **Aggiungi**.

Il file *MovieRatingData.cs* verrà aperto nell'editor di codice. Aggiungere l'istruzione `using` seguente all'inizio di *MovieRatingData.cs*:

```csharp
using Microsoft.ML.Data;
```

Creare una classe denominata `MovieRating` rimuovendo la definizione di classe esistente e aggiungendo il codice seguente in *MovieRatingData.cs*:

[!code-csharp[MovieRatingClass](./snippets/movie-recommendation/csharp/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

`MovieRating` specifica una classe di dati di input. L'attributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) specifica quali colonne (in base all'indice delle colonne) nel set di dati è necessario caricare. Le colonne `userId` e `movieId` sono le `Features`, ovvero gli input che si forniranno al modello per la previsione di `Label`, e la colonna della valutazione è l'oggetto `Label` di cui si otterrà la previsione, ovvero l'output del modello.

Creare un'altra classe, `MovieRatingPrediction`, per rappresentare i risultati previsti aggiungendo il codice seguente dopo la classe `MovieRating` in *MovieRatingData.cs*:

[!code-csharp[PredictionClass](./snippets/movie-recommendation/csharp/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

In *Program.cs* sostituire `Console.WriteLine("Hello World!")` con il codice seguente all'interno di `Main()`:

[!code-csharp[MLContext](./snippets/movie-recommendation/csharp/Program.cs#MLContext "Add MLContext")]

La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

Dopo `Main()`, creare un metodo denominato `LoadData()`:

```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{

}
```

> [!NOTE]
> Questo metodo restituisce un errore finché non si aggiungerà un'istruzione return nei passaggi seguenti.

Inizializzare le variabili di percorso dei dati, caricare i dati dai file \*.csv e restituire i dati `Train` e `Test` come oggetti `IDataView` aggiungendo il codice seguente come riga successiva in `LoadData()`:

[!code-csharp[LoadData](./snippets/movie-recommendation/csharp/Program.cs#LoadData "Load data from data paths")]

I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView). `IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo). È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`.

[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema dei dati e legge il contenuto del file. Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`. In questo caso viene specificato il percorso dei file `Test` e `Train` e vengono indicati sia l'intestazione del file di testo, in modo che il metodo possa usare correttamente i nomi di colonna, sia la virgola come separatore dei dati di tipo carattere (il separatore predefinito è una tabulazione).

Aggiungere il codice seguente nel metodo `Main()` per chiamare il metodo `LoadData()` e restituire i dati `Train` e `Test`:

[!code-csharp[LoadDataMain](./snippets/movie-recommendation/csharp/Program.cs#LoadDataMain "Add LoadData method to Main")]

## <a name="build-and-train-your-model"></a>Creare il modello ed eseguirne il training

Esistono tre concetti principali in ML.NET: [dati](../resources/glossary.md#data), [trasformatori](../resources/glossary.md#transformer)e [estimatori](../resources/glossary.md#estimator).

Gli algoritmi di training del Machine Learning necessitano di dati in un determinato formato. I `Transformers` sono usati per trasformare i dati tabulari in un formato compatibile.

![Diagramma del flusso di datatransformer.](./media/movie-recommendation/data-transformer-transformed.png)

In ML.NET è possibile creare `Transformers` tramite la creazione di `Estimators`. Gli `Estimators` acquisiscono i dati e restituiscono `Transformers`.

![Diagramma del flusso di calcolo di Estimator.](./media/movie-recommendation/data-estimator-transformer.png)

L'algoritmo di training della raccomandazione che si userà per il training del modello è un esempio di `Estimator`.

Creare un `Estimator` seguendo questi passaggi:

Creare il metodo `BuildAndTrainModel()` subito dopo il metodo `LoadData()`, usando il codice seguente:

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{

}
```

> [!NOTE]
> Questo metodo restituisce un errore finché non si aggiungerà un'istruzione return nei passaggi seguenti.

Definire le trasformazioni dei dati aggiungendo il codice seguente a `BuildAndTrainModel()`:

[!code-csharp[DataTransformations](./snippets/movie-recommendation/csharp/Program.cs#DataTransformations "Define data transformations")]

Poiché `userId` e `movieId` rappresentano utenti e titoli di film, non valori reali, viene usato il metodo [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) per trasformare ogni `userId` e ogni `movieId` in una colonna chiave di tipo numerico `Feature` (un formato accettato dagli algoritmi di raccomandazione) e aggiungerle come nuove colonne del set di dati:

| userId | movieId | Label | userIdEncoded | movieIdEncoded |
| ------------- |:-------------:| -----:|-----:|-----:|
| 1 | 1 | 4 | userKey1 | movieKey1 |
| 1 | 3 | 4 | userKey1 | movieKey2 |
| 1 | 6 | 4 | userKey1 | movieKey3 |

Scegliere l'algoritmo di Machine Learning e aggiungerlo alle definizioni di trasformazione dei dati aggiungendo il codice seguente come riga successiva in `BuildAndTrainModel()`:

[!code-csharp[AddAlgorithm](./snippets/movie-recommendation/csharp/Program.cs#AddAlgorithm "Add the training algorithm with options")]

[MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) è l'algoritmo di training della raccomandazione.  La [fattorizzazione di matrice](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) è un approccio comune alla raccomandazione quando si hanno a disposizione dati su come gli utenti hanno valutato i prodotti in passato, come nel caso dei set di dati usati in questa esercitazione. Per le situazioni in cui sono disponibili dati diversi, esistono altri algoritmi di raccomandazione. Per altre informazioni, vedere la sezione [Altri algoritmi di raccomandazione](#other-recommendation-algorithms) più avanti in questo articolo.

In questo caso, l'algoritmo `Matrix Factorization` usa un metodo denominato "filtraggio collaborativo" il quale presuppone che se l'utente 1 ha la stessa opinione dell'utente 2 relativamente a un determinato problema, è probabile che l'utente 1 sia d'accordo con l'utente 2 riguardo a un altro problema.

Se ad esempio l'utente 1 e l'utente 2 valutano i film in modo simile, è probabile che all'utente 2 piaccia un film che l'utente 1 ha visto e a cui ha assegnato una valutazione elevata:

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| Utente 1 | Ha visto e apprezzato il film | Ha visto e apprezzato il film | Ha visto e apprezzato il film |
| Utente 2 | Ha visto e apprezzato il film | Ha visto e apprezzato il film | Non l'ha visto - RACCOMANDARE il film |

Il trainer `Matrix Factorization` include diverse [opzioni](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options). Per altre informazioni, vedere la sezione [Iperparametri dell'algoritmo](#algorithm-hyperparameters) più avanti in questo articolo.

Eseguire il fit del modello ai dati `Train` e restituire il modello sottoposto a training aggiungendo il codice seguente come riga successiva nel metodo `BuildAndTrainModel()`:

[!code-csharp[FitModel](./snippets/movie-recommendation/csharp/Program.cs#FitModel "Call the Fit method and return back the trained model")]

Il metodo [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) esegue il training del modello con il set di dati di training specificato. Tecnicamente il metodo esegue le definizioni `Estimator` trasformando i dati e applicando il training, quindi restituisce il modello sottoposto a training, ovvero un `Transformer`.

Aggiungere il codice seguente come riga successiva nel metodo `Main()` per chiamare il metodo `BuildAndTrainModel()` e restituire il modello sottoposto a training:

[!code-csharp[BuildTrainModelMain](./snippets/movie-recommendation/csharp/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a>Valutare il modello

Dopo aver eseguito il training del modello, usare i dati di test per valutare le prestazioni del modello.

Creare il metodo `EvaluateModel()` subito dopo il metodo `BuildAndTrainModel()`, usando il codice seguente:

```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{

}
```

Trasformare i dati `Test` aggiungendo il codice seguente a `EvaluateModel()`:

[!code-csharp[Transform](./snippets/movie-recommendation/csharp/Program.cs#Transform "Transform the test data")]

Il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) effettua previsioni per più righe di input specificate di un set di dati di test.

Valutare il modello aggiungendo il codice seguente come riga successiva nel metodo `EvaluateModel()`:

[!code-csharp[Evaluate](./snippets/movie-recommendation/csharp/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

Dopo aver impostato la previsione, il metodo [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) valuta il modello confrontando i valori stimati con gli oggetti `Labels` effettivi presenti nel set di dati di test e restituisce le metriche relative alle prestazioni del modello.

Stampare le metriche di valutazione nella console aggiungendo il codice seguente come riga successiva nel metodo `EvaluateModel()`:

[!code-csharp[PrintMetrics](./snippets/movie-recommendation/csharp/Program.cs#PrintMetrics "Print the evaluation metrics")]

Aggiungere il codice seguente come riga successiva nel metodo `Main()` per chiamare il metodo `EvaluateModel()`:

[!code-csharp[EvaluateModelMain](./snippets/movie-recommendation/csharp/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

A questo punto, l'output dovrebbe avere un aspetto simile al testo seguente:

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

Questo output presenta 20 iterazioni. In ogni iterazione la misura di errore diminuisce ed è sempre più prossima allo 0.

La metrica `root of mean squared error` (RMS o RMSE) viene usata per misurare le differenze tra i valori stimati da un modello e quelli osservati in set di dati di test. Tecnicamente è la radice quadrata della media dei quadrati degli errori. Più basso è il valore, migliore è il modello.

`R Squared` indica il livello di adattamento dei dati a un modello. È compreso tra 0 e 1. Un valore pari a 0 indica che i dati sono casuali o non possono essere adattati al modello. Un valore pari a 1 indica che il modello corrisponde esattamente ai dati. Il punteggio `R Squared` deve essere il più vicino possibile a 1.

La creazione di modelli efficaci è un processo iterativo. Questo modello ha inizialmente una qualità inferiore, perché l'esercitazione usa set di dati di dimensioni contenute per consentire il training rapido del modello. Se non si è soddisfatti della qualità del modello, è possibile provare a migliorarla fornendo set di dati di training più grandi o scegliendo algoritmi di training diversi con iperparametri diversi per ogni algoritmo. Per altre informazioni, vedere la sezione [Migliorare il modello](#improve-your-model) più avanti.

## <a name="use-your-model"></a>Usare il modello

Ora è possibile usare il modello sottoposto a training per effettuare previsioni sui nuovi dati.

Creare il metodo `UseModelForSinglePrediction()` subito dopo il metodo `EvaluateModel()`, usando il codice seguente:

```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{

}
```

Usare `PredictionEngine` per prevedere la valutazione aggiungendo il codice seguente a `UseModelForSinglePrediction()`:

[!code-csharp[PredictionEngine](./snippets/movie-recommendation/csharp/Program.cs#PredictionEngine "Create Prediction Engine")]

[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) è un'API di praticità, che consente di eseguire una stima su una singola istanza di dati. [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)non è thread-safe. È accettabile usare in ambienti a thread singolo o prototipi. Per migliorare le prestazioni e thread safety negli ambienti di produzione, utilizzare il `PredictionEnginePool` servizio, che consente di creare un oggetto [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) di [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) oggetti da utilizzare nell'applicazione. Vedere questa guida su come [usare `PredictionEnginePool` in un'API Web di ASP.NET Core](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).

> [!NOTE]
> L'estensione del servizio `PredictionEnginePool` è attualmente in anteprima.

Creare un'istanza di `MovieRating` denominata `testInput` e passarla al motore di previsione aggiungendo il codice seguente come righe successive nel metodo `UseModelForSinglePrediction()`:

[!code-csharp[MakeSinglePrediction](./snippets/movie-recommendation/csharp/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

La funzione [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) effettua una previsione su una singola colonna di dati.

È quindi possibile usare `Score`, o la valutazione prevista, per determinare se si vuole raccomandare il film con movieId 10 all'utente 6. Tanto più elevato è il valore di `Score`, quanto più elevata sarà la probabilità che a un utente piaccia un determinato film. In questo caso, si raccomanderanno film con una valutazione prevista di > 3.5.

Per stampare i risultati, aggiungere il codice seguente come righe successive nel metodo `UseModelForSinglePrediction()`:

[!code-csharp[PrintResults](./snippets/movie-recommendation/csharp/Program.cs#PrintResults "Print the recommendation prediction results")]

Aggiungere il codice seguente come riga successiva nel metodo `Main()` per chiamare il metodo `UseModelForSinglePrediction()`:

[!code-csharp[UseModelMain](./snippets/movie-recommendation/csharp/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

L'output di questo metodo dovrebbe avere un aspetto simile al testo seguente:

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a>Salvare il modello

Per usare il modello per effettuare previsioni nelle applicazioni per l'utente finale, è prima necessario salvare il modello.

Creare il metodo `SaveModel()` subito dopo il metodo `UseModelForSinglePrediction()`, usando il codice seguente:

```csharp
public static void SaveModel(MLContext mlContext, DataViewSchema trainingDataViewSchema, ITransformer model)
{

}
```

Salvare il modello sottoposto a training aggiungendo il codice seguente nel metodo `SaveModel()`:

[!code-csharp[SaveModel](./snippets/movie-recommendation/csharp/Program.cs#SaveModel "Save the model to a zip file")]

Questo metodo salva il modello sottoposto a training in un file con estensione zip (nella cartella "Data") che potrà essere successivamente usato in altre applicazioni .NET per effettuare previsioni.

Aggiungere il codice seguente come riga successiva nel metodo `Main()` per chiamare il metodo `SaveModel()`:

[!code-csharp[SaveModelMain](./snippets/movie-recommendation/csharp/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a>Usare il modello salvato

Dopo aver salvato il modello sottoposto a training, è possibile utilizzare il modello in ambienti diversi. Per informazioni su come rendere operativo un modello di apprendimento automatico con training nelle app, vedere [salvare e caricare modelli](../how-to-guides/save-load-machine-learning-models-ml-net.md) sottoposti a training.

## <a name="results"></a>Risultati

Dopo aver completato la procedura descritta sopra, eseguire l'app console (CTRL + F5). I risultati della previsione singola indicata in precedenza dovrebbero essere simili a quanto riportato di seguito. È possibile che vengano visualizzati avvisi o messaggi di elaborazione che tuttavia, per chiarezza, sono stati rimossi dai risultati riportati di seguito.

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

Congratulazioni! È stato creato un modello di Machine Learning per raccomandare film. È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation).

## <a name="improve-your-model"></a>Migliorare il modello

È possibile migliorare le prestazioni del modello in diversi modi per ottenere previsioni più accurate.

### <a name="data"></a>Data

L'aggiunta di altri dati di training con sufficienti esempi per ogni utente e ID film contribuisce a migliorare la qualità del modello di raccomandazione.

La [convalida incrociata](../how-to-guides/train-machine-learning-model-cross-validation-ml-net.md) è una tecnica per la valutazione dei modelli che divide in modo casuale i dati in subset, anziché estrarre i dati di test dal set di dati come in questa esercitazione, e acquisisce alcuni gruppi come dati di training e altri come dati di test. In termini di qualità del modello, questo metodo offre prestazioni migliori rispetto alla divisione train-test.

### <a name="features"></a>Funzionalità

In questa esercitazione vengono usate solo le tre `Features` (`user id`, `movie id` e `rating`) offerte dal set di dati.

È un buon inizio, ma nella realtà è utile aggiungere altri attributi o `Features`, ad esempio età, sesso, posizione geografica e così via, se sono inclusi nel set di dati. L'aggiunta di `Features` più rilevanti può contribuire a migliorare le prestazioni del modello di raccomandazione.

Se non si è certi di quale `Features` sia il più pertinente per l'attività di Machine Learning, è anche possibile usare la funzionalità FCC (feature Contribution calculation) e l' [importanza della funzionalità di permutazione](../how-to-guides/explain-machine-learning-model-permutation-feature-importance-ml-net.md), che ml.NET fornisce per individuare i più influenti `Features` .

### <a name="algorithm-hyperparameters"></a>Iperparametri dell'algoritmo

Anche se gli algoritmi di training predefiniti di ML.NET sono di ottima qualità, è possibile ottimizzare ulteriormente le prestazioni modificando gli [iperparametri](../resources/glossary.md#hyperparameter) dell'algoritmo.

Per `Matrix Factorization`, è possibile sperimentare con iperparametri quali [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) e [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) per vedere se vengono restituiti risultati migliori.

Ad esempio, in questa esercitazione le opzioni di algoritmo sono:

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded",
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a>Altri algoritmi per la raccomandazione

L'algoritmo di fattorizzazione di matrice con filtraggio collaborativo è solo uno degli approcci per l'esecuzione di raccomandazioni di film. In molti casi, è possibile che i dati delle valutazioni non siano disponibili e che sia disponibile solo la cronologia del film relativa all'utente. In altri casi, si potrebbe avere di più dei soli dati di valutazione dell'utente.

| Algoritmo       | Scenario           | Esempio  |
| ------------- |:-------------:| -----:|
| One Class Matrix Factorization | Usare questo algoritmo quando sono disponibili solo userId e movieId. Questo stile di raccomandazione si basa sullo scenario di acquisto congiunto o di prodotti acquistati di frequente insieme e consiglierà quindi al cliente un set di prodotti in base alla propria cronologia di acquisto. | [>provare](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| Field Aware Factorization Machines | Usare questo algoritmo per creare raccomandazioni quando sono disponibili altre caratteristiche oltre a userId, productId e rating, ad esempio la descrizione del prodotto o il prezzo del prodotto. Questo metodo usa anche un approccio di filtraggio collaborativo. | [>provare](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a>Scenario con nuovi utenti

Un problema comune nel filtraggio collaborativo è quello relativo ai nuovi utenti per i quali non sono disponibili dati precedenti da cui trarre inferenze. Questo problema viene spesso risolto chiedendo ai nuovi utenti di creare un profilo e, ad esempio, valutare i film che hanno visto in passato. Anche se questo metodo introduce un compito in più per l'utente, esso consente di ottenere alcuni dati di partenza per i nuovi utenti senza una cronologia di valutazioni.

## <a name="resources"></a>Risorse

I dati usati in questa esercitazione sono derivati dal [set di dati MovieLens](http://files.grouplens.org/datasets/movielens/).

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono state illustrate le procedure per:

> [!div class="checklist"]
>
> * Selezionare un algoritmo di Machine Learning
> * Preparare e caricare i dati
> * Creare un modello ed eseguirne il training
> * Valutare un modello
> * Distribuire e usare un modello

Passare all'esercitazione successiva per altre informazioni
> [!div class="nextstepaction"]
> [Analisi del sentiment](sentiment-analysis.md)

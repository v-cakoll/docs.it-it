---
title: Che cos'è ML.NET e come funziona?
description: ML.NET offre la possibilità di aggiungere funzionalità di Machine Learning alle applicazioni .NET, in scenari online o offline. Con questa funzionalità è possibile eseguire stime automatiche usando i dati disponibili per l'applicazione senza che sia necessario connettersi a una rete per usare ML.NET. Questo articolo illustra le nozioni fondamentali dell'apprendimento automatico in ML.NET.
ms.date: 11/5/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: 0929005e02ad9b43636213735f8c7232aa6d4f42
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607771"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a>Che cos'è ML.NET e come funziona?

ML.NET offre la possibilità di aggiungere funzionalità di Machine Learning alle applicazioni .NET, in scenari online o offline. Con questa funzionalità è possibile eseguire stime automatiche usando i dati disponibili per l'applicazione. Le applicazioni di apprendimento automatico usano modelli nei dati per fare previsioni piuttosto che dover essere programmate in modo esplicito.

Centrale per ML.NET è un **modello**di apprendimento automatico. Il modello specifica i passaggi necessari per trasformare i dati di input in una stima. Con ML.NET, è possibile eseguire il training di un modello personalizzato specificando un algoritmo oppure importare modelli TensorFlow e ONNX con training preliminare.

Dopo aver a disposizione un modello, è possibile aggiungerlo all'applicazione per eseguire le stime.

ML.NET vengono eseguiti in Windows, Linux e macOS usando .NET Core o Windows con .NET Framework. 64 bit è supportato su tutte le piattaforme. La funzionalità relativa a 32 bit è supportata in Windows, ad eccezione di TensorFlow, LightGBM e ONNX.

Esempi del tipo di stime che è possibile eseguire con ML.NET:

|||
|-|-|
|Classificazione/categorizzazione|Suddivisione automatica dei commenti e dei suggerimenti degli utenti in categorie positive e negative|
|Regressione/stima di valori continui|Previsione del prezzo delle case in base alle dimensioni e alla posizione|
|Anomaly Detection|Rilevamento di transazioni bancarie fraudolente |
|Consigli|Suggerimento di prodotti che gli acquirenti online potrebbero voler acquistare, in base agli acquisti precedenti|
|Serie temporali/dati sequenziali|Prevedere le vendite meteo/prodotto|
|Classificazione di immagini|Categorizzare le patologie nelle immagini mediche|

## <a name="hello-mlnet-world"></a>Hello ML.NET World

Il codice del frammento seguente illustra l'applicazione più semplice di ML.NET. Questo esempio crea un modello di regressione lineare per stimare i prezzi di unità immobiliari usando i dati delle dimensioni e del prezzo dell'unità immobiliare.

 ```csharp
    using System;
    using Microsoft.ML;
    using Microsoft.ML.Data;

    class Program
    {
        public class HouseData
        {
            public float Size { get; set; }
            public float Price { get; set; }
        }

        public class Prediction
        {
            [ColumnName("Score")]
            public float Price { get; set; }
        }

        static void Main(string[] args)
        {
            MLContext mlContext = new MLContext();

            // 1. Import or create training data
            HouseData[] houseData = {
                new HouseData() { Size = 1.1F, Price = 1.2F },
                new HouseData() { Size = 1.9F, Price = 2.3F },
                new HouseData() { Size = 2.8F, Price = 3.0F },
                new HouseData() { Size = 3.4F, Price = 3.7F } };
            IDataView trainingData = mlContext.Data.LoadFromEnumerable(houseData);

            // 2. Specify data preparation and model training pipeline
            var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
                .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));

            // 3. Train model
            var model = pipeline.Fit(trainingData);

            // 4. Make a prediction
            var size = new HouseData() { Size = 2.5F };
            var price = mlContext.Model.CreatePredictionEngine<HouseData, Prediction>(model).Predict(size);

            Console.WriteLine($"Predicted price for size: {size.Size*1000} sq ft= {price.Price*100:C}k");

            // Predicted price for size: 2500 sq ft= $261.98k
        }
    }
```

## <a name="code-workflow"></a>Flusso di lavoro del codice

Il diagramma seguente rappresenta la struttura del codice dell'applicazione e il processo iterativo di sviluppo del modello:

- Raccogliere e caricare i dati di training in un oggetto **IDataView**
- Specificare una pipeline di operazioni per estrarre caratteristiche e applicare un algoritmo di apprendimento automatico
- Eseguire il training di un modello chiamando **Fit()** sulla pipeline
- Valutare il modello ed eseguire l'iterazione per migliorare
- Salvare il modello in formato binario, per l'uso in un'applicazione
- Caricare il modello in un oggetto **ITransformer**
- Eseguire stime chiamando **CreatePredictionEngine.Predict()**

![Flusso di sviluppo dell'applicazione ML.NET che include componenti per la generazione dei dati, sviluppo di pipeline, training del modello, valutazione del modello e uso del modello](./media/mldotnet-annotated-workflow.png)

Ora si approfondiranno questi concetti.

## <a name="machine-learning-model"></a>Modello di Machine Learning

Un modello ML.NET è un oggetto che contiene le trasformazioni da eseguire sui dati di input per ottenere l'output previsto.

### <a name="basic"></a>Basic

Il modello più semplice è la regressione lineare bidimensionale, in cui una quantità continua è proporzionale a un'altra, come illustrato nell'esempio di prezzi di unità immobiliari precedente.

![Modello di regressione lineare con parametri di distorsione e peso](./media/linear-regression-model.svg)

Il modello è semplicemente: $Price = b + Size * w$. I parametri $b$ e $w$ vengono stimati adattando una riga a un set di coppie (size, price). I dati usati per trovare i parametri del modello sono detti **dati di training**. Gli input di un modello di Machine Learning vengono chiamati **caratteristiche**. In questo esempio $Size$ è l'unica caratteristica. I valori di base usati per il training di un modello di Machine Learning sono detti **etichette**. In questo caso le etichette sono i valori di $Price$ nel training set.

### <a name="more-complex"></a>Più complesso

Un modello più complesso classifica le transazioni finanziarie in categorie usando la descrizione di testo della transazione.

Ogni descrizione di transazione è suddivisa in un set di caratteristiche, tramite la rimozione delle parole e dei caratteri ridondanti e il conteggio delle combinazioni di parole e caratteri. Il set di caratteristiche è usato per il training di un modello lineare sulla base del set di categorie nei dati di training. Più una nuova descrizione è simile a quelle del training set, maggiore è la probabilità che sia assegnata alla stessa categoria.

![Modello di classificazione del testo](./media/text-classification-model.svg)

Sia il modello di tariffazione delle unità immobiliari sia il modello di classificazione del testo sono modelli **lineari**. A seconda della natura dei dati e del problema da risolvere, è anche possibile usare modelli **albero delle decisioni**, modelli **additivi generalizzati (GAM)** e altri ancora. Per altre informazioni sui modelli, vedere [Attività](./resources/tasks.md).

## <a name="data-preparation"></a>Preparazione dei dati

Nella maggior parte dei casi i dati disponibili non sono pronti per l'uso nel training di un modello di Machine Learning. I dati non elaborati devono essere preparati, o pre-elaborati, prima di poter essere utilizzati per trovare i parametri del modello. Può essere necessaria la conversione dei dati da valori stringa a una rappresentazione numerica. I dati di input potrebbero contenere informazioni ridondanti. Potrebbe essere necessario ridurre o espandere le dimensioni dei dati di input. I dati potrebbero richiedere la normalizzazione o la scalatura.

Le [esercitazioni di ML.NET](./tutorials/index.md) illustrano diverse pipeline di elaborazione per dati di testo, immagini, serie temporali e dati numerici usati per attività di apprendimento automatico specifiche.

[Come preparare i dati](./how-to-guides/prepare-data-ml-net.md) mostra come applicare la preparazione dei dati in modo più generale.

Un'appendice con tutte le [trasformazioni](./resources/transforms.md) è disponibile nella sezione delle risorse.

## <a name="model-evaluation"></a>Valutazione del modello.

Dopo aver eseguito il training del modello, come si sa se le stime future verranno eseguite correttamente? Con ML.NET è possibile valutare il modello rispetto a nuovi dati di test.

Ogni tipo di attività di apprendimento automatico dispone di metriche che vengono usate per valutare l'accuratezza e la precisione del modello rispetto al set di dati di test.

Per l'esempio di definizione dei prezzi di unità immobiliari è stata usata l'attività **Regressione**. Per valutare il modello, aggiungere il codice seguente all'esempio originale.

```csharp
        HouseData[] testHouseData =
        {
            new HouseData() { Size = 1.1F, Price = 0.98F },
            new HouseData() { Size = 1.9F, Price = 2.1F },
            new HouseData() { Size = 2.8F, Price = 2.9F },
            new HouseData() { Size = 3.4F, Price = 3.6F }
        };

        var testHouseDataView = mlContext.Data.LoadFromEnumerable(testHouseData);
        var testPriceDataView = model.Transform(testHouseDataView);

        var metrics = mlContext.Regression.Evaluate(testPriceDataView, labelColumnName: "Price");

        Console.WriteLine($"R^2: {metrics.RSquared:0.##}");
        Console.WriteLine($"RMS error: {metrics.RootMeanSquaredError:0.##}");

        // R^2: 0.96
        // RMS error: 0.19
```

Le metriche di valutazione indicano che la quantità di errori è ridotta e che la correlazione tra l'output previsto e l'output del test è elevata. Questa elaborazione non ha presentato problemi. Negli esempi reali, per ottenere metriche del modello valide sono necessarie più operazioni di ottimizzazione.

## <a name="mlnet-architecture"></a>Architettura ML.NET

In questa sezione si prendono in considerazione i modelli architettonici di ML.NET. Per gli sviluppatori .NET esperti alcuni di questi modelli risulteranno familiari e altri meno familiari. Si procede per gradi.

Un'applicazione ML.NET inizia con un oggetto <xref:Microsoft.ML.MLContext>. Questo oggetto singleton contiene **cataloghi**. Un catalogo è una factory per il caricamento e salvataggio di dati, le trasformazioni, i formatori e i componenti di gestione del modello. Ogni oggetto catalogo dispone di metodi per creare diversi tipi di componenti:

|||||
|-|-|-|-|
|Caricamento e salvataggio dei dati||<xref:Microsoft.ML.DataOperationsCatalog>||
|Preparazione dei dati||<xref:Microsoft.ML.TransformsCatalog>||
|Algoritmi di training|Classificazione binaria|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||Classificazione multiclasse|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||Rilevamento anomalie|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||Clustering|<xref:Microsoft.ML.ClusteringCatalog>||
||Previsione|<xref:Microsoft.ML.ForecastingCatalog>||
||Rango|<xref:Microsoft.ML.RankingCatalog>||
||Regressione|<xref:Microsoft.ML.RegressionCatalog>||
||Recommendation|<xref:Microsoft.ML.RecommendationCatalog>|Aggiungere il pacchetto NuGet `Microsoft.ML.Recommender`|
||TimeSeries|<xref:Microsoft.ML.TimeSeriesCatalog>|Aggiungere il pacchetto NuGet `Microsoft.ML.TimeSeries`|
|Uso dei modelli ||<xref:Microsoft.ML.ModelOperationsCatalog>||

È possibile passare ai metodi di creazione in ognuna delle categorie precedenti. Se si usa Visual Studio i cataloghi sono visualizzabili tramite IntelliSense.

   ![IntelliSense per gli algoritmi di training di regressione](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a>Creare la pipeline

Ogni catalogo include un set di metodi di estensione. Ora si esaminerà come i metodi di estensione consentono di creare una pipeline di training.

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

Nel frammento, sia `Concatenate` che `Sdca` sono metodi nel catalogo. Ognuno di essi crea un oggetto [IEstimator](xref:Microsoft.ML.IEstimator%601) che viene accodato alla pipeline.

In questa fase viene eseguita solo la creazione degli oggetti. Non si verifica ancora nessuna esecuzione.

### <a name="train-the-model"></a>Eseguire il training del modello

Dopo che sono stati creati gli oggetti nella pipeline, è possibile usare i dati per il training del modello.

```csharp
    var model = pipeline.Fit(trainingData);
```

La chiamata di `Fit()` usa i dati di training di input per stimare i parametri del modello. Questo processo è noto come training del modello. Ricordare che il modello di regressione lineare precedente aveva due parametri di modello: **bias** e **weight**. Dopo la chiamata `Fit()` i valori dei parametri sono noti. La maggior parte dei modelli ha un numero di parametri di molto superiore a questo.

Per ulteriori informazioni sul training dei modelli, vedere [Come eseguire il training del modello.](./how-to-guides/train-machine-learning-model-ml-net.md)

L'oggetto modello risultante implementa l'interfaccia <xref:Microsoft.ML.ITransformer>. In altre parole il modello trasforma i dati di input in stime.

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a>Usare il modello

È possibile trasformare in stime i dati di input in blocco o un input alla volta. Nell'esempio dei prezzi di unità immobiliari sono state eseguite entrambe le trasformazioni: in blocco per valutare il modello e un input alla volta per eseguire una nuova stima. Ora si analizzano le singole stime.

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```

Il metodo `CreatePredictionEngine()` accetta una classe di input e una classe di output. I nomi di campo e/o gli attributi di codice determinano i nomi delle colonne di dati usate durante il training del modello e la stima. Per ulteriori informazioni, consultate [Creare stime con un modello sottoposto a training.](how-to-guides/machine-learning-model-predictions-ml-net.md)

### <a name="data-models-and-schema"></a>Modelli di dati e schema

Alla base di una pipeline di apprendimento automatico ML.NET si trovano gli oggetti [DataView](xref:Microsoft.ML.IDataView).

Ogni trasformazione nella pipeline presenta uno schema di input (nomi, tipi e dimensioni dei dati che la trasformazione prevede come input) e uno schema di output (nomi, tipi e dimensioni dei dati che vengono prodotti dopo la trasformazione). Il documento seguente offre una spiegazione approfondita dell'[interfaccia IDataView e del relativo sistema di tipi](https://xadupre.github.io/machinelearningext/mlnetdocs/idataviewtypesystem.html).

Se lo schema di output di una trasformazione della pipeline non corrisponde allo schema di input della trasformazione successiva, ML.NET genera un'eccezione.

Un oggetto visualizzazione include colonne e righe. Ogni colonna ha un nome, un tipo e una lunghezza. Ad esempio, le colonne di input nell'esempio di prezzo della casa sono **Dimensione** e **Prezzo**. Sono entrambi di tipo e sono quantità scalari piuttosto che vettoriali.

   ![Esempio di visualizzazione dati ML.NET con dati di stima dei prezzi di unità immobiliari](./media/ml-net-dataview.png)

Tutti gli algoritmi ML.NET cercano una colonna di input che è un vettore. Per impostazione predefinita questa colonna vettore è denominata **Features** (Caratteristiche). Per questo motivo la colonna **Size** è stata concatenata in una nuova colonna denominata **Features** nell'esempio per i prezzi di unità immobiliari.

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

Tutti gli algoritmi creano a loro volta nuove colonne dopo che hanno eseguito una stima. I nomi fissi di queste nuove colonne dipendono dal tipo di algoritmo di apprendimento automatico. Per l'attività di regressione una delle nuove colonne è chiamata **Score** (Punteggio). Ecco perché ai dati dei prezzi è stato assegnato un attributo con questo nome.

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```

Per altre informazioni sulle colonne di output delle diverse attività di apprendimento automatico, vedere [Attività di apprendimento automatico](resources/tasks.md).

Una proprietà importante degli oggetti DataView è che vengono valutati **in modo differito**. Le visualizzazioni dei dati vengono caricate ed elaborate solo durante il training e la valutazione del modello e la stima dei dati. Durante la creazione e il testing dell'applicazione ML.NET è possibile usare il debugger di Visual Studio per visualizzare gli oggetti visualizzazione dati tramite la chiamata del metodo [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*).

```csharp
    var debug = testPriceDataView.Preview();
```

È possibile visualizzare la variabile `debug` nel debugger ed esaminarne il contenuto. Non usare il metodo Preview nel codice di produzione, perché riduce notevolmente le prestazioni.

### <a name="model-deployment"></a>Distribuzione del modello

Nelle applicazioni reali il codice di training e valutazione del modello è separato dalla stima. Di fatto, queste due attività vengono spesso eseguite da team separati. Il team di sviluppo del modello può salvare il modello per l'uso nell'applicazione di stima.

```csharp
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="next-steps"></a>Passaggi successivi

* Informazioni su come creare applicazioni usando diverse attività di apprendimento automatico con set di dati più realistici nelle [esercitazioni.](./tutorials/index.md)

* Per ulteriori informazioni, vedere Come eseguire le [guide.](./how-to-guides/index.md)

* Se sei super appassionato, puoi immergerti direttamente nella documentazione di [riferimento dell'API.](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)

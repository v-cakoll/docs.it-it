---
title: Esercitazione sull'analisi dei sentimenti con .NET per Apache Spark e ML.NET
description: In questa esercitazione si apprenderà come usare ML.NET con .NET per Apache Spark per l'analisi dei sentimenti.
author: mamccrea
ms.author: mamccrea
ms.date: 06/25/2020
ms.topic: tutorial
ms.openlocfilehash: 69deb30419b98536fa309547d94f59bb266e413c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617580"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a>Esercitazione: analisi dei sentimenti con .NET per Apache Spark e ML.NET

Questa esercitazione illustra come eseguire l'analisi dei sentimenti delle revisioni online usando ML.NET e .NET per Apache Spark. [Ml.NET](http://dot.net/ml) è un framework gratuito, multipiattaforma open source di machine learning. È possibile usare ML.NET con .NET per Apache Spark per ridimensionare il training e la stima degli algoritmi di machine learning.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> * Creare un modello di analisi dei sentimenti usando il generatore di modelli ML.NET in Visual Studio.
> * Creare un'applicazione .NET per Apache Spark console.
> * Scrivere e implementare una funzione definita dall'utente.
> * Eseguire un'applicazione .NET per Apache Spark console.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a>Prerequisiti

* Se in precedenza non è stata sviluppata un'applicazione .NET per Apache Spark, iniziare con l' [esercitazione Introduzione](get-started.md) per acquisire familiarità con le nozioni di base. Completare tutti i prerequisiti per l'esercitazione Introduzione prima di continuare con questa esercitazione.

* Questa esercitazione usa il generatore di modelli ML.NET (anteprima), un'interfaccia visiva disponibile in Visual Studio. Se non si dispone già di Visual Studio, è possibile [scaricare gratuitamente la versione community di Visual Studio](https://visualstudio.microsoft.com/downloads/) .

* [Scaricare e installare](https://marketplace.visualstudio.com/items?itemName=MLNET.07) Generatore di modelli ML.NET (anteprima).

* Scaricare i set di impostazioni di [yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) e [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) Yelp Review.

## <a name="review-the-data"></a>Esaminare i dati

Il set di dati delle revisioni di Yelp contiene recensioni di Yelp online sui vari servizi. Aprire [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) e osservare la struttura dei dati. La prima colonna contiene il testo della revisione e la seconda colonna contiene i punteggi dei sentimenti. Se il Punteggio di valutazione è 1, la revisione è positiva e se il punteggio del sentimento è 0, la verifica è negativa.

La tabella seguente contiene dati di esempio:

|ReviewText|Valutazione|
|-|-|
|Wow... Questo posto è stato apprezzato.|    1|
|Crust is not good.|    0|

## <a name="build-your-machine-learning-model"></a>Compilare il modello di Machine Learning

1. Aprire Visual Studio e creare una nuova app console C# (.NET Core). Denominare il progetto *MLSparkModel*.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto *MLSparkModel* . Quindi selezionare **aggiungi > Machine Learning**.

1. Dal generatore di modelli ML.NET selezionare il riquadro scenario **analisi del sentiment** .

1. Nella pagina **Aggiungi dati** caricare il set di dati *yelptrain.csv* .

1. Scegliere *sentimento* dall'elenco **a discesa colonne da stimare** .

1. Nella pagina **Train** impostare il tempo di training su *60 secondi* e selezionare **Avvia Training**. Si noti lo stato della formazione in **corso**.

1. Una volta completato il training del generatore di modelli, **valutare** i risultati della formazione. È possibile digitare frasi nella casella di testo seguente **provare a usare il modello** e selezionare **stima** per visualizzare l'output.

1. Selezionare il **codice** e quindi selezionare **Aggiungi progetti** per aggiungere il modello ml alla soluzione.

1. Si noti che per le soluzioni vengono aggiunti due progetti: **MLSparkModelML. ConsoleApp** e **MLSparkModelML. Model**.

1. Fare doppio clic sul progetto *MLSpark* C# e notare che è stato aggiunto il seguente riferimento al progetto.

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a>Creare un'applicazione console

Generatore di modelli crea automaticamente un'app console.

1. Fare clic con il pulsante destro del mouse su **MLSparkModelML. console** in Esplora soluzioni e selezionare **Gestisci pacchetti NuGet**.

1. Cercare **Microsoft. Spark** e installare il pacchetto. **Microsoft.ml** viene automaticamente installato dal generatore di modelli.

### <a name="create-a-sparksession"></a>Creare un SparkSession

1. Aprire il file *Program.cs* per **MLSparkModelML. ConsoleApp**. Questo file è stato generato automaticamente dal generatore di modelli. Eliminare le `using` istruzioni, il contenuto del metodo Main () e l' `CreateSingleDataSample` area.

1. Aggiungere le istruzioni aggiuntive seguenti `using` all'inizio di *Program.cs*:

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. Modificare il `DATA_FILEPATH` percorso del *yelptest.csv*.

1. Aggiungere il codice seguente al `Main` metodo per creare un nuovo oggetto `SparkSession` . La sessione Spark è il punto di ingresso per la programmazione di Spark con il set di dati e l'API dataframe.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   La chiamata all'oggetto *Spark* creato in precedenza consente di accedere alle funzionalità di Spark e dataframe in tutto il programma.

### <a name="create-a-dataframe-and-print-to-console"></a>Creare un dataframe e stamparlo nella console

Leggere i dati della verifica di Yelp dal file di *yelptest.csv* come `DataFrame` . Includere `header` le `inferSchema` Opzioni e. L' `header` opzione legge la prima riga di *yelptest.csv* come nomi di colonna anziché come dati. L' `inferSchema` opzione deduce i tipi di colonna in base ai dati.

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a>Registrare una funzione definita dall'utente

È possibile usare UDF, *funzioni definite dall'utente*nelle applicazioni Spark per eseguire calcoli e analisi sui dati. In questa esercitazione si userà ML.NET con una funzione definita dall'utente per valutare ogni revisione di Yelp.

Aggiungere il codice seguente al `Main` metodo per registrare una funzione definita dall'utente denominata `MLudf` .

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

Questa funzione definita dall'utente accetta una stringa di verifica Yelp come input e restituisce true o false rispettivamente per i sentimenti positivi o negativi. Usa il metodo *Predict ()* definito in un passaggio successivo.

### <a name="use-spark-sql-to-call-the-udf"></a>Usare Spark SQL per chiamare la funzione definita dall'utente

Ora che sono stati letti i dati e sono stati incorporati ML, usare Spark SQL per chiamare la funzione definita dall'utente che eseguirà l'analisi dei sentimenti in ogni riga del dataframe. Aggiungere il codice seguente al metodo `Main`:

```csharp
// Use Spark SQL to call ML.NET UDF
// Display results of sentiment analysis on reviews
df.CreateOrReplaceTempView("Reviews");
DataFrame sqlDf = spark.Sql("SELECT ReviewText, MLudf(ReviewText) FROM Reviews");
sqlDf.Show();

// Print out first 20 rows of data
// Prevent data getting cut off by setting truncate = 0
sqlDf.Show(20, 0, false);

spark.Stop();
```

### <a name="create-predict-method"></a>Crea metodo Predict ()

Aggiungere il codice seguente prima del `Main()` metodo. Questo codice è simile a quello prodotto dal generatore di modelli in *ConsumeModel.cs*. Se si trasferisce questo metodo nella console, il caricamento del modello viene caricato ogni volta che si esegue l'app.

```csharp
private static readonly PredictionEngine<ModelInput, ModelOutput> _predictionEngine;

static Program()
{
    MLContext mlContext = new MLContext();
    ITransformer model = mlContext.Model.Load("MLModel.zip", out DataViewSchema schema);
    _predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(model);
}

static bool predict(string text)
{
    ModelInput input = new ModelInput
    {
        ReviewText = text
    };

    return _predictionEngine.Predict(input).Prediction;
}
```

## <a name="add-the-model-to-your-console-app"></a>Aggiungere il modello all'app console

In Esplora soluzioni copiare il file di *MLModel.zip* dal progetto **MLSparkModelML. Model** e incollarlo nel progetto **MLSparkModelML. ConsoleApp** . Un riferimento viene aggiunto automaticamente in *MLSparkModelML. ConsoleApp. csproj*.

## <a name="run-your-code"></a>Eseguire il codice

Usare `spark-submit` per eseguire il codice. Passare alla cartella radice dell'app console usando il prompt dei comandi ed eseguire i comandi seguenti.

Per prima cosa, pulire e pubblicare l'app.

```dotnetcli
dotnet clean
dotnet publish
```

Passare quindi alla cartella di pubblicazione dell'app console ed eseguire il `spark-submit` comando seguente. Ricordarsi di aggiornare il comando con il percorso effettivo del file jar di Microsoft Spark.

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2.4.x-0.10.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a>Ottenere il codice

Questa esercitazione è simile al codice dell'esempio [analisi del sentiment con Big Data](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) .

## <a name="next-steps"></a>Passaggi successivi

Passare all'articolo successivo per informazioni su come eseguire lo streaming strutturato con .NET per Apache Spark.
> [!div class="nextstepaction"]
> [Esercitazione: flusso strutturato con .NET per Apache Spark](streaming.md)

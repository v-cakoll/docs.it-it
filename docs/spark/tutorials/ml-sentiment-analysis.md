---
title: Analisi del sentiment con .NET per Apache Spark e ML.NET tutorial
description: In questa esercitazione si apprenderà come usare ML.NET con .NET per Apache Spark per l'analisi del sentiment.
author: mamccrea
ms.author: mamccrea
ms.date: 03/25/2019
ms.topic: tutorial
ms.openlocfilehash: cdd1214c26a5d5a4b159df3a396ec6f36b9fc0dd
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391258"
---
# <a name="tutorial-sentiment-analysis-with-net-for-apache-spark-and-mlnet"></a>Esercitazione: Analisi del sentiment con .NET per Apache Spark e ML.NET

Questo tutorial ti insegna come eseguire l'analisi del sentiment delle recensioni online usando ML.NET e .NET per Apache Spark. [ML.NET](http://dot.net/ml) è un framework di apprendimento automatico gratuito, multipiattaforma e open source. È possibile usare ML.NET con .NET per Apache Spark per ridimensionare il training e la stima degli algoritmi di apprendimento automatico.

In questa esercitazione verranno illustrate le procedure per:

> [!div class="checklist"]
>
> * Creare un modello di analisi del sentiment usando ML.NET Model Builder in Visual Studio.Create a sentiment analysis model using ML.NET Model Builder in Visual Studio.
> * Creare un'app console .NET per Apache Spark.Create a .NET for Apache Spark console app.
> * Scrivere e implementare una funzione definita dall'utente.
> * Eseguire un'app console .NET per Apache Spark.

## <a name="prerequisites"></a>Prerequisiti

* Se non è stata sviluppata un'applicazione .NET per Apache Spark in precedenza, iniziare con [l'esercitazione introduttiva](get-started.md) per acquisire familiarità con le nozioni di base. Completare tutti i prerequisiti per l'esercitazione introduttiva prima di continuare con questa esercitazione.

* Questa esercitazione usa il ML.NET Model Builder (anteprima), un'interfaccia visiva disponibile in Visual Studio.This tutorial uses the ML.NET Model Builder (preview), a visual interface available in Visual Studio. Se non si dispone già di Visual Studio, è possibile [scaricare gratuitamente la versione Community di Visual Studio.](https://visualstudio.microsoft.com/downloads/)

* [Scarica e installa](https://marketplace.visualstudio.com/items?itemName=MLNET.07) ML.NET Model Builder (anteprima).

* Scaricare i set di dati [Yelptest.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptest.csv) e [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) Yelp.

## <a name="review-the-data"></a>Esaminare i dati

Il set di dati Yelp reviews contiene recensioni Yelp online su vari servizi. Aprire [yelptrain.csv](https://github.com/dotnet/spark/blob/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment/Resources/yelptrain.csv) e notare la struttura dei dati. La prima colonna contiene il testo della recensione e la seconda colonna contiene i punteggi di valutazione. Se il punteggio del sentiment è 1, la recensione è positiva e se il punteggio del sentiment è 0, la recensione è negativa.

La tabella seguente contiene dati di esempio:The following table contains sample data:

|Testorevisione|Valutazione|
|-|-|
|Wow... Mi è piaciuto molto questo posto.|    1|
|Crust is not good.|    0|

## <a name="build-your-machine-learning-model"></a>Crea il tuo modello di apprendimento automatico

1. Aprire Visual Studio e creare una nuova applicazione console di C . Denominare il progetto *MLSparkModel*.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto *MLSparkModel.* Selezionare quindi **Aggiungi > Machine Learning**.

1. Nella ML.NET Model Builder selezionare il riquadro scenario **Analisi valutazione.**

1. Nella pagina **Aggiungi dati** caricare il set di dati *yelptrain.csv.*

1. Scegli *Valutazione* dall'elenco a discesa **Colonne da pronostilare.**

1. Nella pagina **Treno** impostare l'ora di training su *60 secondi* e selezionare **Avvia formazione**. Si noti lo stato della formazione in **Progress**.

1. Al termine del training di Model Builder, **valutare** i risultati del training. È possibile digitare frasi nella casella di testo sotto **Provare il modello** e selezionare **Previsione** per visualizzare l'output.

1. Selezionare **Codice** e quindi **Aggiungi progetti** per aggiungere il modello di Configurazione istantanea alla soluzione.

1. Si noti che vengono aggiunti due progetti alle soluzioni: **MLSparkModelML.ConsoleApp** e **MLSparkModelML.Model**.

1. Fare doppio clic sul progetto *MLSpark* in C, quindi notare che è stato aggiunto il riferimento al progetto seguente.

   ```xml
   <ItemGroup>
       <ProjectReference Include="..\MLSparkModelML.Model\MLSparkModelML.Model.csproj" />
   </ItemGroup>
   ```

## <a name="create-a-console-app"></a>Creare un'app console

Model Builder crea automaticamente un'app console.

1. Fare clic con il pulsante destro del mouse su **MLSparkModelML.Console** in Esplora soluzioni e selezionare **Gestisci pacchetti NuGet**.

1. Cercare **Microsoft.Spark** e installare il pacchetto. **Microsoft.ML** viene installato automaticamente da Model Builder.

### <a name="create-a-sparksession"></a>Creare una SparkSessionCreate a SparkSession

1. Aprire il file *di Program.cs* per **MLSparkModelML.ConsoleApp**. Questo file è stato generato automaticamente da Model Builder. Eliminare `using` le istruzioni, il contenuto del metodo `CreateSingleDataSample` Main() e l'area.

1. Aggiungere le `using` seguenti istruzioni aggiuntive all'inizio del *Program.cs:*

   ```csharp
   using System;
   using System.Collections.Generic;
   using Microsoft.ML;
   using Microsoft.ML.Data;
   using Microsoft.Spark.Sql;
   using MLSparkModelML.Model;
   ```

1. Modificare `DATA_FILEPATH` il percorso del *file yelptest.csv*.

1. Aggiungere il codice `Main` seguente al metodo `SparkSession`per creare un nuovo oggetto . La sessione Spark è il punto di ingresso alla programmazione Spark con il Dataset e l'API DataFrame.

   ```csharp
   SparkSession spark = SparkSession
        .Builder()
        .AppName(".NET for Apache Spark Sentiment Analysis")
        .GetOrCreate();
   ```

   La chiamata all'oggetto *spark* creato in precedenza consente di accedere alle funzionalità Spark e DataFrame in tutto il programma.

### <a name="create-a-dataframe-and-print-to-console"></a>Creare un frame di dati e stamparlo su consoleCreate a DataFrame and print to console

Leggere i dati di revisione di Yelp dal file `DataFrame` *yelptest.csv* come file . Includi `header` `inferSchema` e opzioni. L'opzione `header` legge la prima riga di *yelptest.csv* come nomi di colonna anziché come dati. L'opzione `inferSchema` deduce i tipi di colonna in base ai dati.

```csharp
DataFrame df = spark
    .ReadStream()
    .Option("header", true)
    .Option("inferSchema", true)
    .Csv(DATA_FILEPATH);

df.Show();
```

### <a name="register-a-user-defined-function"></a>Registrare una funzione definita dall'utenteRegister a user-defined function

È possibile utilizzare funzioni definite dall'utente, *funzioni definite dall'utente,* nelle applicazioni Spark per eseguire calcoli e analisi sui dati. In questa esercitazione si userà ML.NET con una funzione definita dall'utente per valutare ogni revisione Yelp.In this tutorial, you use a share with a UDF to evaluate each Yelp review.

Aggiungere il codice `Main` seguente al metodo per `MLudf`registrare una funzione definita dall'utente denominata .

```csharp
spark.Udf()
    .Register<string, bool>("MLudf", predict);
```

Questa funzione definita dall'utente accetta una stringa di revisione Yelp come input e restituisce true o false rispettivamente per i sentimenti positivi o negativi. Utilizza il metodo *predict()* definito in un passaggio successivo.

### <a name="use-spark-sql-to-call-the-udf"></a>Usare Spark SQL per chiamare la funzione definita dall'utenteUse Spark SQL to call the UDF

Ora che hai letto i dati e incorporato ML, utilizzare Spark SQL per chiamare la funzione definita dall'utente che eseguirà l'analisi del sentiment su ogni riga del frame di dati. Aggiungere il codice seguente al metodo `Main`:

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

### <a name="create-predict-method"></a>Crea metodo predict()

Aggiungere il codice `Main()` seguente prima del metodo. Questo codice è simile a quello prodotto da Model Builder in *ConsumeModel.cs*. Lo spostamento di questo metodo nella console carica il caricamento del modello ogni volta che si esegue l'app.

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

In Esplora soluzioni copiare il file *MLModel.zip* dal progetto **MLSparkModelML.Model** e incollarlo nel progetto **MLSparkModelML.ConsoleApp.** Un riferimento viene aggiunto automaticamente in *MLSparkModelML.ConsoleApp.csproj*.

## <a name="run-your-code"></a>Eseguire il codiceRun your code

Utilizzare `spark-submit` per eseguire il codice. Passare alla cartella radice dell'app console usando il prompt dei comandi ed eseguire i comandi seguenti.

Innanzitutto, pulisci e pubblica la tua app.

```dotnetcli
dotnet clean
dotnet publish
```

Passare quindi alla cartella di pubblicazione dell'app console ed eseguire il comando seguente. `spark-submit` Ricordarsi di aggiornare il comando con il percorso effettivo del file jar di Microsoft Spark.

```dotnetcli
%SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local microsoft-spark-2.4.x-0.10.0.jar dotnet MLSparkModelML.ConsoleApp.dll
```

## <a name="get-the-code"></a>Ottenere il codice

Questa esercitazione è simile al codice dell'esempio [di analisi del sentiment con Big Data.This](https://github.com/dotnet/spark/tree/master/examples/Microsoft.Spark.CSharp.Examples/MachineLearning/Sentiment) tutorial is similar to the code from the Sentiment Analysis with Big Data example.

## <a name="next-steps"></a>Passaggi successivi

Passare all'articolo successivo per informazioni su come eseguire lo streaming strutturato con .NET per Apache Spark.
> [!div class="nextstepaction"]
> [Esercitazione: Streaming strutturato con .NET per Apache SparkTutorial: Structured Streaming with .NET for Apache Spark](streaming.md)

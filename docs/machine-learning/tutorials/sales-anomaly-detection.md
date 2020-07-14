---
title: 'Esercitazione: rilevare le anomalie nelle vendite di prodotti'
description: Informazioni su come creare un'applicazione di rilevamento delle anomalie per i dati di vendita dei prodotti. Questa esercitazione crea un'applicazione console .NET Core usando C# in Visual Studio 2019.
ms.date: 06/30/2020
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: cf61f197e4befebdbb1fbf2ca4cbcdc61c48780a
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281667"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a>Esercitazione: rilevare le anomalie nelle vendite di prodotti con ML.NET

Informazioni su come creare un'applicazione di rilevamento delle anomalie per i dati di vendita dei prodotti. Questa esercitazione crea un'applicazione console .NET Core usando C# in Visual Studio.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> * Caricare i dati
> * Creare una trasformazione per il rilevamento di anomalie dei picchi
> * Rilevare le anomalie dei picchi con la trasformazione
> * Creare una trasformazione per il rilevamento di anomalie dei punti di modifica
> * Rilevare le anomalie dei punti di modifica con la trasformazione

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 versione 15,6 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro "sviluppo multipiattaforma .NET Core" installato.

* [Set di dati product-sales.csv](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> Il formato di dati usato in `product-sales.csv` è basato sul set di dati "Vendite di shampoo in un arco di tre anni" ricavato originariamente da DataMarket e fornito da Time Series Data Library (TSDL), di Rob Hyndman.
> Set di dati "Vendite di shampoo in un arco di tre anni" concesso in licenza nell'ambito della licenza aperta predefinita DataMarket.

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Creare un'**applicazione Console .NET Core** denominata "ProductSalesAnomalyDetection".

2. Creare una directory denominata *Data* nel progetto per salvare i file del set di dati.

3. Installare il **pacchetto NuGet Microsoft.ML**:

    [!INCLUDE [mlnet-current-nuget-version](../../../includes/mlnet-current-nuget-version.md)]

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine del pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ml** e selezionare il pulsante **Installa** . Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati. Ripetere questi passaggi per **Microsoft. ml. TimeSeries**.

4. Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

    [!code-csharp[AddUsings](./snippets/sales-anomaly-detection/csharp/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>Scarica i tuoi dati

1. Scaricare il set di dati e salvarlo nella cartella *Dati* precedentemente creata:

   * Fare clic con il pulsante destro del mouse su [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) e selezionare "Salva collegamento con nome..." o "Salva oggetto con nome..."

     Assicurarsi di salvare i file \*.csv nella cartella *Dati* oppure, dopo averli salvati in un altro percorso, spostare i file \*.csv nella cartella *Dati*.

2. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file \*.csv e scegliere **Proprietà**. In **Avanzate**impostare il valore di **copia nella directory di output** su **copia se più recente**.

Nella tabella seguente è riportata un'anteprima dei dati del file \*.csv:

|Month  |VenditeProdotto |
|-------|-------------|
|1 - gen  |    271      |
|2 - gen  |    150.9    |
|.....  |    .....    |
|1-feb  |    199.3    |
|.....  |    .....    |

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

Successivamente, definire le strutture dei dati delle classi di input e stima.

Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Aggiungi > Nuovo elemento**.

2. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *ProductSalesData.cs*. Selezionare quindi il pulsante **Aggiungi**.

   Il file *ProductSalesData.cs* verrà aperto nell'editor del codice.

3. Aggiungere l'istruzione `using` seguente all'inizio di *ProductSalesData.cs*:

   ```csharp
   using Microsoft.ML.Data;
   ```

4. Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `ProductSalesData` e `ProductSalesPrediction`, al file *ProductSalesData.cs*:

    [!code-csharp[DeclareTypes](./snippets/sales-anomaly-detection/csharp/ProductSalesData.cs#DeclareTypes "Declare data record types")]

    `ProductSalesData` specifica una classe di dati di input. L'attributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) specifica quali colonne (in base all'indice delle colonne) nel set di dati è necessario caricare.

    `ProductSalesPrediction` specifica la classe di dati di stima. Per il rilevamento delle anomalie, la stima consiste in un avviso per indicare l'eventuale presenza di un'anomalia, un punteggio non elaborato e un valore p. Quanto più vicino a 0 è il valore p, tanto maggiore è la probabilità che si sia verificata un'anomalia.

5. Creare due campi globali per contenere il percorso del file del set di dati scaricato di recente e il percorso del file del modello salvato:

    * `_dataPath` contiene il percorso del set di dati usato per il training del modello.
    * `_docsize` contiene il numero di record presenti nel file del set di dati. Si userà `_docSize` per calcolare `pvalueHistoryLength`.

6. Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi:

    [!code-csharp[Declare global variables](./snippets/sales-anomaly-detection/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

1. Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile `mlContext`:

    [!code-csharp[CreateMLContext](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateMLContext "Create the ML Context")]

    La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

### <a name="load-the-data"></a>Caricare i dati

I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView). `IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo). È possibile caricare dati da un file di testo o da altre origini, ad esempio un database SQL o file di log, in un oggetto `IDataView`.

1. Aggiungere il codice seguente al metodo `Main()` come riga successiva:

    [!code-csharp[LoadData](./snippets/sales-anomaly-detection/csharp/Program.cs#LoadData "loading dataset")]

    [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema dei dati e legge il contenuto del file. Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.

## <a name="time-series-anomaly-detection"></a>Rilevamento delle anomalie delle serie temporali

Il rilevamento delle anomalie segnala eventi o comportamenti imprevisti o insoliti. Fornisce indizi su dove cercare i problemi e consente di rispondere alla domanda "È strano?".

![Esempio del rilevamento anomalie "è questo strano".](./media/sales-anomaly-detection/time-series-anomaly-detection.png)

Il rilevamento delle anomalie è il processo di rilevamento degli outlier dati delle serie temporali; indica una determinata serie temporale di input in cui il comportamento non è quello previsto o è "strano".

Il rilevamento delle anomalie può essere utile in molte situazioni. Ad esempio:

Se si dispone di un'auto, è possibile che si desideri essere a conoscenza della normale presenza di questo misuratore.
Se si sta monitorando il consumo di energia elettrica, è opportuno essere a conoscenza della presenza di un'interruzione.

Esistono due tipi di anomalie di serie temporali che possono essere rilevati:

* **I picchi** indicano accessi temporanei di comportamenti anomali nel sistema.

* **I punti di modifica** indicano l'inizio di modifiche persistenti nel corso del tempo nel sistema.

In ML.NET, gli algoritmi IID Spike Detection o IID Change point Detection sono adatti ai [set di dati indipendenti e distribuiti in modo identico](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).

A differenza dei modelli nelle altre esercitazioni, le trasformazioni di rilevamento delle anomalie nelle serie temporali vengono applicate direttamente ai dati di input. Il metodo `IEstimator.Fit()` non necessita dei dati di training per generare la trasformazione. Ha tuttavia bisogno dello schema dei dati, fornito da una visualizzazione dati generata da un elenco vuoto di `ProductSalesData`.

Analizzare gli stessi dati di vendita del prodotto per rilevare i picchi e i punti di modifica. Il processo del modello di compilazione e di training è lo stesso per il rilevamento dei picchi e dei punti di modifica; la differenza principale è l'algoritmo di rilevamento specifico usato.

## <a name="spike-detection"></a>Rilevamento dei picchi

Lo scopo del rilevamento dei picchi consiste nell'identificare i picchi improvvisi ma temporanei che differiscono notevolmente dalla maggior parte dei valori dei dati delle serie temporali. È importante rilevare questi elementi, osservazioni o eventi rari sospetti in modo tempestivo per fare in modo che abbiano un impatto minimo. L'approccio seguente può essere usato per rilevare un'ampia gamma di anomalie, quali: interruzioni del servizio, attacchi informatici o contenuto web virale. L'immagine seguente riporta un esempio di picchi in un set di dati relativo a una serie temporale:

![Screenshot che mostra due rilevamenti di picchi.](./media/sales-anomaly-detection/two-spike-detections.png)

### <a name="add-the-createemptydataview-method"></a>Aggiungere il metodo CreateEmptyDataView()

Aggiungere il metodo seguente a `Program.cs`:

[!code-csharp[CreateEmptyDataView](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateEmptyDataView)]

Il metodo `CreateEmptyDataView()` genera un oggetto visualizzazione dati vuoto con lo schema corretto, da usare come input per il metodo `IEstimator.Fit()`.

### <a name="create-the-detectspike-method"></a>Creare il metodo DetectSpike()

Il metodo `DetectSpike()`:

* Crea la trasformazione dallo strumento di stima.
* Rileva picchi in base ai dati cronologici di vendita.
* Visualizza i risultati.

1. Creare il metodo `DetectSpike()` subito dopo il metodo `Main()`, usando il codice seguente:

    ```csharp
    static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. Usare [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) per eseguire il training del modello per il rilevamento dei picchi. Aggiungerlo al metodo `DetectSpike()` con il codice seguente:

    [!code-csharp[AddSpikeTrainer](./snippets/sales-anomaly-detection/csharp/Program.cs#AddSpikeTrainer)]

1. Creare la trasformazione di rilevamento dei picchi aggiungendo il codice seguente come riga successiva nel metodo `DetectSpike()`:

    [!code-csharp[TrainModel1](./snippets/sales-anomaly-detection/csharp/Program.cs#TrainModel1)]

1. Aggiungere la seguente riga di codice per trasformare i dati `productSales` nella riga successiva nel metodo `DetectSpike()`:

    [!code-csharp[TransformData1](./snippets/sales-anomaly-detection/csharp/Program.cs#TransformData1)]

    Il codice precedente usa il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) per effettuare stime per più righe di input di un set di dati.

1. Convertire `transformedData` in un oggetto fortemente tipizzato `IEnumerable` per una visualizzazione più semplice usando il metodo [CreateEnumerable ()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con il codice seguente:

    [!code-csharp[CreateEnumerable1](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateEnumerable1)]

1. Creare una linea dell'intestazione di visualizzazione usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

    [!code-csharp[DisplayHeader1](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayHeader1)]

    Nei risultati relativi al rilevamento di picchi saranno visualizzate le informazioni seguenti:

    * `Alert` indica un avviso di picco per un punto dati specificato.
    * `Score` è il valore `ProductSales` per un punto dati specificato nel set di dati.
    * `P-Value` "P" è l'acronimo di probabilità. Quanto più vicino a 0 è il valore p, tanto maggiore è la probabilità che il punto dati costituisca un'anomalia.

1. Usare il codice seguente per scorrere `predictions` `IEnumerable` e visualizzare i risultati:

    [!code-csharp[DisplayResults1](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayResults1)]

1. Aggiungere la chiamata al metodo `DetectSpike()` nel metodo `Main()`:

    [!code-csharp[CallDetectSpike](./snippets/sales-anomaly-detection/csharp/Program.cs#CallDetectSpike)]

## <a name="spike-detection-results"></a>Risultati del rilevamento di picchi

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione, vengono visualizzati alcuni messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Per maggiore chiarezza, dai risultati seguenti sono stati rimossi alcuni messaggi.

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a>Rilevamento dei punti di modifica

`Change points` sono modifiche permanenti in una serie temporale di un flusso di distribuzione di valori, come le modifiche di livello e le tendenze. Queste modifiche persistenti durano molto più tempo rispetto ai `spikes` e potrebbero indicare uno o più eventi catastrofici. I `Change points` non sono in genere visibili a occhio nudo, ma possono essere rilevati nei dati usando alcuni approcci, come nel metodo seguente.  L'immagine seguente rappresenta un esempio di rilevamento di un punto di modifica:

![Screenshot che mostra il rilevamento di un punto di modifica.](./media/sales-anomaly-detection/change-point-detection.png)

### <a name="create-the-detectchangepoint-method"></a>Creare il metodo DetectChangepoint()

Il metodo `DetectChangepoint()` esegue le attività seguenti:

* Crea la trasformazione dallo strumento di stima.
* Rileva punti di modifica in base ai dati cronologici di vendita.
* Visualizza i risultati.

1. Creare il metodo `DetectChangepoint()` subito dopo il metodo `Main()`, usando il codice seguente:

    ```csharp
    static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
    {

    }
    ```

1. Creare l'oggetto [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) nel metodo `DetectChangepoint()` con il codice seguente:

    [!code-csharp[AddChangepointTrainer](./snippets/sales-anomaly-detection/csharp/Program.cs#AddChangepointTrainer)]

1. Come già fatto in precedenza, creare la trasformazione dallo strumento di stima aggiungendo la riga di codice seguente nel metodo `DetectChangePoint()`:

    [!code-csharp[TrainModel2](./snippets/sales-anomaly-detection/csharp/Program.cs#TrainModel2)]

1. Usare il metodo `Transform()` per trasformare i dati aggiungendo il codice seguente a `DetectChangePoint()`:

    [!code-csharp[TransformData2](./snippets/sales-anomaly-detection/csharp/Program.cs#TransformData2)]

1. Come è stato fatto in precedenza, convertire `transformedData` in un fortemente tipizzato `IEnumerable` per una visualizzazione più semplice usando il `CreateEnumerable()` metodo con il codice seguente:

    [!code-csharp[CreateEnumerable2](./snippets/sales-anomaly-detection/csharp/Program.cs#CreateEnumerable2)]

1. Creare un'intestazione di visualizzazione con il codice seguente al metodo `DetectChangePoint()` come riga successiva:

    [!code-csharp[DisplayHeader2](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayHeader2)]

    Nei risultati del rilevamento di punti di modifica saranno visualizzate le informazioni seguenti:

    * `Alert` indica un avviso di punto di modifica per un punto dati specificato.
    * `Score` è il valore `ProductSales` per un punto dati specificato nel set di dati.
    * `P-Value` "P" è l'acronimo di probabilità. Quanto più vicino a 0 è il valore P, tanto maggiore è la probabilità che il punto dati costituisca un'anomalia.
    * `Martingale value` viene usato per identificare il livello di "anomalia" del punto dati, in base alla sequenza di valori di P.

1. Scorrere `predictions` `IEnumerable` e visualizzare i risultati con il codice seguente:

    [!code-csharp[DisplayResults2](./snippets/sales-anomaly-detection/csharp/Program.cs#DisplayResults2)]

1. Aggiungere la chiamata seguente al metodo `DetectChangepoint()` nel metodo `Main()`:

    [!code-csharp[CallDetectChangepoint](./snippets/sales-anomaly-detection/csharp/Program.cs#CallDetectChangepoint)]

## <a name="change-point-detection-results"></a>Risultati del rilevamento dei punti di modifica

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione, vengono visualizzati alcuni messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Per maggiore chiarezza, dai risultati seguenti sono stati rimossi alcuni messaggi.

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

Congratulazioni! Sono stati compilati modelli di machine learning per il rilevamento di anomalie quali picchi e punti di modifica nei dati di vendita.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

In questa esercitazione sono state illustrate le procedure per:
> [!div class="checklist"]
>
> * Caricare i dati
> * Eseguire il training del modello per il rilevamento anomalie dei picchi
> * Rilevare le anomalie dei picchi con il modello con training
> * Eseguire il training del modello per il rilevamento anomalie dei punti di modifica
> * Rilevare le anomalie del punto di modifica con il modello con training

## <a name="next-steps"></a>Passaggi successivi

Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di rilevamento di anomalie di consumo energetico.
> [!div class="nextstepaction"]
> [Repository GitHub dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)

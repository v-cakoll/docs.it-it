---
title: 'Esercitazione: Rilevare le anomalie nelle vendite di prodotti'
description: Informazioni su come creare un'applicazione di rilevamento delle anomalie per i dati di vendita dei prodotti. Questa esercitazione crea un'applicazione console .NET Core usando C# in Visual Studio 2019.
ms.date: 07/17/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: e87034733b048153202bc11ab94ed7605749f60c
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331684"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a>Esercitazione: Rilevare le anomalie nelle vendite di prodotti con ML.NET

Informazioni su come creare un'applicazione di rilevamento delle anomalie per i dati di vendita dei prodotti. Questa esercitazione crea un'applicazione console .NET Core usando C# in Visual Studio.

In questa esercitazione si imparerà a:
> [!div class="checklist"]
> * Caricare i dati
> * Eseguire il training del modello per il rilevamento anomalie dei picchi
> * Rilevare le anomalie dei picchi con il modello con training
> * Eseguire il training del modello per il rilevamento anomalie dei punti di modifica
> * Rilevare le anomalie dei punti di modifica con il modello con training

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio 2017 15.6 o versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato.

* [Set di dati product-sales.csv](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> Il formato di dati usato in `product-sales.csv` è basato sul set di dati "Vendite di shampoo in un arco di tre anni" ricavato originariamente da DataMarket e fornito da Time Series Data Library (TSDL), di Rob Hyndman. Set di dati "Vendite di shampoo in un arco di tre anni" concesso in licenza nell'ambito della licenza aperta predefinita DataMarket.

## <a name="create-a-console-application"></a>Creare un'applicazione console

1. Creare un'**applicazione Console .NET Core** denominata "ProductSalesAnomalyDetection".

2. Creare una directory denominata *Dati* nel progetto per salvare i file del set di dati.

3. Installare il **pacchetto NuGet Microsoft.ML**:

    In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto e selezionare **Gestisci pacchetti NuGet**. Scegliere "nuget.org" come origine pacchetto, selezionare la scheda Sfoglia, cercare **Microsoft.ML**, selezionare il pacchetto **v1.0.0** nell'elenco e quindi selezionare il pulsante **Installa**. Selezionare il pulsante **OK** nella finestra di dialogo **Anteprima modifiche** e quindi selezionare il pulsante **Accetto** nella finestra di dialogo **Accettazione della licenza** se si accettano le condizioni di licenza per i pacchetti elencati. Ripetere questi passaggi per **Microsoft.ML.TimeSeries v0.12.0**.

4. Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>Scaricare i dati

1. Scaricare il set di dati e salvarlo nella cartella *Dati* precedentemente creata:

   * Fare clic con il pulsante destro del mouse su [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) e selezionare "Salva collegamento con nome..." o "Salva oggetto con nome..."

     Assicurarsi di salvare i file \*.csv nella cartella *Dati* oppure, dopo averli salvati in un altro percorso, spostare i file \*.csv nella cartella *Dati*.

2. In Esplora soluzioni fare clic con il pulsante destro del mouse sul file \*.csv e scegliere **Proprietà**. In **Avanzate** impostare il valore di **Copia nella directory di output** su **Copia se più recente**.

Nella tabella seguente è riportata un'anteprima dei dati del file \*.csv:

|Mese  |VenditeProdotto |
|-------|-------------|
|1 - gen  |    271      |
|2 - gen  |    150.9    |
|.....  |    .....    |
|1-feb  |    199.3    |
|.....  |    .....    |

### <a name="create-classes-and-define-paths"></a>Creare le classi e definire i percorsi

Successivamente, definire la struttura dei dati della classe di input.

Aggiungere una nuova classe al progetto:

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e quindi scegliere **Aggiungi > Nuovo elemento**.

2. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **Classe** e impostare il campo **Nome** su *ProductSalesData.cs*. Selezionare quindi il pulsante **Aggiungi**.

Il file *ProductSalesData.cs* verrà aperto nell'editor del codice. Aggiungere l'istruzione `using` seguente all'inizio di *ProductSalesData.cs*:

```csharp
using Microsoft.ML.Data;
```

Rimuovere la definizione di classe esistente e aggiungere il codice seguente, che contiene le due classi `ProductSalesData` e `ProductSalesPrediction`, al file *ProductSalesData.cs*:

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

`ProductSalesData` specifica una classe di dati di input. L'attributo [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) specifica quali colonne (in base all'indice delle colonne) nel set di dati è necessario caricare. 

Aggiungere le istruzioni `using` seguenti all'inizio del file *Program.cs*:

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

È necessario creare due campi globali per contenere il percorso del file del set di dati scaricato di recente e il percorso del file modello salvato:

* `_dataPath` contiene il percorso del set di dati usato per il training del modello.
* `_docsize` contiene il numero di record presenti nel file del set di dati. Verrà usato per calcolare `pvalueHistoryLength`.

Aggiungere il codice seguente nella riga immediatamente sopra il metodo `Main` per specificare questi percorsi:

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

La [classe MLContext](xref:Microsoft.ML.MLContext) è un punto di partenza per tutte le operazioni ML.NET e l'inizializzazione di `mlContext` crea un nuovo ambiente ML.NET che può essere condiviso tra gli oggetti del flusso di lavoro della creazione del modello. Dal punto di vista concettuale è simile a `DBContext` in Entity Framework.

### <a name="initialize-variables-in-main"></a>Inizializzare le variabili in Main

Sostituire la riga `Console.WriteLine("Hello World!")` nel metodo `Main` con il codice seguente per dichiarare e inizializzare la variabile `mlContext`:

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a>Caricare i dati

I dati in ML.NET sono rappresentati come una [classe IDataView](xref:Microsoft.ML.IDataView). `IDataView` è un modo flessibile ed efficiente di descrivere i dati tabulari (numerici e di testo). È possibile caricare dati da un file di testo o in tempo reale, ad esempio da un database SQL o file di log, in un oggetto `IDataView`. Aggiungere il codice seguente al metodo `Main()` come riga successiva:

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) definisce lo schema dei dati e legge il contenuto del file. Acquisisce le variabili di percorso dei dati e restituisce un oggetto `IDataView`.

## <a name="ml-task---time-series-anomaly-detection"></a>Attività di Machine Learning - rilevamento delle anomalie delle serie temporali 

Il rilevamento delle anomalie segnala eventi o comportamenti inattesi o insoliti. Fornisce indizi su dove cercare i problemi e consente di rispondere alla domanda "È strano?".

![È strano](./media/sales-anomaly-detection/anomalydetection.png)

Il rilevamento delle anomalie è il processo di rilevamento degli outlier dati delle serie temporali; indica una determinata serie temporale di input in cui il comportamento non è quello previsto o è "strano".

Ciò può essere utile in molti modi. Ad esempio:

Se si dispone di un'automobile, si potrebbe voler sapere se: La lettura del manometro dell'olio è normale o è presente una perdita?
Se si sta monitorando il consumo di energia elettrica, si desidera sapere: se vi è un'interruzione del servizio.

Esistono due tipi di anomalie di serie temporali che possono essere rilevati: 

* **I picchi** indicano accessi temporanei di comportamenti anomali nel sistema. 

* **I punti di modifica** indicano l'inizio di modifiche persistenti nel corso del tempo nel sistema. 

In ML.NET, gli algoritmi IID Spike Detection o IID Change point Detection sono adatti ai [set di dati indipendenti e distribuiti in modo identico](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables). 

Analizzare gli stessi dati di vendita del prodotto per rilevare i picchi e i punti di modifica. Il processo del modello di compilazione e di training è lo stesso per il rilevamento dei picchi e dei punti di modifica; la differenza principale è l'algoritmo di rilevamento specifico usato.

## <a name="spike-detection"></a>Rilevamento dei picchi 

Lo scopo del rilevamento dei picchi consiste nell'identificare i picchi improvvisi ma temporanei che differiscono notevolmente dalla maggior parte dei valori dei dati delle serie temporali. È importante rilevare questi elementi, eventi oppure osservazioni rari sospetti in modo tempestivo per fare in modo che abbiano un impatto minimo. L'approccio seguente può essere usato per rilevare un'ampia gamma di anomalie, quali: interruzioni del servizio, attacchi informatici o contenuto web virale. L'immagine seguente riporta un esempio di picchi in un set di dati relativo a una serie temporale:

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a>Creare il metodo DetectSpike()

Aggiungere la seguente chiamata al metodo `DetectSpike()` come riga successiva nel metodo `Main()`:

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

Il metodo `DetectSpike()` esegue le attività seguenti:

* Esegue il training del modello.
* Rileva picchi in base ai dati cronologici di vendita.
* Visualizza i risultati.

Creare il metodo `DetectSpike()` subito dopo il metodo `Main()`, usando il codice seguente:

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

Usare [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) per eseguire il training del modello per il rilevamento dei picchi. Aggiungerlo al metodo `DetectSpike()` con il codice seguente:

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

Adattare il modello ai dati di `productSales` aggiungendo il codice seguente come riga successiva nel metodo `DetectSpike()`:

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

Il metodo [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) esegue il training del modello trasformando il set di dati e applicando il training.

Aggiungere la seguente riga di codice per trasformare i dati `productSales` nella riga successiva nel metodo `DetectSpike()`:

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

Il codice precedente usa il metodo [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) per effettuare previsioni per più righe di input specificate di un set di dati di test.

Convertire `transformedData` in un oggetto `IEnumerable` fortemente tipizzato per una visualizzazione più semplice tramite il metodo [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) con il codice seguente:

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

Creare una linea dell'intestazione di visualizzazione usando il codice <xref:System.Console.WriteLine?displayProperty=nameWithType> seguente:

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

Nei risultati relativi al rilevamento di picchi saranno visualizzate le informazioni seguenti:

* `Alert` indica un avviso di picco per un punto dati specificato.

* `Score` è il valore `ProductSales` per un punto dati specificato nel set di dati.

* `P-Value` "P" è l'acronimo di probabilità. Indica con che probabilità il punto dati è un'anomalia. 

Usare il codice seguente per eseguire l'iterazione attraverso `predictions` `IEnumerable` e visualizzare i risultati:

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a>Risultati del rilevamento di picchi

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione, vengono visualizzati alcuni messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

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

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a>Creare il metodo DetectChangepoint()

Aggiungere la seguente chiamata al metodo `DetectChangepoint()` come riga successiva nel metodo `Main()`:

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

Il metodo `DetectChangepoint()` esegue le attività seguenti:

* Esegue il training del modello.
* Rileva punti di modifica in base ai dati cronologici di vendita.
* Visualizza i risultati.

Creare il metodo `DetectChangepoint()` subito dopo il metodo `Main()`, usando il codice seguente:

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

[iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) viene usato per il training del modello per il rilevamento dei punti di modifica. Aggiungerlo al metodo `DetectChangepoint()` con il codice seguente:

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

Come in precedenza, adattare il modello ai dati di `productSales` aggiungendo il codice seguente come riga successiva nel metodo `DetectChangePoint()`:

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

Usare il metodo `Transform()` per trasformare i dati `Training` aggiungendo il codice seguente a `DetectChangePoint()`:

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

Come già fatto in precedenza, convertire `transformedData` in un oggetto `IEnumerable` fortemente tipizzato per una visualizzazione più semplice tramite il metodo `CreateEnumerable()` con il codice seguente:

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

Creare un'intestazione di visualizzazione con il codice seguente al metodo `DetectChangePoint()` come riga successiva:

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

Nei risultati del rilevamento di punti di modifica saranno visualizzate le informazioni seguenti:

* `Alert` indica un avviso di punto di modifica per un punto dati specificato.
* `Score` è il valore `ProductSales` per un punto dati specificato nel set di dati.
* `P-Value` "P" è l'acronimo di probabilità. Indica con che probabilità il punto dati è un'anomalia. 
* `Martingale value` viene usato per identificare il livello di "anomalia" del punto dati, in base alla sequenza di valori di P.  

Eseguire l'iterazione attraverso `predictions` `IEnumerable` e visualizzare i risultati con il codice seguente:

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a>Risultati del rilevamento dei punti di modifica

I risultati dovrebbero essere simili a quanto riportato di seguito. Durante l'elaborazione, vengono visualizzati alcuni messaggi. Possono essere mostrati avvisi o messaggi relativi all'elaborazione. Questi elementi sono stati rimossi dai risultati seguenti per maggiore chiarezza.

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

La procedura è stata completata. Sono stati compilati modelli di machine learning per il rilevamento di anomalie quali picchi e punti di modifica nei dati di vendita.

È possibile trovare il codice sorgente per questa esercitazione nel repository [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection).

In questa esercitazione si è appreso come:
> [!div class="checklist"]
> * Caricare i dati
> * Eseguire il training del modello per il rilevamento anomalie dei picchi
> * Rilevare le anomalie dei picchi con il modello con training
> * Eseguire il training del modello per il rilevamento anomalie dei punti di modifica
> * Rilevare le anomalie del punto di modifica con il modello con training

## <a name="next-steps"></a>Passaggi successivi

Consultare il repository GitHub degli esempi di Machine Learning per esaminare un esempio di rilevamento di anomalie di consumo energetico.
> [!div class="nextstepaction"]
> [Repository GitHub dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)

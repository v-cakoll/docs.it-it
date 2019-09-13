---
title: Preparare i dati per la creazione di un modello
description: Informazioni su come usare le trasformazioni in ML.NET per manipolare e preparare i dati per un'ulteriore elaborazione o creazione di un modello.
author: luisquintanilla
ms.author: luquinta
ms.date: 09/11/2019
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 4452aef351f33df532f3c673307dedbbf71631b8
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929363"
---
# <a name="prepare-data-for-building-a-model"></a>Preparare i dati per la creazione di un modello

Informazioni su come usare ML.NET per preparare i dati per un'ulteriore elaborazione o creazione di un modello.

I dati sono spesso sparsi e non puliti. Gli algoritmi di Machine Learning ML.NET prevedono che l'input o le funzionalità siano in un singolo vettore numerico. Analogamente, il valore da stimare (etichetta), soprattutto quando si tratta di dati categorici, deve essere codificato. Uno degli obiettivi della preparazione dei dati, pertanto, è conferire ai dati il formato previsto dagli algoritmi di ML.NET. 

## <a name="filter-data"></a>Filtrare i dati

In alcuni casi, non tutti i dati in un set di dati sono rilevanti per l'analisi. Un modo per rimuovere i dati irrilevanti da un set di dati consiste nell'applicare dei filtri. La classe [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contiene un set di operazioni di filtro che esaminano un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) che contiene tutti i dati e restituiscono un'interfaccia [IDataView](xref:Microsoft.ML.IDataView) contenente solo i punti dati di interesse. È importante notare che, poiché non sono di tipo [`IEstimator`](xref:Microsoft.ML.IEstimator%601) e neppure [`ITransformer`](xref:Microsoft.ML.ITransformer) come quelle disponibili nella classe [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), le operazioni di filtro non possono essere incluse in una pipeline di preparazione dei dati [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) o [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601). 

Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

Per filtrare i dati in base al valore di una colonna, usare il metodo [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*).

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

L'esempio precedente considera le righe del set di dati con un prezzo compreso tra 200000 e 1000000. Il risultato che si otterrebbe applicando questo filtro sarebbe la restituzione solo delle ultime due righe di dati e l'esclusione della prima riga perché il prezzo è 100000 e pertanto non rientra nell'intervallo specificato.

## <a name="replace-missing-values"></a>Sostituire valori mancanti

I valori mancanti sono un evento comune nei set di dati. Un modo per gestire i valori mancanti consiste nel sostituirli con il valore predefinito, qualora esistesse per il tipo specificato, oppure con un altro valore significativo, ad esempio il valore medio dei dati. 

Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=float.NaN
    }
};
```

Si noti che l'ultimo elemento nell'elenco presenta un valore mancante per `Price`. Per sostituire i valori mancanti nella colonna `Price`, inserire valore mancante usando il metodo [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*).

> [!IMPORTANT]
> [`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) funziona solo con dati numerici.

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

ML.NET supporta varie [modalità sostituzione](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode). L'esempio precedente usa la modalità sostituzione `Mean` che inserirà il valore medio della colonna per sopperire al valore mancante. Il risultato della sostituzione completa la proprietà `Price` dell'ultimo elemento di dati con il valore 200.000 perché è la media fra 100.000 e 300.000. 

## <a name="use-normalizers"></a>Usare i normalizzatori

La [normalizzazione](https://en.wikipedia.org/wiki/Feature_scaling) è una tecnica usata nella pre-elaborazione dei dati per standardizzare le caratteristiche che non condividono la stessa scala e, pertanto, aiutare gli algoritmi a convergere più velocemente. Gli intervalli di valori di età e reddito, ad esempio, variano in modo significativo perché l'età è generalmente compresa nell'intervallo da 0 a 100 e il reddito nell'intervallo da 0 a diverse migliaia. Visitare la pagina [Trasformazioni dati](../resources/transforms.md) per un elenco e una descrizione più dettagliati delle trasformazioni di normalizzazione. 

### <a name="min-max-normalization"></a>Normalizzazione min-max

Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms = 2f,
        Price = 200000f
    },
    new HomeData
    {
        NumberOfBedrooms = 1f,
        Price = 100000f
    }
};
```

È possibile applicare la normalizzazione alle colonne con valori numerici singoli, nonché vettori. Normalizzare i dati nella colonna `Price` usando la normalizzazione min-max con il metodo [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*).

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

I valori di prezzo originali `[200000,100000]` vengono convertiti in `[ 1, 0.5 ]` usando la formula di normalizzazione `MinMax` che genera valori di output nell'intervallo 0-1.

### <a name="binning"></a>Binning

Il processo di [binning](https://en.wikipedia.org/wiki/Data_binning) converte valori continui in una rappresentazione discreta dell'input. Si supponga, ad esempio, che una delle caratteristiche sia l'età. Invece di usare il valore effettivo dell'età, per tale valore il processo di binning crea intervalli. 0-18 potrebbe essere un intervallo, 19-35 potrebbe essere un altro intervallo e così via. 

Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
HomeData[] homeDataList = new HomeData[]
{
    new HomeData
    {
        NumberOfBedrooms=1f,
        Price=100000f
    },
    new HomeData
    {
        NumberOfBedrooms=2f,
        Price=300000f
    },
    new HomeData
    {
        NumberOfBedrooms=6f,
        Price=600000f
    }
};
```

Normalizzare i dati in contenitori usando il metodo [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*). Il parametro `maximumBinCount` consente di specificare il numero di contenitori necessari per classificare i dati. In questo esempio i dati verranno inseriti in due contenitori.  

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

Il risultato del processo di binning è la creazione di limiti per i contenitori di `[0,200000,Infinity]`. Di conseguenza, i contenitori risultanti sono `[0,1,1]` perché la prima osservazione prende in considerazione i valori tra 0 e 200000 e gli altri sono maggiori di 200000 ma inferiori a infinito.

## <a name="work-with-categorical-data"></a>Usare dati di categorie

I dati di categorie non numerici devono essere convertiti in numeri prima di poter essere usati per creare un modello di Machine Learning. 

Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
CarData[] cars = new CarData[] 
{
    new CarData
    {
        Color="Red",
        VehicleType="SUV"
    },
    new CarData
    {
        Color="Blue",
        VehicleType="Sedan"
    },
    new CarData
    {
        Color="Black",
        VehicleType="SUV"
    }
};
```

La proprietà di categoria `VehicleType` può essere convertita in un numero utilizzando il metodo [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*). 

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

La trasformazione risultante converte il valore di testo in un numero `VehicleType`. Quando viene applicata la trasformazione, le voci della colonna `VehicleType` diventano le seguenti: 

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a>Usare dati di testo

I dati di testo devono essere trasformati in numeri prima di poter essere usati per creare un modello di Machine Learning. Visitare la pagina [Trasformazioni dati](../resources/transforms.md) per un elenco e una descrizione più dettagliati delle trasformazioni del testo.

Usando dati analoghi ai seguenti caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):

```csharp
ReviewData[] reviews = new ReviewData[]
{
    new ReviewData
    {
        Description="This is a good product",
        Rating=4.7f
    },
    new ReviewData
    {
        Description="This is a bad product",
        Rating=2.3f
    }
};
```

Il passaggio minimo per convertire il testo in un vettore numerico consiste nell'usare il metodo [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*). La trasformazione [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) applica una serie di trasformazioni alla colonna di testo di input restituendo come risultato un vettore numerico che rappresenta la parola a cui è stata applicata lp-norm e gli n-grammi dei caratteri. 

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

La trasformazione risultante convertirebbe i valori di testo nella colonna `Description` in un vettore numerico simile all'output seguente:

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

Combinare i complessi passaggi di elaborazione del testo in una classe [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) per rimuovere il rumore e tentare di ridurre la quantità di risorse necessaria per l'elaborazione.

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

`textEstimator` contiene un sottoinsieme di operazioni eseguite tramite il metodo [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*). Il vantaggio che offre l'uso di una pipeline più complessa è la visibilità e il controllo sulle trasformazioni applicate ai dati. 

Usando la prima voce come esempio, la descrizione dettagliata dei risultati generati dai passaggi di trasformazione definiti da `textEstimator` sarebbe:

**Testo originale: This is a good product**

|Transform | Descrizione | Risultato
|--|--|--|
|1. NormalizeText | Converte tutte le lettere in minuscolo per impostazione predefinita | this is a good product
|2. TokenizeWords | Suddivide la stringa in singole parole | ["this","is","a","good","product"]
|3. RemoveDefaultStopWords | Rimuove le parole non significative, ad esempio *is* e *a*. | ["good","product"]
|4. MapValueToKey | Esegue il mapping dei valori su chiavi (categorie) in base ai dati di input |  [1,2]
|5. ProduceNGrams | Trasforma il testo in una sequenza di parole consecutive | [1,1,1,0,0]
|6. NormalizeLpNorm | Scala gli input in base alla relativa lp-norm | [ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]

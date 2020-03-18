---
title: Preparare i dati per la creazione di un modello
description: Informazioni su come usare le trasformazioni in ML.NET per manipolare e preparare i dati per un'ulteriore elaborazione o creazione di un modello.
author: luisquintanilla
ms.author: luquinta
ms.date: 01/29/2020
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 12f933253af9ea519d711c20227fe075fed003de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "77452987"
---
# <a name="prepare-data-for-building-a-model"></a>Preparare i dati per la creazione di un modello

Informazioni su come usare ML.NET per preparare i dati per un'ulteriore elaborazione o creazione di un modello.

I dati sono spesso sparsi e non puliti. ML.NET algoritmi di apprendimento automatico prevedono che l'input o le funzionalità siano in un unico vettore numerico. Analogamente, il valore da stimare (etichetta), soprattutto quando si tratta di dati categorici, deve essere codificato. Uno degli obiettivi della preparazione dei dati, pertanto, è conferire ai dati il formato previsto dagli algoritmi di ML.NET.

## <a name="filter-data"></a>Filtrare i dati

In alcuni casi, non tutti i dati in un set di dati sono rilevanti per l'analisi. Un modo per rimuovere i dati irrilevanti da un set di dati consiste nell'applicare dei filtri. L'oggetto [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contiene un set di [`IDataView`](xref:Microsoft.ML.IDataView) operazioni di filtro che accettano un contenente tutti i dati e restituiscono un [oggetto IDataView](xref:Microsoft.ML.IDataView) contenente solo i punti dati di interesse. È importante notare che, poiché [`IEstimator`](xref:Microsoft.ML.IEstimator%601) le [`ITransformer`](xref:Microsoft.ML.ITransformer) operazioni filtro [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog)non sono un o [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) simili [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) a quelle in , non possono essere incluse come parte di una pipeline o di preparazione dei dati.

Prendere i seguenti dati di [`IDataView`](xref:Microsoft.ML.IDataView) input `data`e caricarli in un file chiamato:

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

Per filtrare i dati in base [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A) al valore di una colonna, utilizzare il metodo .

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

L'esempio precedente considera le righe del set di dati con un prezzo compreso tra 200000 e 1000000. Il risultato che si otterrebbe applicando questo filtro sarebbe la restituzione solo delle ultime due righe di dati e l'esclusione della prima riga perché il prezzo è 100000 e pertanto non rientra nell'intervallo specificato.

## <a name="replace-missing-values"></a>Sostituire valori mancanti

I valori mancanti sono un evento comune nei set di dati. Un modo per gestire i valori mancanti consiste nel sostituirli con il valore predefinito, qualora esistesse per il tipo specificato, oppure con un altro valore significativo, ad esempio il valore medio dei dati.

Prendere i seguenti dati di [`IDataView`](xref:Microsoft.ML.IDataView) input `data`e caricarli in un file chiamato:

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

Si noti che l'ultimo elemento nell'elenco presenta un valore mancante per `Price`. Per sostituire i valori `Price` mancanti [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) nella colonna, utilizzare il metodo per inserire il valore mancante.

> [!IMPORTANT]
> [`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A)funziona solo con dati numerici.

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

ML.NET supporta varie [modalità sostituzione](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode). Nell'esempio precedente `Mean` viene utilizzata la modalità di sostituzione, che inserisce il valore mancante con il valore medio della colonna. Il risultato della sostituzione completa la proprietà `Price` dell'ultimo elemento di dati con il valore 200.000 perché è la media fra 100.000 e 300.000.

## <a name="use-normalizers"></a>Usare i normalizzatori

[La normalizzazione](https://en.wikipedia.org/wiki/Feature_scaling) è una tecnica di pre-elaborazione dei dati utilizzata per scalare le funzionalità nello stesso intervallo, in genere tra 0 e 1, in modo che possano essere elaborate in modo più accurato da un algoritmo di apprendimento automatico. Ad esempio, le fasce per età e reddito variano in modo significativo con l'età generalmente compresa nell'intervallo di 0-100 e il reddito generalmente è compreso nell'intervallo da zero a migliaia. Visitare la pagina [Trasformazioni dati](../resources/transforms.md) per un elenco e una descrizione più dettagliati delle trasformazioni di normalizzazione.

### <a name="min-max-normalization"></a>Normalizzazione min-max

Prendere i seguenti dati di [`IDataView`](xref:Microsoft.ML.IDataView) input `data`e caricarli in un file chiamato:

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

È possibile applicare la normalizzazione alle colonne con valori numerici singoli, nonché vettori. Normalizzare i dati `Price` nella colonna utilizzando la normalizzazione min-max con il [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) metodo .

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

I valori `[200000,100000]` di prezzo `[ 1, 0.5 ]` originali `MinMax` vengono convertiti utilizzando la formula di normalizzazione che genera valori di output nell'intervallo 0-1.

### <a name="binning"></a>Binning

Il processo di [binning](https://en.wikipedia.org/wiki/Data_binning) converte valori continui in una rappresentazione discreta dell'input. Si supponga, ad esempio, che una delle caratteristiche sia l'età. Invece di usare il valore effettivo dell'età, per tale valore il processo di binning crea intervalli. 0-18 potrebbe essere un intervallo, 19-35 potrebbe essere un altro intervallo e così via.

Prendere i seguenti dati di [`IDataView`](xref:Microsoft.ML.IDataView) input `data`e caricarli in un file chiamato:

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

Normalizzare i dati in [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A) contenitori utilizzando il metodo . Il parametro `maximumBinCount` consente di specificare il numero di contenitori necessari per classificare i dati. In questo esempio i dati verranno inseriti in due contenitori.

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

Uno dei tipi di dati più comuni è la categoria dei dati. I dati categorici hanno un numero finito di categorie. Ad esempio, gli stati degli Stati Uniti, o un elenco dei tipi di animali trovati in una serie di immagini. Se i dati categorici sono caratteristiche o etichette, è necessario mappare su un valore numerico in modo che possano essere usati per generare un modello di apprendimento automatico. Esistono diversi modi per lavorare con i dati categorici in ML.NET, a seconda del problema che si sta risolvendo.

### <a name="key-value-mapping"></a>Mapping del valore della chiaveKey value mapping

In ML.NET, una chiave è un valore intero che rappresenta una categoria. Il mapping dei valori chiave viene spesso usato per eseguire il mapping delle etichette di stringa in valori interi univoci per il training, quindi di nuovo ai relativi valori stringa quando il modello viene usato per eseguire una stima.

Le trasformazioni utilizzate per eseguire il mapping del valore tasto sono [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) e [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).

`MapValueToKey`aggiunge un dizionario di mapping nel `MapKeyToValue` modello, in modo che possa eseguire la trasformazione inversa quando si esegue una stima.

### <a name="one-hot-encoding"></a>Una codifica a caldo

Una codifica a caldo accetta un set finito di valori e `1` li mappa su numeri interi la cui rappresentazione binaria ha un singolo valore in posizioni univoche nella stringa. Una codifica a caldo può essere la scelta migliore se non esiste un ordinamento implicito dei dati categorici. Nella tabella seguente viene illustrato un esempio con i codici postali come valori non elaborati.

|Valore non elaborato|Un valore codificato a caldo|
|---------|---------------------|
|98052|00...01|
|98100|00...10|
|...|...|
|98109|10...00|

La trasformazione per convertire i dati categorici in numeri codificati a un solo caldo è [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).

### <a name="hashing"></a>Hashing

L'hashing è un altro modo per convertire i dati categorici in numeri. Una funzione hash esegue il mapping di dati di dimensioni arbitrarie (una stringa di testo, ad esempio) su un numero con un intervallo fisso. L'hashing può essere un modo rapido ed efficiente in termini di spazio per vettorizzare le funzionalità. Un notevole esempio di hashing nell'apprendimento automatico è il filtro antispam tramite posta elettronica in cui, invece di mantenere un dizionario di parole note, ogni parola nell'e-mail viene sottoposta a hashing e aggiunta a un vettore di funzionalità di grandi dimensioni. L'utilizzo dell'hashing in questo modo consente di evitare il problema dell'elusione del filtro antispam dannoso mediante l'uso di parole non presenti nel dizionario.

ML.NET fornisce la trasformazione [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) per eseguire l'hashing su testo, date e dati numerici. Analogamente al mapping della chiave di valore, gli output della trasformazione hash sono tipi di chiave.

## <a name="work-with-text-data"></a>Usare dati di testo

Analogamente ai dati categorici, i dati di testo devono essere trasformati in funzionalità numeriche prima di utilizzarli per creare un modello di apprendimento automatico. Visitare la pagina [Trasformazioni dati](../resources/transforms.md) per un elenco e una descrizione più dettagliati delle trasformazioni del testo.

Utilizzando dati come i dati sottostanti [`IDataView`](xref:Microsoft.ML.IDataView)che sono stati caricati in un:

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

ML.NET fornisce [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) la trasformazione che accetta il valore stringa di un testo e crea un set di funzionalità dal testo, applicando una serie di singole trasformazioni.

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

La trasformazione risultante converte `Description` i valori di testo nella colonna in un vettore numerico simile all'output seguente:

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

Le trasformazioni che `FeaturizeText` compongono possono essere applicate singolarmente anche per un controllo più preciso del grano sulla generazione delle funzionalità.

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

`textEstimator`contiene un sottoinsieme di [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) operazioni eseguite dal metodo. Il vantaggio che offre l'uso di una pipeline più complessa è la visibilità e il controllo sulle trasformazioni applicate ai dati.

Usando la prima voce come esempio, la descrizione dettagliata dei risultati generati dai passaggi di trasformazione definiti da `textEstimator` sarebbe:

**Testo originale: Questo è un buon prodotto**

|Trasformare | Descrizione | Risultato
|--|--|--|
|1. Normalizza testo | Converte tutte le lettere in minuscolo per impostazione predefinita | this is a good product
|2. TokenizeWords | Suddivide la stringa in singole parole | ["this","is","a","good","product"]
|3. RemoveDefaultStopWords | Rimuove le parole non significative, ad esempio *is* e *a*. | ["good","product"]
|4. MapValueToKey | Esegue il mapping dei valori su chiavi (categorie) in base ai dati di input |  [1,2]
|5. ProdottiNGrammi | Trasforma il testo in una sequenza di parole consecutive | [1,1,1,0,0]
|6. NormalizeLpNorm | Scala gli input in base alla relativa lp-norm | [ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]

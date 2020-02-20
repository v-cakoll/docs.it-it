---
title: Preparare i dati per la creazione di un modello
description: Informazioni su come usare le trasformazioni in ML.NET per manipolare e preparare i dati per un'ulteriore elaborazione o creazione di un modello.
author: luisquintanilla
ms.author: luquinta
ms.date: 01/29/2020
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 12f933253af9ea519d711c20227fe075fed003de
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452987"
---
# <a name="prepare-data-for-building-a-model"></a><span data-ttu-id="6f477-103">Preparare i dati per la creazione di un modello</span><span class="sxs-lookup"><span data-stu-id="6f477-103">Prepare data for building a model</span></span>

<span data-ttu-id="6f477-104">Informazioni su come usare ML.NET per preparare i dati per un'ulteriore elaborazione o creazione di un modello.</span><span class="sxs-lookup"><span data-stu-id="6f477-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="6f477-105">I dati sono spesso sparsi e non puliti.</span><span class="sxs-lookup"><span data-stu-id="6f477-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="6f477-106">Gli algoritmi di Machine Learning ML.NET prevedono che l'input o le funzionalità siano in un singolo vettore numerico.</span><span class="sxs-lookup"><span data-stu-id="6f477-106">ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="6f477-107">Analogamente, il valore da stimare (etichetta), soprattutto quando si tratta di dati categorici, deve essere codificato.</span><span class="sxs-lookup"><span data-stu-id="6f477-107">Similarly, the value to predict (label), especially when it's categorical data, has to be encoded.</span></span> <span data-ttu-id="6f477-108">Uno degli obiettivi della preparazione dei dati, pertanto, è conferire ai dati il formato previsto dagli algoritmi di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="6f477-108">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span>

## <a name="filter-data"></a><span data-ttu-id="6f477-109">Filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="6f477-109">Filter data</span></span>

<span data-ttu-id="6f477-110">In alcuni casi, non tutti i dati in un set di dati sono rilevanti per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="6f477-110">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="6f477-111">Un modo per rimuovere i dati irrilevanti da un set di dati consiste nell'applicare dei filtri.</span><span class="sxs-lookup"><span data-stu-id="6f477-111">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="6f477-112">La classe [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contiene un set di operazioni di filtro che esaminano un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) che contiene tutti i dati e restituiscono un'interfaccia [IDataView](xref:Microsoft.ML.IDataView) contenente solo i punti dati di interesse.</span><span class="sxs-lookup"><span data-stu-id="6f477-112">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="6f477-113">È importante notare che, poiché non sono di tipo [`IEstimator`](xref:Microsoft.ML.IEstimator%601) e neppure [`ITransformer`](xref:Microsoft.ML.ITransformer) come quelle disponibili nella classe [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), le operazioni di filtro non possono essere incluse in una pipeline di preparazione dei dati [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) o [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601).</span><span class="sxs-lookup"><span data-stu-id="6f477-113">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span>

<span data-ttu-id="6f477-114">Prendere i dati di input seguenti e caricarli in un [`IDataView`](xref:Microsoft.ML.IDataView) denominato `data`:</span><span class="sxs-lookup"><span data-stu-id="6f477-114">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="6f477-115">Per filtrare i dati in base al valore di una colonna, usare il metodo [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A).</span><span class="sxs-lookup"><span data-stu-id="6f477-115">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn%2A) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="6f477-116">L'esempio precedente considera le righe del set di dati con un prezzo compreso tra 200000 e 1000000.</span><span class="sxs-lookup"><span data-stu-id="6f477-116">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="6f477-117">Il risultato che si otterrebbe applicando questo filtro sarebbe la restituzione solo delle ultime due righe di dati e l'esclusione della prima riga perché il prezzo è 100000 e pertanto non rientra nell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="6f477-117">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="6f477-118">Sostituisce i valori mancanti</span><span class="sxs-lookup"><span data-stu-id="6f477-118">Replace missing values</span></span>

<span data-ttu-id="6f477-119">I valori mancanti sono un evento comune nei set di dati.</span><span class="sxs-lookup"><span data-stu-id="6f477-119">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="6f477-120">Un modo per gestire i valori mancanti consiste nel sostituirli con il valore predefinito, qualora esistesse per il tipo specificato, oppure con un altro valore significativo, ad esempio il valore medio dei dati.</span><span class="sxs-lookup"><span data-stu-id="6f477-120">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span>

<span data-ttu-id="6f477-121">Prendere i dati di input seguenti e caricarli in un [`IDataView`](xref:Microsoft.ML.IDataView) denominato `data`:</span><span class="sxs-lookup"><span data-stu-id="6f477-121">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="6f477-122">Si noti che l'ultimo elemento nell'elenco presenta un valore mancante per `Price`.</span><span class="sxs-lookup"><span data-stu-id="6f477-122">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="6f477-123">Per sostituire i valori mancanti nella colonna `Price`, inserire valore mancante usando il metodo [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A).</span><span class="sxs-lookup"><span data-stu-id="6f477-123">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f477-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) funziona solo con dati numerici.</span><span class="sxs-lookup"><span data-stu-id="6f477-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues%2A) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="6f477-125">ML.NET supporta varie [modalità sostituzione](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span><span class="sxs-lookup"><span data-stu-id="6f477-125">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="6f477-126">Nell'esempio precedente viene utilizzata la modalità di sostituzione `Mean`, che inserisce il valore mancante nel valore medio della colonna.</span><span class="sxs-lookup"><span data-stu-id="6f477-126">The sample above uses the `Mean` replacement mode, which fills in the missing value with that column's average value.</span></span> <span data-ttu-id="6f477-127">Il risultato della sostituzione completa la proprietà `Price` dell'ultimo elemento di dati con il valore 200.000 perché è la media fra 100.000 e 300.000.</span><span class="sxs-lookup"><span data-stu-id="6f477-127">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span>

## <a name="use-normalizers"></a><span data-ttu-id="6f477-128">Usare i normalizzatori</span><span class="sxs-lookup"><span data-stu-id="6f477-128">Use normalizers</span></span>

<span data-ttu-id="6f477-129">La [normalizzazione](https://en.wikipedia.org/wiki/Feature_scaling) è una tecnica di pre-elaborazione dei dati usata per ridimensionare le funzionalità in modo che si trovino nello stesso intervallo, in genere tra 0 e 1, in modo che possano essere elaborate più accuratamente da un algoritmo di machine learning.</span><span class="sxs-lookup"><span data-stu-id="6f477-129">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to scale features to be in the same range, usually between 0 and 1, so that they can be more accurately processed by a machine learning algorithm.</span></span> <span data-ttu-id="6f477-130">Ad esempio, gli intervalli per Age e Income variano significativamente con Age in genere nell'intervallo di 0-100 e il reddito è generalmente compreso nell'intervallo da zero a migliaia.</span><span class="sxs-lookup"><span data-stu-id="6f477-130">For example, the ranges for age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="6f477-131">Visitare la pagina [Trasformazioni dati](../resources/transforms.md) per un elenco e una descrizione più dettagliati delle trasformazioni di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f477-131">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span>

### <a name="min-max-normalization"></a><span data-ttu-id="6f477-132">Normalizzazione min-max</span><span class="sxs-lookup"><span data-stu-id="6f477-132">Min-Max normalization</span></span>

<span data-ttu-id="6f477-133">Prendere i dati di input seguenti e caricarli in un [`IDataView`](xref:Microsoft.ML.IDataView) denominato `data`:</span><span class="sxs-lookup"><span data-stu-id="6f477-133">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="6f477-134">È possibile applicare la normalizzazione alle colonne con valori numerici singoli, nonché vettori.</span><span class="sxs-lookup"><span data-stu-id="6f477-134">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="6f477-135">Normalizzare i dati nella colonna `Price` usando la normalizzazione min-max con il metodo [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A).</span><span class="sxs-lookup"><span data-stu-id="6f477-135">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax%2A) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="6f477-136">I valori di prezzo originali `[200000,100000]` vengono convertiti in `[ 1, 0.5 ]` utilizzando la formula di normalizzazione `MinMax` che genera i valori di output nell'intervallo 0-1.</span><span class="sxs-lookup"><span data-stu-id="6f477-136">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula that generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="6f477-137">Binning</span><span class="sxs-lookup"><span data-stu-id="6f477-137">Binning</span></span>

<span data-ttu-id="6f477-138">Il processo di [binning](https://en.wikipedia.org/wiki/Data_binning) converte valori continui in una rappresentazione discreta dell'input.</span><span class="sxs-lookup"><span data-stu-id="6f477-138">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="6f477-139">Si supponga, ad esempio, che una delle caratteristiche sia l'età.</span><span class="sxs-lookup"><span data-stu-id="6f477-139">For example, suppose one of your features is age.</span></span> <span data-ttu-id="6f477-140">Invece di usare il valore effettivo dell'età, per tale valore il processo di binning crea intervalli.</span><span class="sxs-lookup"><span data-stu-id="6f477-140">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="6f477-141">0-18 potrebbe essere un intervallo, 19-35 potrebbe essere un altro intervallo e così via.</span><span class="sxs-lookup"><span data-stu-id="6f477-141">0-18 could be one bin, another could be 19-35 and so on.</span></span>

<span data-ttu-id="6f477-142">Prendere i dati di input seguenti e caricarli in un [`IDataView`](xref:Microsoft.ML.IDataView) denominato `data`:</span><span class="sxs-lookup"><span data-stu-id="6f477-142">Take the following input data and load it into an [`IDataView`](xref:Microsoft.ML.IDataView) called `data`:</span></span>

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

<span data-ttu-id="6f477-143">Normalizzare i dati in contenitori usando il metodo [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A).</span><span class="sxs-lookup"><span data-stu-id="6f477-143">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning%2A) method.</span></span> <span data-ttu-id="6f477-144">Il parametro `maximumBinCount` consente di specificare il numero di contenitori necessari per classificare i dati.</span><span class="sxs-lookup"><span data-stu-id="6f477-144">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="6f477-145">In questo esempio i dati verranno inseriti in due contenitori.</span><span class="sxs-lookup"><span data-stu-id="6f477-145">In this example, data will be put into two bins.</span></span>

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="6f477-146">Il risultato del processo di binning è la creazione di limiti per i contenitori di `[0,200000,Infinity]`.</span><span class="sxs-lookup"><span data-stu-id="6f477-146">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="6f477-147">Di conseguenza, i contenitori risultanti sono `[0,1,1]` perché la prima osservazione prende in considerazione i valori tra 0 e 200000 e gli altri sono maggiori di 200000 ma inferiori a infinito.</span><span class="sxs-lookup"><span data-stu-id="6f477-147">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="6f477-148">Usare dati di categorie</span><span class="sxs-lookup"><span data-stu-id="6f477-148">Work with categorical data</span></span>

<span data-ttu-id="6f477-149">Uno dei tipi di dati più comuni è costituito da dati categorici.</span><span class="sxs-lookup"><span data-stu-id="6f477-149">One of the most common types of data is categorical data.</span></span> <span data-ttu-id="6f477-150">I dati categorici hanno un numero finito di categorie.</span><span class="sxs-lookup"><span data-stu-id="6f477-150">Categorical data has a finite number of categories.</span></span> <span data-ttu-id="6f477-151">Ad esempio, gli Stati degli Stati Uniti o un elenco dei tipi di animali trovati in un set di immagini.</span><span class="sxs-lookup"><span data-stu-id="6f477-151">For example, the states of the USA, or a list of the types of animals found in a set of pictures.</span></span> <span data-ttu-id="6f477-152">Se i dati categorici sono features o labels, è necessario eseguirne il mapping a un valore numerico in modo che possano essere usati per generare un modello di machine learning.</span><span class="sxs-lookup"><span data-stu-id="6f477-152">Whether the categorical data are features or labels, they must be mapped onto a numerical value so they can be used to generate a machine learning model.</span></span> <span data-ttu-id="6f477-153">Esistono diversi modi per lavorare con i dati categorici in ML.NET, a seconda del problema che si sta risolvendo.</span><span class="sxs-lookup"><span data-stu-id="6f477-153">There are a number of ways of working with categorical data in ML.NET, depending on the problem you are solving.</span></span>

### <a name="key-value-mapping"></a><span data-ttu-id="6f477-154">Mapping di valori di chiave</span><span class="sxs-lookup"><span data-stu-id="6f477-154">Key value mapping</span></span>

<span data-ttu-id="6f477-155">In ML.NET, una chiave è un valore integer che rappresenta una categoria.</span><span class="sxs-lookup"><span data-stu-id="6f477-155">In ML.NET, a key is an integer value that represents a category.</span></span> <span data-ttu-id="6f477-156">Il mapping di valori di chiave viene spesso utilizzato per eseguire il mapping delle etichette di stringa in valori integer univoci per il training, quindi di nuovo ai valori stringa quando il modello viene utilizzato per eseguire una stima.</span><span class="sxs-lookup"><span data-stu-id="6f477-156">Key value mapping is most often used to map string labels into unique integer values for training, then back to their string values when the model is used to make a prediction.</span></span>

<span data-ttu-id="6f477-157">Le trasformazioni usate per eseguire il mapping di valori di chiave sono [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) e [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).</span><span class="sxs-lookup"><span data-stu-id="6f477-157">The transforms used to perform key value mapping are [MapValueToKey](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) and [MapKeyToValue](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapKeyToValue%2A).</span></span>

<span data-ttu-id="6f477-158">`MapValueToKey` aggiunge un dizionario di mapping nel modello, in modo che `MapKeyToValue` possibile eseguire la trasformazione inversa durante l'esecuzione di una stima.</span><span class="sxs-lookup"><span data-stu-id="6f477-158">`MapValueToKey` adds a dictionary of mappings in the model, so that `MapKeyToValue` can perform the reverse transform when making a prediction.</span></span>

### <a name="one-hot-encoding"></a><span data-ttu-id="6f477-159">Una codifica a caldo</span><span class="sxs-lookup"><span data-stu-id="6f477-159">One hot encoding</span></span>

<span data-ttu-id="6f477-160">Una codifica a caldo accetta un set limitato di valori e ne esegue il mapping su numeri interi la cui rappresentazione binaria ha un singolo valore di `1` in posizioni univoche nella stringa.</span><span class="sxs-lookup"><span data-stu-id="6f477-160">One hot encoding takes a finite set of values and maps them onto integers whose binary representation has a single `1` value in unique positions in the string.</span></span> <span data-ttu-id="6f477-161">Una codifica a caldo può essere la scelta migliore se non è presente alcun ordinamento implicito dei dati categorici.</span><span class="sxs-lookup"><span data-stu-id="6f477-161">One hot encoding can be the best choice if there is no implicit ordering of the categorical data.</span></span> <span data-ttu-id="6f477-162">La tabella seguente mostra un esempio con Cap come valori non elaborati.</span><span class="sxs-lookup"><span data-stu-id="6f477-162">The following table shows an example with zip codes as raw values.</span></span>

|<span data-ttu-id="6f477-163">Valore non elaborato</span><span class="sxs-lookup"><span data-stu-id="6f477-163">Raw value</span></span>|<span data-ttu-id="6f477-164">Un valore codificato a caldo</span><span class="sxs-lookup"><span data-stu-id="6f477-164">One hot encoded value</span></span>|
|---------|---------------------|
|<span data-ttu-id="6f477-165">98052</span><span class="sxs-lookup"><span data-stu-id="6f477-165">98052</span></span>|<span data-ttu-id="6f477-166">00... 01</span><span class="sxs-lookup"><span data-stu-id="6f477-166">00...01</span></span>|
|<span data-ttu-id="6f477-167">98100</span><span class="sxs-lookup"><span data-stu-id="6f477-167">98100</span></span>|<span data-ttu-id="6f477-168">00... 10</span><span class="sxs-lookup"><span data-stu-id="6f477-168">00...10</span></span>|
|<span data-ttu-id="6f477-169">...</span><span class="sxs-lookup"><span data-stu-id="6f477-169">...</span></span>|<span data-ttu-id="6f477-170">...</span><span class="sxs-lookup"><span data-stu-id="6f477-170">...</span></span>|
|<span data-ttu-id="6f477-171">98109</span><span class="sxs-lookup"><span data-stu-id="6f477-171">98109</span></span>|<span data-ttu-id="6f477-172">10... 00</span><span class="sxs-lookup"><span data-stu-id="6f477-172">10...00</span></span>|

<span data-ttu-id="6f477-173">La trasformazione per convertire i dati categorici in numeri con codifica One-Hot è [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).</span><span class="sxs-lookup"><span data-stu-id="6f477-173">The transform to convert categorical data to one-hot encoded numbers is [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding%2A).</span></span>

### <a name="hashing"></a><span data-ttu-id="6f477-174">Hash</span><span class="sxs-lookup"><span data-stu-id="6f477-174">Hashing</span></span>

<span data-ttu-id="6f477-175">L'hashing è un altro modo per convertire i dati categorici in numeri.</span><span class="sxs-lookup"><span data-stu-id="6f477-175">Hashing is another way to convert categorical data to numbers.</span></span> <span data-ttu-id="6f477-176">Una funzione hash esegue il mapping dei dati di una dimensione arbitraria, ad esempio una stringa di testo, su un numero con un intervallo fisso.</span><span class="sxs-lookup"><span data-stu-id="6f477-176">A hash function maps data of an arbitrary size (a string of text for example) onto a number with a fixed range.</span></span> <span data-ttu-id="6f477-177">L'hashing può essere un modo rapido ed efficiente per lo spazio di vettorizzazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6f477-177">Hashing can be a fast and space-efficient way of vectorizing features.</span></span> <span data-ttu-id="6f477-178">Un esempio significativo di hashing in Machine Learning è il filtraggio della posta indesiderata, dove, anziché mantenere un dizionario di parole note, viene eseguito l'hashing di ogni parola del messaggio di posta elettronica e viene aggiunto a un vettore di funzionalità di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="6f477-178">One notable example of hashing in machine learning is email spam filtering where, instead of maintaining a dictionary of known words, every word in the email is hashed and added to a large feature vector.</span></span> <span data-ttu-id="6f477-179">L'uso di hash in questo modo evita il problema dell'elusione dannosa del filtro della posta indesiderata mediante l'uso di parole non presenti nel dizionario.</span><span class="sxs-lookup"><span data-stu-id="6f477-179">Using hashing in this way avoids the problem of malicious spam filtering circumvention by the use of words that are not in the dictionary.</span></span>

<span data-ttu-id="6f477-180">ML.NET fornisce la trasformazione [hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) per eseguire l'hashing su testo, date e dati numerici.</span><span class="sxs-lookup"><span data-stu-id="6f477-180">ML.NET provides [Hash](xref:Microsoft.ML.ConversionsExtensionsCatalog.Hash%2A) transform to perform hashing on text, dates, and numerical data.</span></span> <span data-ttu-id="6f477-181">Analogamente al mapping della chiave del valore, gli output della trasformazione hash sono tipi di chiave.</span><span class="sxs-lookup"><span data-stu-id="6f477-181">Like value key mapping, the outputs of the hash transform are key types.</span></span>

## <a name="work-with-text-data"></a><span data-ttu-id="6f477-182">Usare dati di testo</span><span class="sxs-lookup"><span data-stu-id="6f477-182">Work with text data</span></span>

<span data-ttu-id="6f477-183">Analogamente ai dati categorici, i dati di testo devono essere trasformati in funzionalità numeriche prima di usarli per creare un modello di machine learning.</span><span class="sxs-lookup"><span data-stu-id="6f477-183">Like categorical data, text data needs to be transformed into numerical features before using it to build a machine learning model.</span></span> <span data-ttu-id="6f477-184">Visitare la pagina [Trasformazioni dati](../resources/transforms.md) per un elenco e una descrizione più dettagliati delle trasformazioni del testo.</span><span class="sxs-lookup"><span data-stu-id="6f477-184">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="6f477-185">Usando dati analoghi ai seguenti caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="6f477-185">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="6f477-186">ML.NET fornisce la trasformazione [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) che accetta il valore stringa di un testo e crea un set di funzionalità dal testo, applicando una serie di trasformazioni singole.</span><span class="sxs-lookup"><span data-stu-id="6f477-186">ML.NET provides the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) transform that takes a text's string value and creates a set of features from the text, by applying a series of individual transforms.</span></span>

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="6f477-187">La trasformazione risultante converte i valori di testo nella colonna `Description` in un vettore numerico simile all'output seguente:</span><span class="sxs-lookup"><span data-stu-id="6f477-187">The resulting transform converts the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="6f477-188">Le trasformazioni che costituiscono `FeaturizeText` possono anche essere applicate singolarmente per un controllo più preciso sulla generazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6f477-188">The transforms that make up `FeaturizeText` can also be applied individually for finer grain control over feature generation.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="6f477-189">`textEstimator` contiene un sottoinsieme di operazioni eseguite tramite il metodo [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A).</span><span class="sxs-lookup"><span data-stu-id="6f477-189">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText%2A) method.</span></span> <span data-ttu-id="6f477-190">Il vantaggio che offre l'uso di una pipeline più complessa è la visibilità e il controllo sulle trasformazioni applicate ai dati.</span><span class="sxs-lookup"><span data-stu-id="6f477-190">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span>

<span data-ttu-id="6f477-191">Usando la prima voce come esempio, la descrizione dettagliata dei risultati generati dai passaggi di trasformazione definiti da `textEstimator` sarebbe:</span><span class="sxs-lookup"><span data-stu-id="6f477-191">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="6f477-192">**Testo originale: si tratta di un prodotto valido**</span><span class="sxs-lookup"><span data-stu-id="6f477-192">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="6f477-193">Trasforma</span><span class="sxs-lookup"><span data-stu-id="6f477-193">Transform</span></span> | <span data-ttu-id="6f477-194">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f477-194">Description</span></span> | <span data-ttu-id="6f477-195">Risultato</span><span class="sxs-lookup"><span data-stu-id="6f477-195">Result</span></span>
|--|--|--|
|<span data-ttu-id="6f477-196">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="6f477-196">1. NormalizeText</span></span> | <span data-ttu-id="6f477-197">Converte tutte le lettere in minuscolo per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="6f477-197">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="6f477-198">this is a good product</span><span class="sxs-lookup"><span data-stu-id="6f477-198">this is a good product</span></span>
|<span data-ttu-id="6f477-199">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="6f477-199">2. TokenizeWords</span></span> | <span data-ttu-id="6f477-200">Suddivide la stringa in singole parole</span><span class="sxs-lookup"><span data-stu-id="6f477-200">Splits string into individual words</span></span> | <span data-ttu-id="6f477-201">["this","is","a","good","product"]</span><span class="sxs-lookup"><span data-stu-id="6f477-201">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="6f477-202">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="6f477-202">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="6f477-203">Rimuove le parole non significative, ad esempio *is* e *a*.</span><span class="sxs-lookup"><span data-stu-id="6f477-203">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="6f477-204">["good","product"]</span><span class="sxs-lookup"><span data-stu-id="6f477-204">["good","product"]</span></span>
|<span data-ttu-id="6f477-205">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="6f477-205">4. MapValueToKey</span></span> | <span data-ttu-id="6f477-206">Esegue il mapping dei valori su chiavi (categorie) in base ai dati di input</span><span class="sxs-lookup"><span data-stu-id="6f477-206">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="6f477-207">[1,2]</span><span class="sxs-lookup"><span data-stu-id="6f477-207">[1,2]</span></span>
|<span data-ttu-id="6f477-208">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="6f477-208">5. ProduceNGrams</span></span> | <span data-ttu-id="6f477-209">Trasforma il testo in una sequenza di parole consecutive</span><span class="sxs-lookup"><span data-stu-id="6f477-209">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="6f477-210">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="6f477-210">[1,1,1,0,0]</span></span>
|<span data-ttu-id="6f477-211">6. NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="6f477-211">6. NormalizeLpNorm</span></span> | <span data-ttu-id="6f477-212">Scala gli input in base alla relativa lp-norm</span><span class="sxs-lookup"><span data-stu-id="6f477-212">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="6f477-213">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="6f477-213">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>

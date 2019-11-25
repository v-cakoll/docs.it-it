---
title: Preparare i dati per la creazione di un modello
description: Informazioni su come usare le trasformazioni in ML.NET per manipolare e preparare i dati per un'ulteriore elaborazione o creazione di un modello.
author: luisquintanilla
ms.author: luquinta
ms.date: 09/11/2019
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: e9bfad4724b353b0f3bfc615a40f1d72b80a2cd4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976972"
---
# <a name="prepare-data-for-building-a-model"></a><span data-ttu-id="e14fa-103">Preparare i dati per la creazione di un modello</span><span class="sxs-lookup"><span data-stu-id="e14fa-103">Prepare data for building a model</span></span>

<span data-ttu-id="e14fa-104">Informazioni su come usare ML.NET per preparare i dati per un'ulteriore elaborazione o creazione di un modello.</span><span class="sxs-lookup"><span data-stu-id="e14fa-104">Learn how to use ML.NET to prepare data for additional processing or building a model.</span></span>

<span data-ttu-id="e14fa-105">I dati sono spesso sparsi e non puliti.</span><span class="sxs-lookup"><span data-stu-id="e14fa-105">Data is often unclean and sparse.</span></span> <span data-ttu-id="e14fa-106">Gli algoritmi di Machine Learning ML.NET prevedono che l'input o le funzionalità siano in un singolo vettore numerico.</span><span class="sxs-lookup"><span data-stu-id="e14fa-106">ML.NET machine learning algorithms expect input or features to be in a single numerical vector.</span></span> <span data-ttu-id="e14fa-107">Analogamente, il valore da stimare (etichetta), soprattutto quando si tratta di dati categorici, deve essere codificato.</span><span class="sxs-lookup"><span data-stu-id="e14fa-107">Similarly, the value to predict (label), especially when it's categorical data, has to be encoded.</span></span> <span data-ttu-id="e14fa-108">Uno degli obiettivi della preparazione dei dati, pertanto, è conferire ai dati il formato previsto dagli algoritmi di ML.NET.</span><span class="sxs-lookup"><span data-stu-id="e14fa-108">Therefore one of the goals of data preparation is to get the data into the format expected by ML.NET algorithms.</span></span>

## <a name="filter-data"></a><span data-ttu-id="e14fa-109">Filtrare i dati</span><span class="sxs-lookup"><span data-stu-id="e14fa-109">Filter data</span></span>

<span data-ttu-id="e14fa-110">In alcuni casi, non tutti i dati in un set di dati sono rilevanti per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="e14fa-110">Sometimes, not all data in a dataset is relevant for analysis.</span></span> <span data-ttu-id="e14fa-111">Un modo per rimuovere i dati irrilevanti da un set di dati consiste nell'applicare dei filtri.</span><span class="sxs-lookup"><span data-stu-id="e14fa-111">An approach to remove irrelevant data is filtering.</span></span> <span data-ttu-id="e14fa-112">La classe [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contiene un set di operazioni di filtro che esaminano un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) che contiene tutti i dati e restituiscono un'interfaccia [IDataView](xref:Microsoft.ML.IDataView) contenente solo i punti dati di interesse.</span><span class="sxs-lookup"><span data-stu-id="e14fa-112">The [`DataOperationsCatalog`](xref:Microsoft.ML.DataOperationsCatalog) contains a set of filter operations that take in an [`IDataView`](xref:Microsoft.ML.IDataView) containing all of the data and return an [IDataView](xref:Microsoft.ML.IDataView) containing only the data points of interest.</span></span> <span data-ttu-id="e14fa-113">È importante notare che, poiché non sono di tipo [`IEstimator`](xref:Microsoft.ML.IEstimator%601) e neppure [`ITransformer`](xref:Microsoft.ML.ITransformer) come quelle disponibili nella classe [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), le operazioni di filtro non possono essere incluse in una pipeline di preparazione dei dati [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) o [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601).</span><span class="sxs-lookup"><span data-stu-id="e14fa-113">It's important to note that because filter operations are not an [`IEstimator`](xref:Microsoft.ML.IEstimator%601) or [`ITransformer`](xref:Microsoft.ML.ITransformer) like those in the [`TransformsCatalog`](xref:Microsoft.ML.TransformsCatalog), they cannot be included as part of an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) or [`TransformerChain`](xref:Microsoft.ML.Data.TransformerChain%601) data preparation pipeline.</span></span>

<span data-ttu-id="e14fa-114">Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="e14fa-114">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="e14fa-115">Per filtrare i dati in base al valore di una colonna, usare il metodo [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*).</span><span class="sxs-lookup"><span data-stu-id="e14fa-115">To filter data based on the value of a column, use the [`FilterRowsByColumn`](xref:Microsoft.ML.DataOperationsCatalog.FilterRowsByColumn*) method.</span></span>

```csharp
// Apply filter
IDataView filteredData = mlContext.Data.FilterRowsByColumn(data, "Price", lowerBound: 200000, upperBound: 1000000);
```

<span data-ttu-id="e14fa-116">L'esempio precedente considera le righe del set di dati con un prezzo compreso tra 200000 e 1000000.</span><span class="sxs-lookup"><span data-stu-id="e14fa-116">The sample above takes rows in the dataset with a price between 200000 and 1000000.</span></span> <span data-ttu-id="e14fa-117">Il risultato che si otterrebbe applicando questo filtro sarebbe la restituzione solo delle ultime due righe di dati e l'esclusione della prima riga perché il prezzo è 100000 e pertanto non rientra nell'intervallo specificato.</span><span class="sxs-lookup"><span data-stu-id="e14fa-117">The result of applying this filter would return only the last two rows in the data and exclude the first row because its price is 100000 and not between the specified range.</span></span>

## <a name="replace-missing-values"></a><span data-ttu-id="e14fa-118">Sostituire valori mancanti</span><span class="sxs-lookup"><span data-stu-id="e14fa-118">Replace missing values</span></span>

<span data-ttu-id="e14fa-119">I valori mancanti sono un evento comune nei set di dati.</span><span class="sxs-lookup"><span data-stu-id="e14fa-119">Missing values are a common occurrence in datasets.</span></span> <span data-ttu-id="e14fa-120">Un modo per gestire i valori mancanti consiste nel sostituirli con il valore predefinito, qualora esistesse per il tipo specificato, oppure con un altro valore significativo, ad esempio il valore medio dei dati.</span><span class="sxs-lookup"><span data-stu-id="e14fa-120">One approach to dealing with missing values is to replace them with the default value for the given type if any or another meaningful value such as the mean value in the data.</span></span>

<span data-ttu-id="e14fa-121">Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="e14fa-121">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="e14fa-122">Si noti che l'ultimo elemento nell'elenco presenta un valore mancante per `Price`.</span><span class="sxs-lookup"><span data-stu-id="e14fa-122">Notice that the last element in our list has a missing value for `Price`.</span></span> <span data-ttu-id="e14fa-123">Per sostituire i valori mancanti nella colonna `Price`, inserire valore mancante usando il metodo [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*).</span><span class="sxs-lookup"><span data-stu-id="e14fa-123">To replace the missing values in the `Price` column, use the [`ReplaceMissingValues`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) method to fill in that missing value.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e14fa-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) funziona solo con dati numerici.</span><span class="sxs-lookup"><span data-stu-id="e14fa-124">[`ReplaceMissingValue`](xref:Microsoft.ML.ExtensionsCatalog.ReplaceMissingValues*) only works with numerical data.</span></span>

```csharp
// Define replacement estimator
var replacementEstimator = mlContext.Transforms.ReplaceMissingValues("Price", replacementMode: MissingValueReplacingEstimator.ReplacementMode.Mean);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer replacementTransformer = replacementEstimator.Fit(data);

// Transform data
IDataView transformedData = replacementTransformer.Transform(data);
```

<span data-ttu-id="e14fa-125">ML.NET supporta varie [modalità sostituzione](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span><span class="sxs-lookup"><span data-stu-id="e14fa-125">ML.NET supports various [replacement modes](xref:Microsoft.ML.Transforms.MissingValueReplacingEstimator.ReplacementMode).</span></span> <span data-ttu-id="e14fa-126">L'esempio precedente usa la modalità sostituzione `Mean` che inserirà il valore medio della colonna per sopperire al valore mancante.</span><span class="sxs-lookup"><span data-stu-id="e14fa-126">The sample above uses the `Mean` replacement mode which will fill in the missing value with that column's average value.</span></span> <span data-ttu-id="e14fa-127">Il risultato della sostituzione completa la proprietà `Price` dell'ultimo elemento di dati con il valore 200.000 perché è la media fra 100.000 e 300.000.</span><span class="sxs-lookup"><span data-stu-id="e14fa-127">The replacement 's result fills in the `Price` property for the last element in our data with 200,000 since it's the average of 100,000 and 300,000.</span></span>

## <a name="use-normalizers"></a><span data-ttu-id="e14fa-128">Usare i normalizzatori</span><span class="sxs-lookup"><span data-stu-id="e14fa-128">Use normalizers</span></span>

<span data-ttu-id="e14fa-129">La [normalizzazione](https://en.wikipedia.org/wiki/Feature_scaling) è una tecnica usata nella pre-elaborazione dei dati per standardizzare le caratteristiche che non condividono la stessa scala e, pertanto, aiutare gli algoritmi a convergere più velocemente.</span><span class="sxs-lookup"><span data-stu-id="e14fa-129">[Normalization](https://en.wikipedia.org/wiki/Feature_scaling) is a data pre-processing technique used to standardize features that are not on the same scale which helps algorithms converge faster.</span></span> <span data-ttu-id="e14fa-130">Gli intervalli di valori di età e reddito, ad esempio, variano in modo significativo perché l'età è generalmente compresa nell'intervallo da 0 a 100 e il reddito nell'intervallo da 0 a diverse migliaia.</span><span class="sxs-lookup"><span data-stu-id="e14fa-130">For example, the ranges for values like age and income vary significantly with age generally being in the range of 0-100 and income generally being in the range of zero to thousands.</span></span> <span data-ttu-id="e14fa-131">Visitare la pagina [Trasformazioni dati](../resources/transforms.md) per un elenco e una descrizione più dettagliati delle trasformazioni di normalizzazione.</span><span class="sxs-lookup"><span data-stu-id="e14fa-131">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of normalization transforms.</span></span>

### <a name="min-max-normalization"></a><span data-ttu-id="e14fa-132">Normalizzazione min-max</span><span class="sxs-lookup"><span data-stu-id="e14fa-132">Min-Max normalization</span></span>

<span data-ttu-id="e14fa-133">Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="e14fa-133">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="e14fa-134">È possibile applicare la normalizzazione alle colonne con valori numerici singoli, nonché vettori.</span><span class="sxs-lookup"><span data-stu-id="e14fa-134">Normalization can be applied to columns with single numerical values as well as vectors.</span></span> <span data-ttu-id="e14fa-135">Normalizzare i dati nella colonna `Price` usando la normalizzazione min-max con il metodo [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*).</span><span class="sxs-lookup"><span data-stu-id="e14fa-135">Normalize the data in the `Price` column using min-max normalization with the [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) method.</span></span>

```csharp
// Define min-max estimator
var minMaxEstimator = mlContext.Transforms.NormalizeMinMax("Price");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer minMaxTransformer = minMaxEstimator.Fit(data);

// Transform data
IDataView transformedData = minMaxTransformer.Transform(data);
```

<span data-ttu-id="e14fa-136">I valori di prezzo originali `[200000,100000]` vengono convertiti in `[ 1, 0.5 ]` usando la formula di normalizzazione `MinMax` che genera valori di output nell'intervallo 0-1.</span><span class="sxs-lookup"><span data-stu-id="e14fa-136">The original price values `[200000,100000]` are converted to `[ 1, 0.5 ]` using the `MinMax` normalization formula which generates output values in the range of 0-1.</span></span>

### <a name="binning"></a><span data-ttu-id="e14fa-137">Binning</span><span class="sxs-lookup"><span data-stu-id="e14fa-137">Binning</span></span>

<span data-ttu-id="e14fa-138">Il processo di [binning](https://en.wikipedia.org/wiki/Data_binning) converte valori continui in una rappresentazione discreta dell'input.</span><span class="sxs-lookup"><span data-stu-id="e14fa-138">[Binning](https://en.wikipedia.org/wiki/Data_binning) converts continuous values into a discrete representation of the input.</span></span> <span data-ttu-id="e14fa-139">Si supponga, ad esempio, che una delle caratteristiche sia l'età.</span><span class="sxs-lookup"><span data-stu-id="e14fa-139">For example, suppose one of your features is age.</span></span> <span data-ttu-id="e14fa-140">Invece di usare il valore effettivo dell'età, per tale valore il processo di binning crea intervalli.</span><span class="sxs-lookup"><span data-stu-id="e14fa-140">Instead of using the actual age value,  binning creates ranges for that value.</span></span> <span data-ttu-id="e14fa-141">0-18 potrebbe essere un intervallo, 19-35 potrebbe essere un altro intervallo e così via.</span><span class="sxs-lookup"><span data-stu-id="e14fa-141">0-18 could be one bin, another could be 19-35 and so on.</span></span>

<span data-ttu-id="e14fa-142">Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="e14fa-142">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="e14fa-143">Normalizzare i dati in contenitori usando il metodo [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*).</span><span class="sxs-lookup"><span data-stu-id="e14fa-143">Normalize the data into bins using the [`NormalizeBinning`](xref:Microsoft.ML.NormalizationCatalog.NormalizeBinning*) method.</span></span> <span data-ttu-id="e14fa-144">Il parametro `maximumBinCount` consente di specificare il numero di contenitori necessari per classificare i dati.</span><span class="sxs-lookup"><span data-stu-id="e14fa-144">The `maximumBinCount` parameter enables you to specify the number of bins needed to classify your data.</span></span> <span data-ttu-id="e14fa-145">In questo esempio i dati verranno inseriti in due contenitori.</span><span class="sxs-lookup"><span data-stu-id="e14fa-145">In this example, data will be put into two bins.</span></span>

```csharp
// Define binning estimator
var binningEstimator = mlContext.Transforms.NormalizeBinning("Price", maximumBinCount: 2);

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
var binningTransformer = binningEstimator.Fit(data);

// Transform Data
IDataView transformedData = binningTransformer.Transform(data);
```

<span data-ttu-id="e14fa-146">Il risultato del processo di binning è la creazione di limiti per i contenitori di `[0,200000,Infinity]`.</span><span class="sxs-lookup"><span data-stu-id="e14fa-146">The result of binning creates bin bounds of `[0,200000,Infinity]`.</span></span> <span data-ttu-id="e14fa-147">Di conseguenza, i contenitori risultanti sono `[0,1,1]` perché la prima osservazione prende in considerazione i valori tra 0 e 200000 e gli altri sono maggiori di 200000 ma inferiori a infinito.</span><span class="sxs-lookup"><span data-stu-id="e14fa-147">Therefore the resulting bins are `[0,1,1]` because the first observation is between 0-200000 and the others are greater than 200000 but less than infinity.</span></span>

## <a name="work-with-categorical-data"></a><span data-ttu-id="e14fa-148">Usare dati di categorie</span><span class="sxs-lookup"><span data-stu-id="e14fa-148">Work with categorical data</span></span>

<span data-ttu-id="e14fa-149">I dati di categorie non numerici devono essere convertiti in numeri prima di poter essere usati per creare un modello di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="e14fa-149">Non-numeric categorical data needs to be converted to a number before being used to build a machine learning model.</span></span>

<span data-ttu-id="e14fa-150">Usando i dati di input seguenti che vengono caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="e14fa-150">Using the following input data which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="e14fa-151">La proprietà di categoria `VehicleType` può essere convertita in un numero utilizzando il metodo [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*).</span><span class="sxs-lookup"><span data-stu-id="e14fa-151">The categorical `VehicleType` property can be converted into a number using the [`OneHotEncoding`](xref:Microsoft.ML.CategoricalCatalog.OneHotEncoding*) method.</span></span>

```csharp
// Define categorical transform estimator
var categoricalEstimator = mlContext.Transforms.Categorical.OneHotEncoding("VehicleType");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer categoricalTransformer = categoricalEstimator.Fit(data);

// Transform Data
IDataView transformedData = categoricalTransformer.Transform(data);
```

<span data-ttu-id="e14fa-152">La trasformazione risultante converte il valore di testo in un numero `VehicleType`.</span><span class="sxs-lookup"><span data-stu-id="e14fa-152">The resulting transform converts the text value of `VehicleType` to a number.</span></span> <span data-ttu-id="e14fa-153">Quando viene applicata la trasformazione, le voci della colonna `VehicleType` diventano le seguenti:</span><span class="sxs-lookup"><span data-stu-id="e14fa-153">The entries in the `VehicleType` column become the following when the transform is applied:</span></span>

```text
[
    1, // SUV
    2, // Sedan
    1 // SUV
]
```

## <a name="work-with-text-data"></a><span data-ttu-id="e14fa-154">Usare dati di testo</span><span class="sxs-lookup"><span data-stu-id="e14fa-154">Work with text data</span></span>

<span data-ttu-id="e14fa-155">I dati di testo devono essere trasformati in numeri prima di poter essere usati per creare un modello di Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="e14fa-155">Text data needs to be transformed into numbers before using it to build a machine learning model.</span></span> <span data-ttu-id="e14fa-156">Visitare la pagina [Trasformazioni dati](../resources/transforms.md) per un elenco e una descrizione più dettagliati delle trasformazioni del testo.</span><span class="sxs-lookup"><span data-stu-id="e14fa-156">Visit the [transforms page](../resources/transforms.md) for a more detailed list and description of text transforms.</span></span>

<span data-ttu-id="e14fa-157">Usando dati analoghi ai seguenti caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView):</span><span class="sxs-lookup"><span data-stu-id="e14fa-157">Using data like the data below that has been loaded into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

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

<span data-ttu-id="e14fa-158">Il passaggio minimo per convertire il testo in un vettore numerico consiste nell'usare il metodo [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*).</span><span class="sxs-lookup"><span data-stu-id="e14fa-158">The minimum step to convert text to a numerical vector representation is to use the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="e14fa-159">La trasformazione [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) applica una serie di trasformazioni alla colonna di testo di input restituendo come risultato un vettore numerico che rappresenta la parola a cui è stata applicata lp-norm e gli n-grammi dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="e14fa-159">By using the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) transform, a series of transformations is applied to the input text column resulting in a numerical vector representing the lp-normalized word and character ngrams.</span></span>

```csharp
// Define text transform estimator
var textEstimator  = mlContext.Transforms.Text.FeaturizeText("Description");

// Fit data to estimator
// Fitting generates a transformer that applies the operations of defined by estimator
ITransformer textTransformer = textEstimator.Fit(data);

// Transform data
IDataView transformedData = textTransformer.Transform(data);
```

<span data-ttu-id="e14fa-160">La trasformazione risultante convertirebbe i valori di testo nella colonna `Description` in un vettore numerico simile all'output seguente:</span><span class="sxs-lookup"><span data-stu-id="e14fa-160">The resulting transform would convert the text values in the `Description` column to a numerical vector that looks similar to the output below:</span></span>

```text
[ 0.2041241, 0.2041241, 0.2041241, 0.4082483, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0.2041241, 0, 0, 0, 0, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0.4472136, 0 ]
```

<span data-ttu-id="e14fa-161">Combinare i complessi passaggi di elaborazione del testo in una classe [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) per rimuovere il rumore e tentare di ridurre la quantità di risorse necessaria per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="e14fa-161">Combine complex text processing steps into an [`EstimatorChain`](xref:Microsoft.ML.Data.EstimatorChain%601) to remove noise and potentially reduce the amount of required processing resources as needed.</span></span>

```csharp
// Define text transform estimator
var textEstimator = mlContext.Transforms.Text.NormalizeText("Description")
    .Append(mlContext.Transforms.Text.TokenizeIntoWords("Description"))
    .Append(mlContext.Transforms.Text.RemoveDefaultStopWords("Description"))
    .Append(mlContext.Transforms.Conversion.MapValueToKey("Description"))
    .Append(mlContext.Transforms.Text.ProduceNgrams("Description"))
    .Append(mlContext.Transforms.NormalizeLpNorm("Description"));
```

<span data-ttu-id="e14fa-162">`textEstimator` contiene un sottoinsieme di operazioni eseguite tramite il metodo [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*).</span><span class="sxs-lookup"><span data-stu-id="e14fa-162">`textEstimator` contains a subset of operations performed by the [`FeaturizeText`](xref:Microsoft.ML.TextCatalog.FeaturizeText*) method.</span></span> <span data-ttu-id="e14fa-163">Il vantaggio che offre l'uso di una pipeline più complessa è la visibilità e il controllo sulle trasformazioni applicate ai dati.</span><span class="sxs-lookup"><span data-stu-id="e14fa-163">The benefit of a more complex pipeline is control and visibility over the transformations applied to the data.</span></span>

<span data-ttu-id="e14fa-164">Usando la prima voce come esempio, la descrizione dettagliata dei risultati generati dai passaggi di trasformazione definiti da `textEstimator` sarebbe:</span><span class="sxs-lookup"><span data-stu-id="e14fa-164">Using the first entry as an example, the following is a detailed description of the results produced by the transformation steps defined by `textEstimator`:</span></span>

<span data-ttu-id="e14fa-165">**Testo originale: si tratta di un prodotto valido**</span><span class="sxs-lookup"><span data-stu-id="e14fa-165">**Original Text: This is a good product**</span></span>

|<span data-ttu-id="e14fa-166">Transform</span><span class="sxs-lookup"><span data-stu-id="e14fa-166">Transform</span></span> | <span data-ttu-id="e14fa-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e14fa-167">Description</span></span> | <span data-ttu-id="e14fa-168">Risultato</span><span class="sxs-lookup"><span data-stu-id="e14fa-168">Result</span></span>
|--|--|--|
|<span data-ttu-id="e14fa-169">1. NormalizeText</span><span class="sxs-lookup"><span data-stu-id="e14fa-169">1. NormalizeText</span></span> | <span data-ttu-id="e14fa-170">Converte tutte le lettere in minuscolo per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="e14fa-170">Converts all letters to lowercase by default</span></span> | <span data-ttu-id="e14fa-171">this is a good product</span><span class="sxs-lookup"><span data-stu-id="e14fa-171">this is a good product</span></span>
|<span data-ttu-id="e14fa-172">2. TokenizeWords</span><span class="sxs-lookup"><span data-stu-id="e14fa-172">2. TokenizeWords</span></span> | <span data-ttu-id="e14fa-173">Suddivide la stringa in singole parole</span><span class="sxs-lookup"><span data-stu-id="e14fa-173">Splits string into individual words</span></span> | <span data-ttu-id="e14fa-174">["this","is","a","good","product"]</span><span class="sxs-lookup"><span data-stu-id="e14fa-174">["this","is","a","good","product"]</span></span>
|<span data-ttu-id="e14fa-175">3. RemoveDefaultStopWords</span><span class="sxs-lookup"><span data-stu-id="e14fa-175">3. RemoveDefaultStopWords</span></span> | <span data-ttu-id="e14fa-176">Rimuove le parole non significative, ad esempio *is* e *a*.</span><span class="sxs-lookup"><span data-stu-id="e14fa-176">Removes stopwords like *is* and *a*.</span></span> | <span data-ttu-id="e14fa-177">["good","product"]</span><span class="sxs-lookup"><span data-stu-id="e14fa-177">["good","product"]</span></span>
|<span data-ttu-id="e14fa-178">4. MapValueToKey</span><span class="sxs-lookup"><span data-stu-id="e14fa-178">4. MapValueToKey</span></span> | <span data-ttu-id="e14fa-179">Esegue il mapping dei valori su chiavi (categorie) in base ai dati di input</span><span class="sxs-lookup"><span data-stu-id="e14fa-179">Maps the values to keys (categories) based on the input data</span></span> |  <span data-ttu-id="e14fa-180">[1,2]</span><span class="sxs-lookup"><span data-stu-id="e14fa-180">[1,2]</span></span>
|<span data-ttu-id="e14fa-181">5. ProduceNGrams</span><span class="sxs-lookup"><span data-stu-id="e14fa-181">5. ProduceNGrams</span></span> | <span data-ttu-id="e14fa-182">Trasforma il testo in una sequenza di parole consecutive</span><span class="sxs-lookup"><span data-stu-id="e14fa-182">Transforms text into sequence of consecutive words</span></span> | <span data-ttu-id="e14fa-183">[1,1,1,0,0]</span><span class="sxs-lookup"><span data-stu-id="e14fa-183">[1,1,1,0,0]</span></span>
|<span data-ttu-id="e14fa-184">6. NormalizeLpNorm</span><span class="sxs-lookup"><span data-stu-id="e14fa-184">6. NormalizeLpNorm</span></span> | <span data-ttu-id="e14fa-185">Scala gli input in base alla relativa lp-norm</span><span class="sxs-lookup"><span data-stu-id="e14fa-185">Scale inputs by their lp-norm</span></span> | <span data-ttu-id="e14fa-186">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span><span class="sxs-lookup"><span data-stu-id="e14fa-186">[ 0.577350529, 0.577350529, 0.577350529, 0, 0 ]</span></span>

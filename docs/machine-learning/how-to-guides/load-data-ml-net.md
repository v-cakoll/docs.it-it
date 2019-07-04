---
title: Caricare i dati da file e altre origini
description: Questa procedura illustra come caricare i dati per l'elaborazione e il training in ML.NET. I dati vengono inizialmente archiviati nei file o in altre origini dati, ad esempio database, JSON, XML o raccolte in memoria.
ms.date: 06/25/2019
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: fafbe3fed9e3f0b509eda4f9d8967965bde19767
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397740"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="db5ce-104">Caricare i dati da file e altre origini</span><span class="sxs-lookup"><span data-stu-id="db5ce-104">Load data from files and other sources</span></span>

<span data-ttu-id="db5ce-105">Questa procedura illustra come caricare i dati per l'elaborazione e il training in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="db5ce-105">This how-to shows you how to load data for processing and training into ML.NET.</span></span> <span data-ttu-id="db5ce-106">I dati vengono inizialmente archiviati nei file o in altre origini dati, ad esempio database, JSON, XML o raccolte in memoria.</span><span class="sxs-lookup"><span data-stu-id="db5ce-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="db5ce-107">Creare il modello di dati</span><span class="sxs-lookup"><span data-stu-id="db5ce-107">Create the data model</span></span>

<span data-ttu-id="db5ce-108">ML.NET consente di definire modelli di dati tramite le classi.</span><span class="sxs-lookup"><span data-stu-id="db5ce-108">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="db5ce-109">Si considerino, ad esempio, i dati di input seguenti:</span><span class="sxs-lookup"><span data-stu-id="db5ce-109">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="db5ce-110">Creare un modello di dati che rappresenti il frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="db5ce-110">Create a data model that represents the snippet below:</span></span>

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }
 
    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="db5ce-111">Annotazione del modello di dati con gli attributi di colonna</span><span class="sxs-lookup"><span data-stu-id="db5ce-111">Annotating the data model with column attributes</span></span>

<span data-ttu-id="db5ce-112">Gli attributi comunicano a ML.NET più informazioni sul modello di data e l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="db5ce-112">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="db5ce-113">L'attributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) specifica gli indici colonna delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="db5ce-113">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db5ce-114">L'attributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) è necessario solo per caricare dati da un file.</span><span class="sxs-lookup"><span data-stu-id="db5ce-114">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="db5ce-115">Caricare le colonne come:</span><span class="sxs-lookup"><span data-stu-id="db5ce-115">Load columns as:</span></span> 
- <span data-ttu-id="db5ce-116">Colonne singole come `Size` e `CurrentPrices` nella classe `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="db5ce-116">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="db5ce-117">Più colonne contemporaneamente sotto forma di vettore come `HistoricalPrices` nella classe `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="db5ce-117">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="db5ce-118">Se si dispone di una proprietà Vector, applicare l'attributo [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) alla proprietà nel modello di dati.</span><span class="sxs-lookup"><span data-stu-id="db5ce-118">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="db5ce-119">È importante sottolineare che tutti gli elementi del vettore devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="db5ce-119">It's important to note that all of the elements in the vector need to be the same type.</span></span>

<span data-ttu-id="db5ce-120">ML.NET opera attraverso i nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="db5ce-120">ML.NET Operates through column names.</span></span> <span data-ttu-id="db5ce-121">Se si desidera modificare il nome di una colonna cambiandolo rispetto al nome della proprietà, usare l'attributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="db5ce-121">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="db5ce-122">Quando si creano oggetti in memoria, è ancora necessario usare il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="db5ce-122">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="db5ce-123">Tuttavia, per l'elaborazione dei dati e la creazione di modelli di Machine Learning, ML.NET esegue l'override e fa riferimento alla proprietà con il valore fornito nell'attributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).</span><span class="sxs-lookup"><span data-stu-id="db5ce-123">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="db5ce-124">Caricare i dati da un unico file</span><span class="sxs-lookup"><span data-stu-id="db5ce-124">Load data from a single file</span></span>

<span data-ttu-id="db5ce-125">Per caricare i dati da un file, usare il metodo [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) insieme al modello per i dati da caricare.</span><span class="sxs-lookup"><span data-stu-id="db5ce-125">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="db5ce-126">Poiché il parametro `separatorChar` è delimitato da tabulazioni per impostazione predefinita, modificarlo per il file di dati in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="db5ce-126">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="db5ce-127">Se il file presenta un'intestazione, impostare il parametro `hasHeader` su `true` per ignorare la prima riga del file e iniziare a caricare i dati dalla seconda riga.</span><span class="sxs-lookup"><span data-stu-id="db5ce-127">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="db5ce-128">Caricare i dati da più file</span><span class="sxs-lookup"><span data-stu-id="db5ce-128">Load data from multiple files</span></span>

<span data-ttu-id="db5ce-129">Nel caso in cui i dati siano archiviati in più file, e a condizione che lo schema dei dati sia lo stesso, ML.NET consente di caricare i dati da più file in una stessa directory o in directory diverse.</span><span class="sxs-lookup"><span data-stu-id="db5ce-129">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="db5ce-130">Caricare da file in una singola directory</span><span class="sxs-lookup"><span data-stu-id="db5ce-130">Load from files in a single directory</span></span>

<span data-ttu-id="db5ce-131">Quando tutti i file di dati sono nella stessa directory, usare i caratteri jolly nel metodo [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*).</span><span class="sxs-lookup"><span data-stu-id="db5ce-131">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="db5ce-132">Caricare da file in più directory</span><span class="sxs-lookup"><span data-stu-id="db5ce-132">Load from files in multiple directories</span></span>

<span data-ttu-id="db5ce-133">Per caricare i dati da più directory, usare il metodo [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) per creare un elemento [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span><span class="sxs-lookup"><span data-stu-id="db5ce-133">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="db5ce-134">Quindi, usare il metodo [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) per specificare i percorsi dei singoli file. Non è possibile usare caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="db5ce-134">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="db5ce-135">Caricare i dati da altre origini</span><span class="sxs-lookup"><span data-stu-id="db5ce-135">Load data from other sources</span></span>

<span data-ttu-id="db5ce-136">Oltre a caricare i dati archiviati nei file, ML.NET permette di caricare i dati da altre origini tra cui:</span><span class="sxs-lookup"><span data-stu-id="db5ce-136">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="db5ce-137">Raccolte in memoria</span><span class="sxs-lookup"><span data-stu-id="db5ce-137">In-memory collections</span></span>
- <span data-ttu-id="db5ce-138">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="db5ce-138">JSON/XML</span></span>
- <span data-ttu-id="db5ce-139">Database</span><span class="sxs-lookup"><span data-stu-id="db5ce-139">Databases</span></span>

<span data-ttu-id="db5ce-140">Si noti che quando si usano origini di streaming, ML.NET prevede input in forma di raccolta in memoria.</span><span class="sxs-lookup"><span data-stu-id="db5ce-140">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="db5ce-141">Pertanto, quando si usano origini come JSON/XML, assicurarsi di formattare i dati come una raccolta in memoria.</span><span class="sxs-lookup"><span data-stu-id="db5ce-141">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="db5ce-142">Considerando la raccolta in memoria seguente:</span><span class="sxs-lookup"><span data-stu-id="db5ce-142">Given the following in-memory collection:</span></span>

```csharp
HousingData[] inMemoryCollection = new HousingData[]
{
    new HousingData
    {
        Size =700f,
        HistoricalPrices = new float[]
        {
            100000f, 3000000f, 250000f
        },
        CurrentPrice = 500000f
    },
    new HousingData
    {
        Size =1000f,
        HistoricalPrices = new float[]
        {
            600000f, 400000f, 650000f
        },
        CurrentPrice=700000f
    }
};
```

<span data-ttu-id="db5ce-143">Caricare la raccolta in memoria in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) con il metodo [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):</span><span class="sxs-lookup"><span data-stu-id="db5ce-143">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

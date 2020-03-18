---
title: Caricare i dati da file e altre origini
description: Informazioni su come caricare i dati per l'elaborazione e il training in ML.NET usando l'API. I dati vengono archiviati in file, database, JSON, XML o raccolte in memoria.
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 83aaae2d2e75b3076841750bf5d505390a538bc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74344751"
---
# <a name="load-data-from-files-and-other-sources"></a><span data-ttu-id="c50bc-104">Caricare i dati da file e altre origini</span><span class="sxs-lookup"><span data-stu-id="c50bc-104">Load data from files and other sources</span></span>

<span data-ttu-id="c50bc-105">Informazioni su come caricare i dati per l'elaborazione e il training in ML.NET usando l'API.</span><span class="sxs-lookup"><span data-stu-id="c50bc-105">Learn how to load data for processing and training into ML.NET using the API.</span></span> <span data-ttu-id="c50bc-106">I dati vengono inizialmente archiviati nei file o in altre origini dati, ad esempio database, JSON, XML o raccolte in memoria.</span><span class="sxs-lookup"><span data-stu-id="c50bc-106">The data is originally stored in files or other data sources such as databases, JSON, XML or in-memory collections.</span></span>

<span data-ttu-id="c50bc-107">Se si usa Model Builder, vedere Caricare i dati di [training in Model Builder](load-data-model-builder.md).</span><span class="sxs-lookup"><span data-stu-id="c50bc-107">If you're using Model Builder, see [Load training data into Model Builder](load-data-model-builder.md).</span></span>

## <a name="create-the-data-model"></a><span data-ttu-id="c50bc-108">Creare il modello di dati</span><span class="sxs-lookup"><span data-stu-id="c50bc-108">Create the data model</span></span>

<span data-ttu-id="c50bc-109">ML.NET consente di definire modelli di dati tramite le classi.</span><span class="sxs-lookup"><span data-stu-id="c50bc-109">ML.NET enables you to define data models via classes.</span></span> <span data-ttu-id="c50bc-110">Si considerino, ad esempio, i dati di input seguenti:</span><span class="sxs-lookup"><span data-stu-id="c50bc-110">For example, given the following input data:</span></span>

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

<span data-ttu-id="c50bc-111">Creare un modello di dati che rappresenti il frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="c50bc-111">Create a data model that represents the snippet below:</span></span>

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

### <a name="annotating-the-data-model-with-column-attributes"></a><span data-ttu-id="c50bc-112">Annotazione del modello di dati con gli attributi di colonna</span><span class="sxs-lookup"><span data-stu-id="c50bc-112">Annotating the data model with column attributes</span></span>

<span data-ttu-id="c50bc-113">Gli attributi comunicano a ML.NET più informazioni sul modello di data e l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c50bc-113">Attributes give ML.NET more information about the data model and the data source.</span></span>

<span data-ttu-id="c50bc-114">L'attributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) specifica gli indici di colonna delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="c50bc-114">The [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute specifies your properties' column indices.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c50bc-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)è necessario solo durante il caricamento dei dati da un file.</span><span class="sxs-lookup"><span data-stu-id="c50bc-115">[`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) is only required when loading data from a file.</span></span>

<span data-ttu-id="c50bc-116">Caricare le colonne come:</span><span class="sxs-lookup"><span data-stu-id="c50bc-116">Load columns as:</span></span>

- <span data-ttu-id="c50bc-117">Colonne singole come `Size` e `CurrentPrices` nella classe `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="c50bc-117">Individual columns like `Size` and `CurrentPrices` in the `HousingData` class.</span></span>
- <span data-ttu-id="c50bc-118">Più colonne contemporaneamente sotto forma di vettore come `HistoricalPrices` nella classe `HousingData`.</span><span class="sxs-lookup"><span data-stu-id="c50bc-118">Multiple columns at a time in the form of a vector like `HistoricalPrices` in the `HousingData` class.</span></span>

<span data-ttu-id="c50bc-119">Se si dispone di una [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) proprietà vector, applicare l'attributo alla proprietà nel modello di dati.</span><span class="sxs-lookup"><span data-stu-id="c50bc-119">If you have a vector property, apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to the property in your data model.</span></span> <span data-ttu-id="c50bc-120">È importante sottolineare che tutti gli elementi del vettore devono essere dello stesso tipo.</span><span class="sxs-lookup"><span data-stu-id="c50bc-120">It's important to note that all of the elements in the vector need to be the same type.</span></span> <span data-ttu-id="c50bc-121">Mantenere separate le colonne offre vantaggi in termini di semplicità e flessibilità di progettazione delle funzionalità, ma per un elevato numero di colonne, il funzionamento delle singole colonne influisce sulla velocità di training.</span><span class="sxs-lookup"><span data-stu-id="c50bc-121">Keeping the columns separated allows for ease and flexibility of feature engineering, but for a very large number of columns, operating on the individual columns causes an impact on training speed.</span></span>

<span data-ttu-id="c50bc-122">ML.NET opera attraverso i nomi di colonna.</span><span class="sxs-lookup"><span data-stu-id="c50bc-122">ML.NET Operates through column names.</span></span> <span data-ttu-id="c50bc-123">Se si desidera modificare il nome di una colonna in [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) un valore diverso dal nome della proprietà, utilizzare l'attributo .</span><span class="sxs-lookup"><span data-stu-id="c50bc-123">If you want to change the name of a column to something other than the property name, use the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span> <span data-ttu-id="c50bc-124">Quando si creano oggetti in memoria, è ancora necessario usare il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c50bc-124">When creating in-memory objects, you still create objects using the property name.</span></span> <span data-ttu-id="c50bc-125">Tuttavia, per l'elaborazione dei dati e la creazione di modelli [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) di apprendimento automatico, ML.NET esegue l'override e fa riferimento alla proprietà con il valore fornito nell'attributo.</span><span class="sxs-lookup"><span data-stu-id="c50bc-125">However, for data processing and building machine learning models, ML.NET overrides and references the property with the value provided in the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute.</span></span>

## <a name="load-data-from-a-single-file"></a><span data-ttu-id="c50bc-126">Caricare i dati da un unico file</span><span class="sxs-lookup"><span data-stu-id="c50bc-126">Load data from a single file</span></span>

<span data-ttu-id="c50bc-127">Per caricare dati da [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) un file, utilizzare il metodo insieme al modello di dati per i dati da caricare.</span><span class="sxs-lookup"><span data-stu-id="c50bc-127">To load data from a file use the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method along with the data model for the data to be loaded.</span></span> <span data-ttu-id="c50bc-128">Poiché il parametro `separatorChar` è delimitato da tabulazioni per impostazione predefinita, modificarlo per il file di dati in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="c50bc-128">Since `separatorChar` parameter is tab-delimited by default, change it for your data file as needed.</span></span> <span data-ttu-id="c50bc-129">Se il file presenta un'intestazione, impostare il parametro `hasHeader` su `true` per ignorare la prima riga del file e iniziare a caricare i dati dalla seconda riga.</span><span class="sxs-lookup"><span data-stu-id="c50bc-129">If your file has a header, set the `hasHeader` parameter to `true` to ignore the first line in the file and begin to load data from the second line.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a><span data-ttu-id="c50bc-130">Caricare i dati da più file</span><span class="sxs-lookup"><span data-stu-id="c50bc-130">Load data from multiple files</span></span>

<span data-ttu-id="c50bc-131">Nel caso in cui i dati siano archiviati in più file, e a condizione che lo schema dei dati sia lo stesso, ML.NET consente di caricare i dati da più file in una stessa directory o in directory diverse.</span><span class="sxs-lookup"><span data-stu-id="c50bc-131">In the event that your data is stored in multiple files, as long as the data schema is the same, ML.NET allows you to load data from multiple files that are either in the same directory or multiple directories.</span></span>

### <a name="load-from-files-in-a-single-directory"></a><span data-ttu-id="c50bc-132">Caricare da file in una singola directory</span><span class="sxs-lookup"><span data-stu-id="c50bc-132">Load from files in a single directory</span></span>

<span data-ttu-id="c50bc-133">Quando tutti i file di dati si trovano nella [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) stessa directory, utilizzare i caratteri jolly nel metodo .</span><span class="sxs-lookup"><span data-stu-id="c50bc-133">When all of your data files are in the same directory, use wildcards in the [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) method.</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a><span data-ttu-id="c50bc-134">Caricare da file in più directory</span><span class="sxs-lookup"><span data-stu-id="c50bc-134">Load from files in multiple directories</span></span>

<span data-ttu-id="c50bc-135">Per caricare dati da più [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) directory, [`TextLoader`](xref:Microsoft.ML.Data.TextLoader)utilizzare il metodo per creare un file .</span><span class="sxs-lookup"><span data-stu-id="c50bc-135">To load data from multiple directories, use the [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) method to create a [`TextLoader`](xref:Microsoft.ML.Data.TextLoader).</span></span> <span data-ttu-id="c50bc-136">Quindi, utilizzare [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) il metodo e specificare i singoli percorsi di file (caratteri jolly non possono essere utilizzati).</span><span class="sxs-lookup"><span data-stu-id="c50bc-136">Then, use the [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) method and specify the individual file paths (wildcards can't be used).</span></span>

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a><span data-ttu-id="c50bc-137">Caricare dati da un database relazionaleLoad data from a relational database</span><span class="sxs-lookup"><span data-stu-id="c50bc-137">Load data from a relational database</span></span>

<span data-ttu-id="c50bc-138">ML.NET supporta il caricamento di dati da [`System.Data`](xref:System.Data) una varietà di database relazionali supportati da che includono SQL Server, Database SQL di Azure, Oracle, SQLite, PostgreSQL, Progress, IBM DB2 e molti altri.</span><span class="sxs-lookup"><span data-stu-id="c50bc-138">ML.NET supports loading data from a variety of relational databases supported by [`System.Data`](xref:System.Data) that include SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2, and many more.</span></span>

> [!NOTE]
> <span data-ttu-id="c50bc-139">Per `DatabaseLoader`utilizzare , fare riferimento al pacchetto [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet.</span><span class="sxs-lookup"><span data-stu-id="c50bc-139">To use `DatabaseLoader`, reference the [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet package.</span></span>

<span data-ttu-id="c50bc-140">Dato un database con `House` una tabella denominata e lo schema seguente:Given a database with a table named and the following schema:</span><span class="sxs-lookup"><span data-stu-id="c50bc-140">Given a database with a table named `House` and the following schema:</span></span>

```SQL
CREATE TABLE [House] (
    [HouseId] INT NOT NULL IDENTITY,
    [Size] INT NOT NULL,
    [NumBed] INT NOT NULL,
    [Price] REAL NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

<span data-ttu-id="c50bc-141">I dati possono essere modellati in base a una classe come `HouseData`.</span><span class="sxs-lookup"><span data-stu-id="c50bc-141">The data can be modeled by a class like `HouseData`.</span></span>

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float NumBed { get; set; }

    public float Price { get; set; }
}
```

<span data-ttu-id="c50bc-142">Quindi, all'interno dell'applicazione, creare un `DatabaseLoader`file .</span><span class="sxs-lookup"><span data-stu-id="c50bc-142">Then, inside of your application, create a `DatabaseLoader`.</span></span>

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

<span data-ttu-id="c50bc-143">Definire la stringa di connessione e il comando SQL da `DatabaseSource` eseguire nel database e creare un'istanza.</span><span class="sxs-lookup"><span data-stu-id="c50bc-143">Define your connection string as well as the SQL command to be executed on the database and create a `DatabaseSource` instance.</span></span> <span data-ttu-id="c50bc-144">In questo esempio viene utilizzato un database di SQL Server LocalDB con un percorso di file.</span><span class="sxs-lookup"><span data-stu-id="c50bc-144">This sample uses a LocalDB SQL Server database with a file path.</span></span> <span data-ttu-id="c50bc-145">Tuttavia, DatabaseLoader supporta qualsiasi altra stringa di connessione valida per i database locali e nel cloud.</span><span class="sxs-lookup"><span data-stu-id="c50bc-145">However, DatabaseLoader supports any other valid connection string for databases on-premises and in the cloud.</span></span>

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size, CAST(NumBed as REAL) as NumBed, Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance, connectionString, sqlCommand);
```

<span data-ttu-id="c50bc-146">I dati numerici che [`Real`](xref:System.Data.SqlDbType) non sono [`Real`](xref:System.Data.SqlDbType)di tipo devono essere convertiti in .</span><span class="sxs-lookup"><span data-stu-id="c50bc-146">Numerical data that is not of type [`Real`](xref:System.Data.SqlDbType) has to be converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="c50bc-147">Il [`Real`](xref:System.Data.SqlDbType) tipo è rappresentato come un valore [`Single`](xref:System.Single)a virgola mobile a precisione singola o , il tipo di input previsto dagli algoritmi ML.NET.</span><span class="sxs-lookup"><span data-stu-id="c50bc-147">The [`Real`](xref:System.Data.SqlDbType) type is represented as a single-precision floating-point value or [`Single`](xref:System.Single), the input type expected by ML.NET algorithms.</span></span> <span data-ttu-id="c50bc-148">In questo esempio, la `NumBed` colonna è un numero intero nel database.</span><span class="sxs-lookup"><span data-stu-id="c50bc-148">In this sample, the `NumBed` column is an integer in the database.</span></span> <span data-ttu-id="c50bc-149">Utilizzando `CAST` la funzione incorporata, viene [`Real`](xref:System.Data.SqlDbType)convertito in .</span><span class="sxs-lookup"><span data-stu-id="c50bc-149">Using the `CAST` built-in function, it's converted to [`Real`](xref:System.Data.SqlDbType).</span></span> <span data-ttu-id="c50bc-150">Poiché `Price` la proprietà [`Real`](xref:System.Data.SqlDbType) è già di tipo, viene caricata così com'è.</span><span class="sxs-lookup"><span data-stu-id="c50bc-150">Because the `Price` property is already of type [`Real`](xref:System.Data.SqlDbType) it is loaded as is.</span></span>

<span data-ttu-id="c50bc-151">Utilizzare `Load` il metodo per caricare [`IDataView`](xref:Microsoft.ML.IDataView)i dati in un oggetto .</span><span class="sxs-lookup"><span data-stu-id="c50bc-151">Use the `Load` method to load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).</span></span>

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a><span data-ttu-id="c50bc-152">Caricare i dati da altre origini</span><span class="sxs-lookup"><span data-stu-id="c50bc-152">Load data from other sources</span></span>

<span data-ttu-id="c50bc-153">Oltre a caricare i dati archiviati nei file, ML.NET permette di caricare i dati da altre origini tra cui:</span><span class="sxs-lookup"><span data-stu-id="c50bc-153">In addition to loading data stored in files, ML.NET supports loading data from sources that include but are not limited to:</span></span>

- <span data-ttu-id="c50bc-154">Raccolte in memoria</span><span class="sxs-lookup"><span data-stu-id="c50bc-154">In-memory collections</span></span>
- <span data-ttu-id="c50bc-155">JSON/XML</span><span class="sxs-lookup"><span data-stu-id="c50bc-155">JSON/XML</span></span>

<span data-ttu-id="c50bc-156">Si noti che quando si usano origini di streaming, ML.NET prevede input in forma di raccolta in memoria.</span><span class="sxs-lookup"><span data-stu-id="c50bc-156">Note that when working with streaming sources, ML.NET expects input to be in the form of an in-memory collection.</span></span> <span data-ttu-id="c50bc-157">Pertanto, quando si usano origini come JSON/XML, assicurarsi di formattare i dati come una raccolta in memoria.</span><span class="sxs-lookup"><span data-stu-id="c50bc-157">Therefore, when working with sources like JSON/XML, make sure to format the data into an in-memory collection.</span></span>

<span data-ttu-id="c50bc-158">Considerando la raccolta in memoria seguente:</span><span class="sxs-lookup"><span data-stu-id="c50bc-158">Given the following in-memory collection:</span></span>

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

<span data-ttu-id="c50bc-159">Caricare la raccolta in [`IDataView`](xref:Microsoft.ML.IDataView) memoria [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) in un con il metodo :</span><span class="sxs-lookup"><span data-stu-id="c50bc-159">Load the in-memory collection into an [`IDataView`](xref:Microsoft.ML.IDataView) with the [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) method:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c50bc-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)presuppone che [`IEnumerable`](xref:System.Collections.IEnumerable) l'operazione caricata da sia thread-safe.</span><span class="sxs-lookup"><span data-stu-id="c50bc-160">[`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) assumes that the [`IEnumerable`](xref:System.Collections.IEnumerable) it loads from is thread-safe.</span></span>

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

## <a name="next-steps"></a><span data-ttu-id="c50bc-161">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c50bc-161">Next steps</span></span>

- <span data-ttu-id="c50bc-162">Per pulire o [elaborare](prepare-data-ml-net.md)in altro modo i dati, vedere Preparare i dati per la creazione di un modello .</span><span class="sxs-lookup"><span data-stu-id="c50bc-162">To clean or otherwise process data, see [Prepare data for building a model](prepare-data-ml-net.md).</span></span>
- <span data-ttu-id="c50bc-163">Quando si è pronti per creare un modello, vedere [Eseguire il training e valutare un modello.](train-machine-learning-model-ml-net.md)</span><span class="sxs-lookup"><span data-stu-id="c50bc-163">When you're ready to build a model, see [Train and evaluate a model](train-machine-learning-model-ml-net.md).</span></span>

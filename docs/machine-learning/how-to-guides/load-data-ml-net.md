---
title: Caricare i dati da file e altre origini
description: Learn how to load data for processing and training into ML.NET using the API. Data is stored in files, databases, JSON, XML or in-memory collections.
ms.date: 11/07/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to, title-hack-0625
ms.openlocfilehash: 83aaae2d2e75b3076841750bf5d505390a538bc0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344751"
---
# <a name="load-data-from-files-and-other-sources"></a>Caricare i dati da file e altre origini

Learn how to load data for processing and training into ML.NET using the API. I dati vengono inizialmente archiviati nei file o in altre origini dati, ad esempio database, JSON, XML o raccolte in memoria.

If you're using Model Builder, see [Load training data into Model Builder](load-data-model-builder.md).

## <a name="create-the-data-model"></a>Creare il modello di dati

ML.NET consente di definire modelli di dati tramite le classi. Si considerino, ad esempio, i dati di input seguenti:

```text
Size (Sq. ft.), HistoricalPrice1 ($), HistoricalPrice2 ($), HistoricalPrice3 ($), Current Price ($)
700, 100000, 3000000, 250000, 500000
1000, 600000, 400000, 650000, 700000
```

Creare un modello di dati che rappresenti il frammento di codice seguente:

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

### <a name="annotating-the-data-model-with-column-attributes"></a>Annotazione del modello di dati con gli attributi di colonna

Gli attributi comunicano a ML.NET più informazioni sul modello di data e l'origine dati.

L'attributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) specifica gli indici colonna delle proprietà.

> [!IMPORTANT]
> L'attributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) è necessario solo per caricare dati da un file.

Caricare le colonne come:

- Colonne singole come `Size` e `CurrentPrices` nella classe `HousingData`.
- Più colonne contemporaneamente sotto forma di vettore come `HistoricalPrices` nella classe `HousingData`.

Se si dispone di una proprietà Vector, applicare l'attributo [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) alla proprietà nel modello di dati. È importante sottolineare che tutti gli elementi del vettore devono essere dello stesso tipo. Mantenere separate le colonne offre vantaggi in termini di semplicità e flessibilità di progettazione delle funzionalità, ma per un elevato numero di colonne, il funzionamento delle singole colonne influisce sulla velocità di training.

ML.NET opera attraverso i nomi di colonna. Se si desidera modificare il nome di una colonna cambiandolo rispetto al nome della proprietà, usare l'attributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute). Quando si creano oggetti in memoria, è ancora necessario usare il nome della proprietà. Tuttavia, per l'elaborazione dei dati e la creazione di modelli di Machine Learning, ML.NET esegue l'override e fa riferimento alla proprietà con il valore fornito nell'attributo [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute).

## <a name="load-data-from-a-single-file"></a>Caricare i dati da un unico file

Per caricare i dati da un file, usare il metodo [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) insieme al modello per i dati da caricare. Poiché il parametro `separatorChar` è delimitato da tabulazioni per impostazione predefinita, modificarlo per il file di dati in base alle esigenze. Se il file presenta un'intestazione, impostare il parametro `hasHeader` su `true` per ignorare la prima riga del file e iniziare a caricare i dati dalla seconda riga.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a>Caricare i dati da più file

Nel caso in cui i dati siano archiviati in più file, e a condizione che lo schema dei dati sia lo stesso, ML.NET consente di caricare i dati da più file in una stessa directory o in directory diverse.

### <a name="load-from-files-in-a-single-directory"></a>Caricare da file in una singola directory

Quando tutti i file di dati sono nella stessa directory, usare i caratteri jolly nel metodo [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*).

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a>Caricare da file in più directory

Per caricare i dati da più directory, usare il metodo [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) per creare un elemento [`TextLoader`](xref:Microsoft.ML.Data.TextLoader). Quindi, usare il metodo [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) per specificare i percorsi dei singoli file. Non è possibile usare caratteri jolly.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a>Load data from a relational database

ML.NET supports loading data from a variety of relational databases supported by [`System.Data`](xref:System.Data) that include SQL Server, Azure SQL Database, Oracle, SQLite, PostgreSQL, Progress, IBM DB2, and many more.

> [!NOTE]
> To use `DatabaseLoader`, reference the [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet package.

Given a database with a table named `House` and the following schema:

```SQL
CREATE TABLE [House] (
    [HouseId] INT NOT NULL IDENTITY,
    [Size] INT NOT NULL,
    [NumBed] INT NOT NULL,
    [Price] REAL NOT NULL
    CONSTRAINT [PK_House] PRIMARY KEY ([HouseId])
);
```

I dati possono essere modellati in base a una classe come `HouseData`.

```csharp
public class HouseData
{
    public float Size { get; set; }

    public float NumBed { get; set; }

    public float Price { get; set; }
}
```

Then, inside of your application, create a `DatabaseLoader`.

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

Define your connection string as well as the SQL command to be executed on the database and create a `DatabaseSource` instance. This sample uses a LocalDB SQL Server database with a file path. However, DatabaseLoader supports any other valid connection string for databases on-premises and in the cloud.

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size, CAST(NumBed as REAL) as NumBed, Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance, connectionString, sqlCommand);
```

Numerical data that is not of type [`Real`](xref:System.Data.SqlDbType) has to be converted to [`Real`](xref:System.Data.SqlDbType). The [`Real`](xref:System.Data.SqlDbType) type is represented as a single-precision floating-point value or [`Single`](xref:System.Single), the input type expected by ML.NET algorithms. In this sample, the `NumBed` column is an integer in the database. Using the `CAST` built-in function, it's converted to [`Real`](xref:System.Data.SqlDbType). Because the `Price` property is already of type [`Real`](xref:System.Data.SqlDbType) it is loaded as is.

Use the `Load` method to load the data into an [`IDataView`](xref:Microsoft.ML.IDataView).

```csharp
IDataView data = loader.Load(dbSource);
```

## <a name="load-data-from-other-sources"></a>Caricare i dati da altre origini

Oltre a caricare i dati archiviati nei file, ML.NET permette di caricare i dati da altre origini tra cui:

- Raccolte in memoria
- JSON/XML

Si noti che quando si usano origini di streaming, ML.NET prevede input in forma di raccolta in memoria. Pertanto, quando si usano origini come JSON/XML, assicurarsi di formattare i dati come una raccolta in memoria.

Considerando la raccolta in memoria seguente:

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

Caricare la raccolta in memoria in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) con il metodo [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*):

> [!IMPORTANT]
> [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) presuppone che l'oggetto [`IEnumerable`](xref:System.Collections.IEnumerable) da cui viene caricato sia di tipo thread-safe.

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

## <a name="next-steps"></a>Passaggi successivi

- To clean or otherwise process data, see [Prepare data for building a model](prepare-data-ml-net.md).
- When you're ready to build a model, see [Train and evaluate a model](train-machine-learning-model-ml-net.md).

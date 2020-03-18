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
# <a name="load-data-from-files-and-other-sources"></a>Caricare i dati da file e altre origini

Informazioni su come caricare i dati per l'elaborazione e il training in ML.NET usando l'API. I dati vengono inizialmente archiviati nei file o in altre origini dati, ad esempio database, JSON, XML o raccolte in memoria.

Se si usa Model Builder, vedere Caricare i dati di [training in Model Builder](load-data-model-builder.md).

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

L'attributo [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute) specifica gli indici di colonna delle proprietà.

> [!IMPORTANT]
> [`LoadColumn`](xref:Microsoft.ML.Data.LoadColumnAttribute)è necessario solo durante il caricamento dei dati da un file.

Caricare le colonne come:

- Colonne singole come `Size` e `CurrentPrices` nella classe `HousingData`.
- Più colonne contemporaneamente sotto forma di vettore come `HistoricalPrices` nella classe `HousingData`.

Se si dispone di una [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) proprietà vector, applicare l'attributo alla proprietà nel modello di dati. È importante sottolineare che tutti gli elementi del vettore devono essere dello stesso tipo. Mantenere separate le colonne offre vantaggi in termini di semplicità e flessibilità di progettazione delle funzionalità, ma per un elevato numero di colonne, il funzionamento delle singole colonne influisce sulla velocità di training.

ML.NET opera attraverso i nomi di colonna. Se si desidera modificare il nome di una colonna in [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) un valore diverso dal nome della proprietà, utilizzare l'attributo . Quando si creano oggetti in memoria, è ancora necessario usare il nome della proprietà. Tuttavia, per l'elaborazione dei dati e la creazione di modelli [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) di apprendimento automatico, ML.NET esegue l'override e fa riferimento alla proprietà con il valore fornito nell'attributo.

## <a name="load-data-from-a-single-file"></a>Caricare i dati da un unico file

Per caricare dati da [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) un file, utilizzare il metodo insieme al modello di dati per i dati da caricare. Poiché il parametro `separatorChar` è delimitato da tabulazioni per impostazione predefinita, modificarlo per il file di dati in base alle esigenze. Se il file presenta un'intestazione, impostare il parametro `hasHeader` su `true` per ignorare la prima riga del file e iniziare a caricare i dati dalla seconda riga.

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("my-data-file.csv", separatorChar: ',', hasHeader: true);
```

## <a name="load-data-from-multiple-files"></a>Caricare i dati da più file

Nel caso in cui i dati siano archiviati in più file, e a condizione che lo schema dei dati sia lo stesso, ML.NET consente di caricare i dati da più file in una stessa directory o in directory diverse.

### <a name="load-from-files-in-a-single-directory"></a>Caricare da file in una singola directory

Quando tutti i file di dati si trovano nella [`LoadFromTextFile`](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile*) stessa directory, utilizzare i caratteri jolly nel metodo .

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

//Load Data File
IDataView data = mlContext.Data.LoadFromTextFile<HousingData>("Data/*", separatorChar: ',', hasHeader: true);
```

### <a name="load-from-files-in-multiple-directories"></a>Caricare da file in più directory

Per caricare dati da più [`CreateTextLoader`](xref:Microsoft.ML.TextLoaderSaverCatalog.CreateTextLoader*) directory, [`TextLoader`](xref:Microsoft.ML.Data.TextLoader)utilizzare il metodo per creare un file . Quindi, utilizzare [`TextLoader.Load`](xref:Microsoft.ML.DataLoaderExtensions.Load*) il metodo e specificare i singoli percorsi di file (caratteri jolly non possono essere utilizzati).

```csharp
//Create MLContext
MLContext mlContext = new MLContext();

// Create TextLoader
TextLoader textLoader = mlContext.Data.CreateTextLoader<HousingData>(separatorChar: ',', hasHeader: true);

// Load Data
IDataView data = textLoader.Load("DataFolder/SubFolder1/1.txt", "DataFolder/SubFolder2/1.txt");
```

## <a name="load-data-from-a-relational-database"></a>Caricare dati da un database relazionaleLoad data from a relational database

ML.NET supporta il caricamento di dati da [`System.Data`](xref:System.Data) una varietà di database relazionali supportati da che includono SQL Server, Database SQL di Azure, Oracle, SQLite, PostgreSQL, Progress, IBM DB2 e molti altri.

> [!NOTE]
> Per `DatabaseLoader`utilizzare , fare riferimento al pacchetto [System.Data.SqlClient](https://www.nuget.org/packages/System.Data.SqlClient) NuGet.

Dato un database con `House` una tabella denominata e lo schema seguente:Given a database with a table named and the following schema:

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

Quindi, all'interno dell'applicazione, creare un `DatabaseLoader`file .

```csharp
MLContext mlContext = new MLContext();

DatabaseLoader loader = mlContext.Data.CreateDatabaseLoader<HouseData>();
```

Definire la stringa di connessione e il comando SQL da `DatabaseSource` eseguire nel database e creare un'istanza. In questo esempio viene utilizzato un database di SQL Server LocalDB con un percorso di file. Tuttavia, DatabaseLoader supporta qualsiasi altra stringa di connessione valida per i database locali e nel cloud.

```csharp
string connectionString = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=<YOUR-DB-FILEPATH>;Database=<YOUR-DB-NAME>;Integrated Security=True;Connect Timeout=30";

string sqlCommand = "SELECT Size, CAST(NumBed as REAL) as NumBed, Price FROM House";

DatabaseSource dbSource = new DatabaseSource(SqlClientFactory.Instance, connectionString, sqlCommand);
```

I dati numerici che [`Real`](xref:System.Data.SqlDbType) non sono [`Real`](xref:System.Data.SqlDbType)di tipo devono essere convertiti in . Il [`Real`](xref:System.Data.SqlDbType) tipo è rappresentato come un valore [`Single`](xref:System.Single)a virgola mobile a precisione singola o , il tipo di input previsto dagli algoritmi ML.NET. In questo esempio, la `NumBed` colonna è un numero intero nel database. Utilizzando `CAST` la funzione incorporata, viene [`Real`](xref:System.Data.SqlDbType)convertito in . Poiché `Price` la proprietà [`Real`](xref:System.Data.SqlDbType) è già di tipo, viene caricata così com'è.

Utilizzare `Load` il metodo per caricare [`IDataView`](xref:Microsoft.ML.IDataView)i dati in un oggetto .

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

Caricare la raccolta in [`IDataView`](xref:Microsoft.ML.IDataView) memoria [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*) in un con il metodo :

> [!IMPORTANT]
> [`LoadFromEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.LoadFromEnumerable*)presuppone che [`IEnumerable`](xref:System.Collections.IEnumerable) l'operazione caricata da sia thread-safe.

```csharp
// Create MLContext
MLContext mlContext = new MLContext();

//Load Data
IDataView data = mlContext.Data.LoadFromEnumerable<HousingData>(inMemoryCollection);
```

## <a name="next-steps"></a>Passaggi successivi

- Per pulire o [elaborare](prepare-data-ml-net.md)in altro modo i dati, vedere Preparare i dati per la creazione di un modello .
- Quando si è pronti per creare un modello, vedere [Eseguire il training e valutare un modello.](train-machine-learning-model-ml-net.md)

---
title: Esaminare i valori dei dati intermedi durante l'elaborazione di ML.NET
description: Informazioni su come esaminare i valori effettivi dei dati intermedi durante l'elaborazione della pipeline di apprendimento automatico di ML.NET
ms.date: 04/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 06c4a473841db62a10dfc24025f842df7ae2c583
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063510"
---
# <a name="inspect-intermediate-data-values-during-processing"></a><span data-ttu-id="7f139-103">Esaminare i valori dei dati intermedi durante l'elaborazione</span><span class="sxs-lookup"><span data-stu-id="7f139-103">Inspect intermediate data values during processing</span></span>

<span data-ttu-id="7f139-104">Informazioni su come esaminare i valori durante i passaggi di caricamento, elaborazione e training in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7f139-104">Learn how to inspect values during loading, processing and training steps in ML.NET.</span></span>

<span data-ttu-id="7f139-105">Dati analoghi a quelli rappresentati di seguito e caricati in un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) possono essere esaminati in vari modi in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="7f139-105">Data like the one represented below which is loaded into an [`IDataView`](xref:Microsoft.ML.IDataView) can be inspected in various ways in ML.NET.</span></span>
 
```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

## <a name="convert-idataview-to-ienumerable"></a><span data-ttu-id="7f139-106">Convertire IDataView in IEnumerable</span><span class="sxs-lookup"><span data-stu-id="7f139-106">Convert IDataView to IEnumerable</span></span>

<span data-ttu-id="7f139-107">Uno dei modi più rapidi per esaminare i valori di un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) consiste nel convertirla in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span><span class="sxs-lookup"><span data-stu-id="7f139-107">One of the quickest ways to inspect the values of an [`IDataView`](xref:Microsoft.ML.IDataView) is to convert it to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span> <span data-ttu-id="7f139-108">Per convertire [`IDataView`](xref:Microsoft.ML.IDataView) in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601), usare il metodo [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*).</span><span class="sxs-lookup"><span data-stu-id="7f139-108">To convert an [`IDataView`](xref:Microsoft.ML.IDataView) to [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) use the [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) method.</span></span> 

<span data-ttu-id="7f139-109">Per ottimizzare le prestazioni, impostare il valore di `reuseRowObject` su `true`.</span><span class="sxs-lookup"><span data-stu-id="7f139-109">To optimize performance, set the value of `reuseRowObject` to `true`.</span></span> <span data-ttu-id="7f139-110">Questa operazione popolerà lo stesso oggetto in modo differito con i dati della riga corrente quando viene valutata anziché creare un nuovo oggetto per ogni riga nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="7f139-110">Doing so will lazily populate the same object with the data of the current row as it's being evaluated as opposed to creating a new object for each row in the dataset.</span></span>

```csharp
// Create an IEnumerable of HousingData objects from IDataView
IEnumerable<HousingData> housingDataEnumerable =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: true);

// Iterate over each row
foreach (HousingData row in housingDataEnumerable)
{
    // Do something (print out Size property) with current Housing Data object being evaluated
    Console.WriteLine(row.Size);
}
```

<span data-ttu-id="7f139-111">Se è sufficiente accedere a una parte dei dati o a indici specifici, usare [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) e impostare il valore del parametro `reuseRowObject` su `false`, in modo che venga creato un nuovo oggetto per ogni riga richiesta del set di dati.</span><span class="sxs-lookup"><span data-stu-id="7f139-111">If you only need access to a portion of the data or specific indices, use [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) and set the `reuseRowObject` parameter value to `false` so a new object is created for each of the requested rows in the dataset.</span></span> <span data-ttu-id="7f139-112">Quindi, convertire [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) in una matrice o in un elenco.</span><span class="sxs-lookup"><span data-stu-id="7f139-112">Then, convert the [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) to an array or list.</span></span>

> [!WARNING]
> <span data-ttu-id="7f139-113">Poiché la conversione di [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) in una matrice o elenco caricherà in memoria tutte le righe di [`IDataView`](xref:Microsoft.ML.IDataView) richieste, le prestazioni potrebbero risentirne.</span><span class="sxs-lookup"><span data-stu-id="7f139-113">Converting the result of [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) to an array or list will load all the requested [`IDataView`](xref:Microsoft.ML.IDataView) rows into memory which may affect performance.</span></span>

<span data-ttu-id="7f139-114">Dopo aver creata la raccolta, sarà possibile eseguire operazioni sui dati.</span><span class="sxs-lookup"><span data-stu-id="7f139-114">Once the collection has been created, you can perform operations on the data.</span></span> <span data-ttu-id="7f139-115">Il frammento di codice riportato di seguito prende le prime tre righe del set di dati e calcola il prezzo medio corrente.</span><span class="sxs-lookup"><span data-stu-id="7f139-115">The code snippet below takes the first three rows in the dataset and calculates the average current price.</span></span>

```csharp
// Create an Array of HousingData objects from IDataView
HousingData[] housingDataArray =
    mlContext.Data.CreateEnumerable<HousingData>(data, reuseRowObject: false)
        .Take(3)
        .ToArray();

// Calculate Average CurrentPrice of First Three Elements
HousingData firstRow = housingDataArray[0];
HousingData secondRow = housingDataArray[1];
HousingData thirdRow = housingDataArray[2];
float averageCurrentPrice = (firstRow.CurrentPrice + secondRow.CurrentPrice + thirdRow.CurrentPrice) / 3;
``` 

## <a name="inspect-values-in-a-single-column"></a><span data-ttu-id="7f139-116">Esaminare i valori in una singola colonna</span><span class="sxs-lookup"><span data-stu-id="7f139-116">Inspect values in a single column</span></span>

<span data-ttu-id="7f139-117">In qualsiasi momento del processo di creazione del modello, è possibile accedere ai valori in una singola colonna di un elemento [`IDataView`](xref:Microsoft.ML.IDataView) tramite il metodo [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*).</span><span class="sxs-lookup"><span data-stu-id="7f139-117">At any point in the model building process, values in a single column of an [`IDataView`](xref:Microsoft.ML.IDataView) can be accessed using the [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method.</span></span> <span data-ttu-id="7f139-118">Il metodo [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) restituisce tutti i valori in una singola colonna come [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span><span class="sxs-lookup"><span data-stu-id="7f139-118">The [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) method returns all of the values in a single column as an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601).</span></span>

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a><span data-ttu-id="7f139-119">Esaminare i valori IDataView una riga alla volta</span><span class="sxs-lookup"><span data-stu-id="7f139-119">Inspect IDataView values one row at a time</span></span>

<span data-ttu-id="7f139-120">L'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) viene valutata in modo differito.</span><span class="sxs-lookup"><span data-stu-id="7f139-120">[`IDataView`](xref:Microsoft.ML.IDataView) is lazily evaluated.</span></span> <span data-ttu-id="7f139-121">Per scorrere le righe di un'interfaccia [`IDataView`](xref:Microsoft.ML.IDataView) senza eseguire la conversione in [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601), come illustrato nelle sezioni precedenti di questo documento, creare una classe [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) usando il metodo [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) e passare la classe [DataViewSchema](xref:Microsoft.ML.DataViewSchema) di [`IDataView`](xref:Microsoft.ML.IDataView) come parametro.</span><span class="sxs-lookup"><span data-stu-id="7f139-121">To iterate over the rows of an [`IDataView`](xref:Microsoft.ML.IDataView) without converting to an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) as demonstrated in previous sections of this document, create a [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) by using the [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) method and passing in the [DataViewSchema](xref:Microsoft.ML.DataViewSchema) of your [`IDataView`](xref:Microsoft.ML.IDataView) as a parameter.</span></span> <span data-ttu-id="7f139-122">Quindi, per scorrere le righe, usare il metodo [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) del cursore insieme ai delegati [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) per estrarre i rispettivi valori da ognuna delle colonne.</span><span class="sxs-lookup"><span data-stu-id="7f139-122">Then, to iterate over rows, use the [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) cursor method along with [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) delegates to extract the respective values from each of the columns.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f139-123">Per motivi di prestazioni, in ML.NET i vettori usano [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) anziché i tipi di raccolta nativi (vale a dire `Vector`,`float[]`).</span><span class="sxs-lookup"><span data-stu-id="7f139-123">For performance purposes, vectors in ML.NET use [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) instead of native collection types (that is, `Vector`,`float[]`).</span></span> 

```csharp
// Get DataViewSchema of IDataView
DataViewSchema columns = data.Schema;

// Create DataViewCursor
using (DataViewRowCursor cursor = data.GetRowCursor(columns))
{
    // Define variables where extracted values will be stored to
    float size = default;
    VBuffer<float> historicalPrices = default;
    float currentPrice = default;

    // Define delegates for extracting values from columns
    ValueGetter<float> sizeDelegate = cursor.GetGetter<float>(columns[0]);
    ValueGetter<VBuffer<float>> historicalPriceDelegate = cursor.GetGetter<VBuffer<float>>(columns[1]);
    ValueGetter<float> currentPriceDelegate = cursor.GetGetter<float>(columns[2]);
    
    // Iterate over each row
    while (cursor.MoveNext())
    {
        //Get values from respective columns
        sizeDelegate.Invoke(ref size);
        historicalPriceDelegate.Invoke(ref historicalPrices);
        currentPriceDelegate.Invoke(ref currentPrice);
    }
}
```

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a><span data-ttu-id="7f139-124">Anteprima dei risultati di pre-elaborazione o di training su un subset di dati</span><span class="sxs-lookup"><span data-stu-id="7f139-124">Preview result of pre-processing or training on a subset of the data</span></span>

> [!WARNING]
> <span data-ttu-id="7f139-125">Non usare `Preview` nel codice da usare in ambienti di produzione perché è destinato al debug e può ridurre le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7f139-125">Do not use `Preview` in production code because it is intended for debugging and may reduce performance.</span></span>

<span data-ttu-id="7f139-126">Il processo di creazione dei modelli è sperimentale e iterativo.</span><span class="sxs-lookup"><span data-stu-id="7f139-126">The model building process is experimental and iterative.</span></span> <span data-ttu-id="7f139-127">Per visualizzare in anteprima come si presenteranno i dati dopo la pre-elaborazione o il training di un modello di Machine Learning su un subset di dati, usare il metodo [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) che restituisce una classe [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span><span class="sxs-lookup"><span data-stu-id="7f139-127">To preview what data would look like after pre-processing or training a machine learning model on a subset of the data, use the [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) method which returns a [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview).</span></span> <span data-ttu-id="7f139-128">Il risultato è un oggetto con le proprietà `ColumnView` e `RowView` che sono entrambe [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) e che contengono i valori in una particolare colonna o riga.</span><span class="sxs-lookup"><span data-stu-id="7f139-128">The result is an object with `ColumnView` and `RowView` properties which are both an [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) and contain the values in a particular column or row.</span></span> <span data-ttu-id="7f139-129">Specificare il numero di righe a cui applicare la trasformazione con il parametro `maxRows`.</span><span class="sxs-lookup"><span data-stu-id="7f139-129">Specify the number of rows to apply the transformation to with the `maxRows` parameter.</span></span>

![Oggetto di anteprima debugger dati](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

<span data-ttu-id="7f139-131">L'analisi di un elemento [`IDataView`](xref:Microsoft.ML.IDataView) avrebbe un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7f139-131">The result of inspecting an [`IDataView`](xref:Microsoft.ML.IDataView) would look similar to the following:</span></span>

![Visualizzazione righe di anteprima debugger dati](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)

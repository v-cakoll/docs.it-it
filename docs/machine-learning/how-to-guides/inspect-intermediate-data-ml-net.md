---
title: Esaminare i dati intermedi durante l'elaborazione di ML.NET
description: Informazioni su come esaminare i dati intermedi durante il caricamento della pipeline di Machine Learning di ML.NET, l'elaborazione e i passaggi di training del modello in ML.NET.
ms.date: 06/25/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 11df1d5caaa7b7974360d863f85afbff18985e47
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73977095"
---
# <a name="inspect-intermediate-data-during-processing"></a>Esaminare i dati intermedi durante l'elaborazione

Di seguito viene descritto come esaminare i dati intermedi durante il caricamento, l'elaborazione e i passaggi di training del modello in ML.NET. I dati intermedi corrispondono all'output di ogni fase della pipeline di Machine Learning.

I dati intermedi come quello rappresentato [`IDataView`](xref:Microsoft.ML.IDataView) al di sotto che viene caricato in un possono essere ispezionati in vari modi in ML.NET.

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

## <a name="convert-idataview-to-ienumerable"></a>Convertire IDataView in IEnumerable

Uno dei modi più rapidi per ispezionare un [`IDataView`](xref:Microsoft.ML.IDataView) è quello di convertirlo in un [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)file . Per convertire [`IDataView`](xref:Microsoft.ML.IDataView) [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) un [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) oggetto per utilizzare il metodo.

Per ottimizzare le prestazioni, impostare `reuseRowObject` su `true`. Questa operazione popolerà lo stesso oggetto in modo differito con i dati della riga corrente quando viene valutata anziché creare un nuovo oggetto per ogni riga nel set di dati.

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

## <a name="accessing-specific-indices-with-ienumerable"></a>Accesso a indici specifici con IEnumerable

Se è necessario accedere solo a una parte dei [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) dati `reuseRowObject` o a `false` indici specifici, utilizzare e impostare il valore del parametro su in modo che venga creato un nuovo oggetto per ognuna delle righe richieste nel set di dati. Quindi, convertire [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) il in una matrice o un elenco.

> [!WARNING]
> La conversione [`CreateEnumerable`](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable*) del risultato di in una [`IDataView`](xref:Microsoft.ML.IDataView) matrice o in un elenco caricherà tutte le righe richieste in memoria che possono influire sulle prestazioni.

Dopo aver creata la raccolta, sarà possibile eseguire operazioni sui dati. Il frammento di codice riportato di seguito prende le prime tre righe del set di dati e calcola il prezzo medio corrente.

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

## <a name="inspect-values-in-a-single-column"></a>Esaminare i valori in una singola colonna

In qualsiasi punto del processo di creazione del [`IDataView`](xref:Microsoft.ML.IDataView) modello, è [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) possibile accedere ai valori in una singola colonna di un oggetto utilizzando il metodo . Il [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) metodo restituisce tutti i valori [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601)in una singola colonna come oggetto .

```csharp
IEnumerable<float> sizeColumn = data.GetColumn<float>("Size").ToList();
```

## <a name="inspect-idataview-values-one-row-at-a-time"></a>Esaminare i valori IDataView una riga alla volta

[`IDataView`](xref:Microsoft.ML.IDataView)viene valutata in modo pigro. Per scorrere le righe [`IDataView`](xref:Microsoft.ML.IDataView) di un [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) senza convertire in un come illustrato [`DataViewRowCursor`](xref:Microsoft.ML.DataViewRowCursor) nelle sezioni [`GetRowCursor`](xref:Microsoft.ML.IDataView.GetRowCursor*) precedenti di questo documento, [`IDataView`](xref:Microsoft.ML.IDataView) creare un utilizzando il metodo e passando il [DataViewSchema](xref:Microsoft.ML.DataViewSchema) dell'utente come parametro. Quindi, per scorrere le [`MoveNext`](xref:Microsoft.ML.DataViewRowCursor.MoveNext*) righe, utilizzare [`ValueGetter`](xref:Microsoft.ML.ValueGetter%601) il metodo cursor insieme ai delegati per estrarre i rispettivi valori da ognuna delle colonne.

> [!IMPORTANT]
> Ai fini delle prestazioni, [`VBuffer`](xref:Microsoft.ML.Data.VBuffer%601) i vettori in ML.NET utilizzare `Vector``float[]`anziché i tipi di raccolta nativi, ovvero , .

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

## <a name="preview-result-of-pre-processing-or-training-on-a-subset-of-the-data"></a>Anteprima dei risultati di pre-elaborazione o di training su un subset di dati

> [!WARNING]
> Non usare `Preview` nel codice da usare in ambienti di produzione perché è destinato al debug e può ridurre le prestazioni.

Il processo di creazione dei modelli è sperimentale e iterativo. Per visualizzare in anteprima l'aspetto dei dati dopo la pre-elaborazione o [`Preview`](xref:Microsoft.ML.DebuggerExtensions.Preview*) il training [`DataDebuggerPreview`](xref:Microsoft.ML.Data.DataDebuggerPreview)di un modello di Machine Learning in un subset di dati, usare il metodo che restituisce un oggetto . Il risultato è `ColumnView` `RowView` un oggetto con [`IEnumerable`](xref:System.Collections.Generic.IEnumerable%601) proprietà e che sono entrambi e contengono i valori in una particolare colonna o riga. Specificare il numero di righe a cui applicare la trasformazione con il parametro `maxRows`.

![Oggetto di anteprima debugger dati](./media/inspect-intermediate-data-ml-net/data-debugger-preview-01.png)

Il risultato dell'ispezione [`IDataView`](xref:Microsoft.ML.IDataView) sarà simile al seguente:

![Visualizzazione righe di anteprima debugger dati](./media/inspect-intermediate-data-ml-net/data-debugger-preview-02.png)

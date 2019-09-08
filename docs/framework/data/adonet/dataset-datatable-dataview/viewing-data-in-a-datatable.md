---
title: Visualizzazione di dati in un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: c13f0b802b2714a17ea4014625a65ebd1b0011f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785857"
---
# <a name="viewing-data-in-a-datatable"></a>Visualizzazione di dati in un oggetto DataTable

È possibile accedere al contenuto di un <xref:System.Data.DataTable> oggetto utilizzando le raccolte **Rows** e **Columns** di **DataTable**. È anche possibile usare il <xref:System.Data.DataTable.Select%2A> metodo per restituire subset dei dati in un **oggetto DataTable** in base ai criteri, inclusi i criteri di ricerca, l'ordinamento e lo stato della riga. Inoltre, è possibile usare il <xref:System.Data.DataRowCollection.Find%2A> metodo di **DataRowCollection** durante la ricerca di una determinata riga usando un valore di chiave primaria.

Il metodo **Select** dell'oggetto **DataTable** restituisce un set di <xref:System.Data.DataRow> oggetti che corrispondono ai criteri specificati. **Select** accetta gli argomenti facoltativi di un'espressione di filtro, di un'espressione di ordinamento e di **DataViewRowState**. L'espressione di filtro identifica le righe da restituire in base ai valori di DataColumn `LastName = 'Smith'`, ad esempio. Per l'espressione di ordinamento vengono usate le convenzioni SQL standard per l'ordinamento di colonne, ad esempio `LastName ASC, FirstName ASC`. Per le regole sulla scrittura di espressioni, <xref:System.Data.DataColumn.Expression%2A> vedere la proprietà della classe **DataColumn** .

> [!TIP]
> Se si eseguono una serie di chiamate al metodo **Select** di un **oggetto DataTable**, è possibile migliorare le prestazioni creando prima un <xref:System.Data.DataView> oggetto per la **DataTable**. La creazione di **DataView** indicizza le righe della tabella. Il metodo **Select** usa quindi tale indice, riducendo in modo significativo il tempo necessario per generare il risultato della query. Per informazioni sulla creazione di un **DataView** per un **DataTable**, vedere [DataViews](dataviews.md).

Il metodo **Select** determina la versione delle righe da visualizzare o modificare in base a un <xref:System.Data.DataViewRowState>oggetto. Nella tabella seguente vengono descritti i possibili valori di enumerazione **DataViewRowState** .

|Valore di DataViewRowState|Descrizione|
|----------------------------|-----------------|
|**CurrentRows**|Righe correnti, incluse le righe non modificate, aggiunte e modificate.|
|**Eliminato**|Riga eliminata.|
|**ModifiedCurrent**|Una versione corrente, ovvero una versione modificata dei dati originali. Vedere **ModifiedOriginal**.|
|**ModifiedOriginal**|La versione originale di tutte le righe modificate. La versione corrente è disponibile tramite **ModifiedCurrent**.|
|**Aggiunto**|Nuova riga.|
|**None**|No.|
|**OriginalRows**|Righe originali, tra cui righe non modificate ed eliminate.|
|**Invariato**|Riga non modificata.|

Nell'esempio seguente l'oggetto **DataSet** viene filtrato in modo da usare solo le righe il cui **DataViewRowState** è impostato su **CurrentRows**.

```vb
Dim column As DataColumn
Dim row As DataRow

Dim currentRows() As DataRow = _
    workTable.Select(Nothing, Nothing, DataViewRowState.CurrentRows)

If (currentRows.Length < 1 ) Then
  Console.WriteLine("No Current Rows Found")
Else
  For Each column in workTable.Columns
    Console.Write(vbTab & column.ColumnName)
  Next

  Console.WriteLine(vbTab & "RowState")

  For Each row In currentRows
    For Each column In workTable.Columns
      Console.Write(vbTab & row(column).ToString())
    Next

    Dim rowState As String = _
        System.Enum.GetName(row.RowState.GetType(), row.RowState)
    Console.WriteLine(vbTab & rowState)
  Next
End If
```

```csharp
DataRow[] currentRows = workTable.Select(
    null, null, DataViewRowState.CurrentRows);

if (currentRows.Length < 1 )
  Console.WriteLine("No Current Rows Found");
else
{
  foreach (DataColumn column in workTable.Columns)
    Console.Write("\t{0}", column.ColumnName);

  Console.WriteLine("\tRowState");

  foreach (DataRow row in currentRows)
  {
    foreach (DataColumn column in workTable.Columns)
      Console.Write("\t{0}", row[column]);

    Console.WriteLine("\t" + row.RowState);
  }
}
```

Il metodo **Select** può essere utilizzato per restituire righe con valori di campo o valori di **RowState** diversi. Nell'esempio seguente viene restituita una matrice **DataRow** che fa riferimento a tutte le righe che sono state eliminate e restituisce un'altra matrice **DataRow** che fa riferimento a tutte le righe, ordinate per **CustLName**, in cui la colonna **CustID** è maggiore di 5. Per informazioni su come visualizzare le informazioni nella riga **Deleted** , vedere Stati di [riga e versioni di riga](row-states-and-row-versions.md).

```vb
' Retrieve all deleted rows.
Dim deletedRows() As DataRow = workTable.Select(Nothing, Nothing, DataViewRowState.Deleted)

' Retrieve rows where CustID > 5, and order by CustLName.
Dim custRows() As DataRow = workTable.Select( _
    "CustID > 5", "CustLName ASC")
```

```csharp
// Retrieve all deleted rows.
DataRow[] deletedRows = workTable.Select(
    null, null, DataViewRowState.Deleted);

// Retrieve rows where CustID > 5, and order by CustLName.
DataRow[] custRows = workTable.Select("CustID > 5", "CustLName ASC");
```

## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataViewRowState>
- [Manipolazione di dati in un oggetto DataTable](manipulating-data-in-a-datatable.md)
- [Stati e versioni delle righe](row-states-and-row-versions.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)

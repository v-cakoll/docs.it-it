---
title: Visualizzazione di dati in un oggetto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
ms.openlocfilehash: de745633060dd4f7b1610492d0ff57ec7a4f545b
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "46710709"
---
# <a name="viewing-data-in-a-datatable"></a>Visualizzazione di dati in un oggetto DataTable
È possibile accedere al contenuto di un <xref:System.Data.DataTable> usando il **righe** e **colonne** raccolte del **DataTable**. È anche possibile usare la <xref:System.Data.DataTable.Select%2A> per restituire subset di dati in un **DataTable** in base ai criteri inclusi i criteri di ricerca, l'ordinamento e lo stato della riga. Inoltre, è possibile usare la <xref:System.Data.DataRowCollection.Find%2A> metodo per il **DataRowCollection** durante la ricerca di una particolare riga mediante un valore di chiave primaria.  
  
 Il **seleziona** metodo per il **DataTable** oggetto restituisce un set di <xref:System.Data.DataRow> gli oggetti che corrispondono ai criteri specificati. **Selezionare** accetta gli argomenti facoltativi di un'espressione di filtro, espressione di ordinamento, e **DataViewRowState**. L'espressione di filtro identifica le righe da restituire in base alle **DataColumn** valori, ad esempio `LastName = 'Smith'`. Per l'espressione di ordinamento vengono usate le convenzioni SQL standard per l'ordinamento di colonne, ad esempio `LastName ASC, FirstName ASC`. Per informazioni sulla scrittura di espressioni, vedere la <xref:System.Data.DataColumn.Expression%2A> proprietà del **DataColumn** classe.  
  
> [!TIP]
>  Se si sta eseguendo un numero di chiamate per il **selezionare** metodo di un **DataTable**, è possibile migliorare le prestazioni tramite la creazione di un <xref:System.Data.DataView> per i **DataTable**. Creazione di **DataView** Indicizza le righe della tabella. Il **seleziona** metodo quindi utilizza l'indice, riducendo in modo significativo il tempo necessario per generare il risultato della query. Per informazioni sulla creazione di un **DataView** per una **DataTable**, vedere [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 Il **selezionate** metodo determina la versione delle righe da visualizzare o modificare in base un <xref:System.Data.DataViewRowState>. Nella tabella seguente vengono descritti i possibili **DataViewRowState** valori di enumerazione.  
  
|Valore di DataViewRowState|Descrizione|  
|----------------------------|-----------------|  
|**CurrentRows**|Righe correnti, incluse le righe non modificate, aggiunte e modificate.|  
|**Eliminato**|Riga eliminata.|  
|**ModifiedCurrent**|Una versione corrente, ovvero una versione modificata dei dati originali. (Vedere **ModifiedOriginal**.)|  
|**ModifiedOriginal**|La versione originale di tutte le righe modificate. La versione corrente è disponibile se si usa **ModifiedCurrent**.|  
|**Aggiunto**|Nuova riga.|  
|**None**|Nessuno.|  
|**OriginalRows**|Righe originali, tra cui righe non modificate ed eliminate.|  
|**non modificato**|Riga non modificata.|  
  
 Nell'esempio seguente, il **set di dati** l'oggetto viene escluso in modo che si utilizza soltanto con righe la cui proprietà **DataViewRowState** è impostata su **CurrentRows**.  
  
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
  
 Il **selezionate** metodo può essere utilizzato per restituire righe con diversi **RowState** valori o valori di campo. L'esempio seguente restituisce un **DataRow** che fa riferimento a tutte le righe che sono state eliminate e restituisce un'altra matrice **DataRow** array che fa riferimento a tutte le righe, ordinate in base **CustLName**, dove il **CustID** colonna è maggiore di 5. Per informazioni su come visualizzare le informazioni contenute nel **Deleted** righe, vedere [stati e le versioni delle righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
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
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataViewRowState>  
 [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Stati e versioni delle righe](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)

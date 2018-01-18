---
title: Visualizzazione di dati in un oggetto DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1d26e0fb-f6e0-4afa-9a9c-b8d55b8f20dc
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2576c95ad7739d28e2ca822fd13fb6f176900814
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="viewing-data-in-a-datatable"></a>Visualizzazione di dati in un oggetto DataTable
È possibile accedere al contenuto di un <xref:System.Data.DataTable> utilizzando il **righe** e **colonne** insiemi di **DataTable**. È inoltre possibile utilizzare il <xref:System.Data.DataTable.Select%2A> per restituire subset di dati in un **DataTable** in base ai criteri compresi i criteri di ricerca, ordinamento e lo stato della riga. Inoltre, è possibile utilizzare il <xref:System.Data.DataRowCollection.Find%2A> metodo il **DataRowCollection** durante la ricerca di una particolare riga mediante un valore di chiave primaria.  
  
 Il **selezionare** metodo il **DataTable** oggetto restituisce un set di <xref:System.Data.DataRow> gli oggetti che soddisfano i criteri specificati. **Selezionare** accetta gli argomenti facoltativi di un'espressione di filtro, un'espressione di ordinamento e **DataViewRowState**. L'espressione di filtro identifica le righe da restituire in base alle **DataColumn** valori, ad esempio `LastName = 'Smith'`. Per l'espressione di ordinamento vengono usate le convenzioni SQL standard per l'ordinamento di colonne, ad esempio `LastName ASC, FirstName ASC`. Per le regole sulla scrittura di espressioni, vedere il <xref:System.Data.DataColumn.Expression%2A> proprietà del **DataColumn** classe.  
  
> [!TIP]
>  Se si esegue un numero di chiamate per il **selezionare** metodo di un **DataTable**, è possibile migliorare le prestazioni creando innanzitutto un <xref:System.Data.DataView> per il **DataTable**. Creazione di **DataView** indicizzate le righe della tabella. Il **selezionare** metodo quindi utilizza l'indicizzazione, riducendo notevolmente il tempo necessario per generare il risultato della query. Per informazioni sulla creazione di un **DataView** per un **DataTable**, vedere [DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 Il **selezionare** (metodo) determina quale versione delle righe da visualizzare o modificare in base a un <xref:System.Data.DataViewRowState>. Nella tabella seguente vengono descritti i possibili **DataViewRowState** valori di enumerazione.  
  
|Valore di DataViewRowState|Descrizione|  
|----------------------------|-----------------|  
|**CurrentRows**|Righe correnti, incluse le righe non modificate, aggiunte e modificate.|  
|**Eliminato**|Riga eliminata.|  
|**ModifiedCurrent**|Una versione corrente, ovvero una versione modificata dei dati originali. (Vedere **ModifiedOriginal**.)|  
|**ModifiedOriginal**|La versione originale di tutte le righe modificate. La versione corrente è disponibile tramite **ModifiedCurrent**.|  
|**Aggiunta**|Nuova riga.|  
|**None**|Nessuno.|  
|**OriginalRows**|Righe originali, tra cui righe non modificate ed eliminate.|  
|**Non modificato**|Riga non modificata.|  
  
 Nell'esempio seguente, il **DataSet** oggetto è filtrato in modo che si utilizza soltanto le righe il cui **DataViewRowState** è impostato su **CurrentRows**.  
  
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
  
 Il **selezionare** metodo può essere utilizzato per restituire le righe con diversi **RowState** valori o valori di campo. Nell'esempio seguente viene restituito un **DataRow** matrice che fa riferimento a tutte le righe che sono state eliminate e restituisce un'altra **DataRow** matrice che fa riferimento a tutte le righe, ordinate in base **CustLName**, dove il **CustID** colonna è maggiore di 5. Per informazioni su come visualizzare le informazioni contenute nel **Deleted** di riga, vedere [stati delle righe e le versioni di riga](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
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
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Spostarsi tra il risultato delle query
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 5d86095586af273f62980fcf8ddf10804b1cfa5a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406810"
---
# <a name="paging-through-a-query-result"></a>Spostarsi tra il risultato delle query
Il paging del risultato di una query corrisponde al processo di restituzione dei risultati di una query in subset di dati di dimensioni inferiori o pagine. Si tratta di una tecnica comunemente usata per la visualizzazione di risultati in blocchi di dimensioni ridotte e di facile gestione.  
  
 Il **DataAdapter** fornisce una funzionalità per la restituzione solo una pagina di dati, tramite gli overload del **riempire** (metodo). Tuttavia, ciò potrebbe non essere ottimale per il paging dei risultati di query di grandi dimensioni perché, anche se il **DataAdapter** riempie la destinazione <xref:System.Data.DataTable> o <xref:System.Data.DataSet> con solo i record richiesti, le risorse per restituire il intera query sono comunque utilizzato. Per restituire una pagina di dati da un'origine dati senza usare le risorse per la restituzione dell'intera query, specificare dei criteri aggiuntivi per la query, in modo che vengano restituite solo le righe necessarie.  
  
 Usare la **riempire** metodo per restituire una pagina di dati, specificare un **startRecord** parametro, il primo record della pagina di dati e un **maxRecords** parametro, per il numero di record nella pagina di dati.  
  
 Esempio di codice seguente viene illustrato come utilizzare il **riempire** per restituire la prima pagina del risultato della query in cui le dimensioni di pagina corrispondono a cinque record.  
  
```vb  
Dim currentIndex As Integer = 0  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT * FROM dbo.Orders ORDER BY OrderID"  
' Assumes that connection is a valid SqlConnection object.  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
int currentIndex = 0;  
int pageSize = 5;  
  
string orderSQL = "SELECT * FROM Orders ORDER BY OrderID";  
// Assumes that connection is a valid SqlConnection object.  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 Nell'esempio precedente, il **set di dati** viene compilato solo con cinque record, ma l'intero **ordini** viene restituita una tabella. Per riempire il **set di dati** con gli stessi cinque record, ma restituire solo cinque record, usare la parte superiore e le clausole WHERE nell'istruzione SQL, come nell'esempio di codice seguente.  
  
```vb  
Dim pageSize As Integer = 5  
  
Dim orderSQL As String = "SELECT TOP " & pageSize & _  
  " * FROM Orders ORDER BY OrderID"  
Dim adapter As SqlDataAdapter = _  
  New SqlDataAdapter(orderSQL, connection)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Orders")   
```  
  
```csharp  
int pageSize = 5;  
  
string orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders ORDER BY OrderID";  
SqlDataAdapter adapter = new SqlDataAdapter(orderSQL, connection);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Orders");  
```  
  
 Notare che, quando si esegue in questo modo il paging dei risultati della query, è necessario conservare l'identificatore univoco in base al quale sono ordinate le righe, in modo da passare l'identificatore univoco al comando per restituire la pagina successiva di record, come illustrato nell'esempio seguente.  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =   
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 Per restituire la pagina successiva di record usando l'overload del metodo di **riempire** metodo che accetta il **startRecord** e **maxRecords** parametri, incrementare l'indice corrente di record da le dimensioni di pagina e il riempimento della tabella. Tenere presente che il server di database restituisce i risultati di query completa anche se solo una pagina di record è stato aggiunto per il **set di dati**. Nell'esempio di codice seguente i contenuti delle tabelle vengono cancellati prima che tali tabelle siano compilate con la pagina successiva di dati. Per ridurre i percorsi al server database, è possibile archiviare in una cache locale un determinato numero di righe restituite.  
  
```vb  
currentIndex = currentIndex + pageSize  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders")  
```  
  
```csharp  
currentIndex += pageSize;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, currentIndex, pageSize, "Orders");  
```  
  
 Per restituire la pagina successiva di record senza che il server database restituisca l'intera query, specificare dei criteri restrittivi per l'istruzione SELECT. Poiché nell'esempio precedente l'ultimo record restituito viene conservato, è possibile usare tale record nella clausola WHERE per specificare un punto di partenza per la query, come illustrato nel seguente esempio di codice.  
  
```vb  
orderSQL = "SELECT TOP " & pageSize & _  
  " * FROM Orders WHERE OrderID > " & lastRecord & " ORDER BY OrderID"  
adapter.SelectCommand.CommandText = orderSQL  
  
dataSet.Tables("Orders").Rows.Clear()  
  
adapter.Fill(dataSet, "Orders")  
```  
  
```csharp  
orderSQL = "SELECT TOP " + pageSize +   
  " * FROM Orders WHERE OrderID > " + lastRecord + " ORDER BY OrderID";  
adapter.SelectCommand.CommandText = orderSQL;  
  
dataSet.Tables["Orders"].Rows.Clear();  
  
adapter.Fill(dataSet, "Orders");  
```  
  
## <a name="see-also"></a>Vedere anche  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)

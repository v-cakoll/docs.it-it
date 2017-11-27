---
title: Spostarsi tra il risultato delle query
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
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b4a51eec840b74d04aaab97226191b2ed30d8826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="paging-through-a-query-result"></a>Spostarsi tra il risultato delle query
Il paging del risultato di una query corrisponde al processo di restituzione dei risultati di una query in subset di dati di dimensioni inferiori o pagine. Si tratta di una tecnica comunemente usata per la visualizzazione di risultati in blocchi di dimensioni ridotte e di facile gestione.  
  
 Il **DataAdapter** fornisce una funzionalità per la restituzione solo una pagina di dati, tramite gli overload del **riempimento** metodo. Tuttavia, potrebbe non essere la scelta migliore per il paging dei risultati di query di grandi dimensioni perché, sebbene il **DataAdapter** riempie la destinazione <xref:System.Data.DataTable> o <xref:System.Data.DataSet> utilizzando solo i record richiesti, le risorse per restituire il intera query sono ancora utilizzati. Per restituire una pagina di dati da un'origine dati senza usare le risorse per la restituzione dell'intera query, specificare dei criteri aggiuntivi per la query, in modo che vengano restituite solo le righe necessarie.  
  
 Utilizzare il **riempimento** per restituire una pagina di dati, specificare un **startRecord** parametro, per il primo record nella pagina di dati e un **maxRecords** parametro, per il numero di record nella pagina di dati.  
  
 Esempio di codice seguente viene illustrato come utilizzare il **riempimento** per restituire la prima pagina del risultato della query in cui le dimensioni di pagina corrisponde a cinque record.  
  
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
  
 Nell'esempio precedente, il **DataSet** viene compilato solo con cinque record, ma l'intero **ordini** viene restituita una tabella. Per riempire il **DataSet** con gli stessi cinque record, ma restituire solo cinque record, utilizzato il primo livello e clausole WHERE nell'istruzione SQL, come nell'esempio di codice seguente.  
  
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
  
 Per restituire la pagina successiva di record mediante il metodo di overload di **riempimento** metodo che accetta il **startRecord** e **maxRecords** parametri, incrementare l'indice di record corrente da le dimensioni di pagina e il riempimento della tabella. Ricordare che il server di database restituisce i risultati dell'intera query, anche se viene aggiunta solo una pagina di record di **DataSet**. Nell'esempio di codice seguente i contenuti delle tabelle vengono cancellati prima che tali tabelle siano compilate con la pagina successiva di dati. Per ridurre i percorsi al server database, è possibile archiviare in una cache locale un determinato numero di righe restituite.  
  
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
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)

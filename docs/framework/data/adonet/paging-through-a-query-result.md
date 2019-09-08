---
title: Spostarsi tra il risultato delle query
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 1dbaa159314bf7bb05ff75287f601f619834fd7c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794620"
---
# <a name="paging-through-a-query-result"></a>Spostarsi tra il risultato delle query
Il paging del risultato di una query corrisponde al processo di restituzione dei risultati di una query in subset di dati di dimensioni inferiori o pagine. Si tratta di una tecnica comunemente usata per la visualizzazione di risultati in blocchi di dimensioni ridotte e di facile gestione.  
  
 **DataAdapter** fornisce una funzionalità per restituire solo una pagina di dati, tramite gli overload del metodo **Fill** . Tuttavia, questo potrebbe non essere la scelta migliore per il paging dei risultati di query di grandi dimensioni perché, sebbene l'oggetto <xref:System.Data.DataTable> DataAdapter <xref:System.Data.DataSet> riempia la destinazione o solo i record richiesti, vengono ancora utilizzate le risorse per restituire l'intera query. . Per restituire una pagina di dati da un'origine dati senza usare le risorse per la restituzione dell'intera query, specificare dei criteri aggiuntivi per la query, in modo che vengano restituite solo le righe necessarie.  
  
 Per usare il metodo **Fill** per restituire una pagina di dati, specificare un parametro **startRecord** , per il primo record nella pagina di dati e un parametro **maxRecords** per il numero di record nella pagina di dati.  
  
 Nell'esempio di codice seguente viene illustrato come utilizzare il metodo **Fill** per restituire la prima pagina di un risultato della query in cui la dimensione della pagina è cinque record.  
  
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
  
 Nell'esempio precedente, il **set di dati** viene riempito solo con cinque record, ma viene restituita l'intera tabella **Orders** . Per riempire il **set** di dati con gli stessi cinque record, ma restituire solo cinque record, usare le clausole TOP e WHERE nell'istruzione SQL, come nell'esempio di codice seguente.  
  
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
  
 Per restituire la pagina successiva di record utilizzando l'overload del metodo **Fill** che accetta i parametri **startRecord** e **maxRecords** , incrementare l'indice del record corrente in base alle dimensioni della pagina e compilare la tabella. Tenere presente che il server di database restituisce l'intero risultato della query anche se al **set di dati**viene aggiunta solo una pagina di record. Nell'esempio di codice seguente i contenuti delle tabelle vengono cancellati prima che tali tabelle siano compilate con la pagina successiva di dati. Per ridurre i percorsi al server database, è possibile archiviare in una cache locale un determinato numero di righe restituite.  
  
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

- [DataAdapter e DataReader](dataadapters-and-datareaders.md)
- [Panoramica di ADO.NET](ado-net-overview.md)

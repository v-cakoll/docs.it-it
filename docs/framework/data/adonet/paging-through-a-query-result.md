---
title: Spostarsi tra il risultato delle query
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa360c46-e5f8-411e-a711-46997771133d
ms.openlocfilehash: 2e7fb97e5c0cb42deff43c411f47e8d30e2257ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149388"
---
# <a name="paging-through-a-query-result"></a>Spostarsi tra il risultato delle query
Il paging del risultato di una query corrisponde al processo di restituzione dei risultati di una query in subset di dati di dimensioni inferiori o pagine. Si tratta di una tecnica comunemente usata per la visualizzazione di risultati in blocchi di dimensioni ridotte e di facile gestione.  
  
 Il **DataAdapter** fornisce una funzionalità per la restituzione solo di una pagina di dati, tramite overload del **Fill** metodo. Tuttavia, questa potrebbe non essere la scelta migliore per il paging dei <xref:System.Data.DataTable> <xref:System.Data.DataSet> risultati di query di grandi dimensioni perché, anche se il **DataAdapter** riempie la destinazione o solo con i record richiesti, le risorse per restituire l'intera query vengono ancora utilizzate. Per restituire una pagina di dati da un'origine dati senza usare le risorse per la restituzione dell'intera query, specificare dei criteri aggiuntivi per la query, in modo che vengano restituite solo le righe necessarie.  
  
 Per utilizzare **il** Fill metodo per restituire una pagina di dati, specificare un **startRecord** parametro, per il primo record nella pagina di dati e un **maxRecords** parametro, per il numero di record nella pagina di dati.  
  
 Esempio di codice seguente viene illustrato come utilizzare il **Fill** metodo per restituire la prima pagina di un risultato di query in cui la dimensione della pagina è cinque record.  
  
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
  
 Nell'esempio precedente, il **DataSet** viene compilato solo con cinque record, ma viene restituita l'intera tabella **Orders.** Per riempire il **DataSet** con gli stessi cinque record, ma restituire solo cinque record, utilizzare le clausole TOP e WHERE nell'istruzione SQL, come nell'esempio di codice seguente.  
  
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
  
 Per restituire la pagina di record successiva utilizzando l'overload del metodo **Fill** che accetta i parametri **startRecord** e **maxRecords,** incrementare l'indice del record corrente in base alle dimensioni della pagina e riempire la tabella. Tenere presente che il server di database restituisce l'intero risultato della query anche se al **DataSet**viene aggiunta una sola pagina di record . Nell'esempio di codice seguente i contenuti delle tabelle vengono cancellati prima che tali tabelle siano compilate con la pagina successiva di dati. Per ridurre i percorsi al server database, è possibile archiviare in una cache locale un determinato numero di righe restituite.  
  
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

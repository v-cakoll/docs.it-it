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
# <a name="paging-through-a-query-result"></a><span data-ttu-id="7c53b-102">Spostarsi tra il risultato delle query</span><span class="sxs-lookup"><span data-stu-id="7c53b-102">Paging Through a Query Result</span></span>
<span data-ttu-id="7c53b-103">Il paging del risultato di una query corrisponde al processo di restituzione dei risultati di una query in subset di dati di dimensioni inferiori o pagine.</span><span class="sxs-lookup"><span data-stu-id="7c53b-103">Paging through a query result is the process of returning the results of a query in smaller subsets of data, or pages.</span></span> <span data-ttu-id="7c53b-104">Si tratta di una tecnica comunemente usata per la visualizzazione di risultati in blocchi di dimensioni ridotte e di facile gestione.</span><span class="sxs-lookup"><span data-stu-id="7c53b-104">This is a common practice for displaying results to a user in small, easy-to-manage chunks.</span></span>  
  
 <span data-ttu-id="7c53b-105">Il **DataAdapter** fornisce una funzionalità per la restituzione solo di una pagina di dati, tramite overload del **Fill** metodo.</span><span class="sxs-lookup"><span data-stu-id="7c53b-105">The **DataAdapter** provides a facility for returning only a page of data, through overloads of the **Fill** method.</span></span> <span data-ttu-id="7c53b-106">Tuttavia, questa potrebbe non essere la scelta migliore per il paging dei <xref:System.Data.DataTable> <xref:System.Data.DataSet> risultati di query di grandi dimensioni perché, anche se il **DataAdapter** riempie la destinazione o solo con i record richiesti, le risorse per restituire l'intera query vengono ancora utilizzate.</span><span class="sxs-lookup"><span data-stu-id="7c53b-106">However, this might not be the best choice for paging through large query results because, although the **DataAdapter** fills the target <xref:System.Data.DataTable> or <xref:System.Data.DataSet> with only the requested records, the resources to return the entire query are still used.</span></span> <span data-ttu-id="7c53b-107">Per restituire una pagina di dati da un'origine dati senza usare le risorse per la restituzione dell'intera query, specificare dei criteri aggiuntivi per la query, in modo che vengano restituite solo le righe necessarie.</span><span class="sxs-lookup"><span data-stu-id="7c53b-107">To return a page of data from a data source without using the resources to return the entire query, specify additional criteria for your query that reduce the rows returned to only those required.</span></span>  
  
 <span data-ttu-id="7c53b-108">Per utilizzare **il** Fill metodo per restituire una pagina di dati, specificare un **startRecord** parametro, per il primo record nella pagina di dati e un **maxRecords** parametro, per il numero di record nella pagina di dati.</span><span class="sxs-lookup"><span data-stu-id="7c53b-108">To use the **Fill** method to return a page of data, specify a **startRecord** parameter, for the first record in the page of data, and a **maxRecords** parameter, for the number of records in the page of data.</span></span>  
  
 <span data-ttu-id="7c53b-109">Esempio di codice seguente viene illustrato come utilizzare il **Fill** metodo per restituire la prima pagina di un risultato di query in cui la dimensione della pagina è cinque record.</span><span class="sxs-lookup"><span data-stu-id="7c53b-109">The following code example shows how to use the **Fill** method to return the first page of a query result where the page size is five records.</span></span>  
  
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
  
 <span data-ttu-id="7c53b-110">Nell'esempio precedente, il **DataSet** viene compilato solo con cinque record, ma viene restituita l'intera tabella **Orders.**</span><span class="sxs-lookup"><span data-stu-id="7c53b-110">In the previous example, the **DataSet** is only filled with five records, but the entire **Orders** table is returned.</span></span> <span data-ttu-id="7c53b-111">Per riempire il **DataSet** con gli stessi cinque record, ma restituire solo cinque record, utilizzare le clausole TOP e WHERE nell'istruzione SQL, come nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7c53b-111">To fill the **DataSet** with those same five records, but only return five records, use the TOP and WHERE clauses in your SQL statement, as in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="7c53b-112">Notare che, quando si esegue in questo modo il paging dei risultati della query, è necessario conservare l'identificatore univoco in base al quale sono ordinate le righe, in modo da passare l'identificatore univoco al comando per restituire la pagina successiva di record, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7c53b-112">Note that, when paging through the query results in this way, you must preserve the unique identifier that orders the rows, in order to pass the unique ID to the command to return the next page of records, as shown in the following code example.</span></span>  
  
```vb  
Dim lastRecord As String = _  
  dataSet.Tables("Orders").Rows(pageSize - 1)("OrderID").ToString()  
```  
  
```csharp  
string lastRecord =
  dataSet.Tables["Orders"].Rows[pageSize - 1]["OrderID"].ToString();  
```  
  
 <span data-ttu-id="7c53b-113">Per restituire la pagina di record successiva utilizzando l'overload del metodo **Fill** che accetta i parametri **startRecord** e **maxRecords,** incrementare l'indice del record corrente in base alle dimensioni della pagina e riempire la tabella.</span><span class="sxs-lookup"><span data-stu-id="7c53b-113">To return the next page of records using the overload of the **Fill** method that takes the **startRecord** and **maxRecords** parameters, increment the current record index by the page size and fill the table.</span></span> <span data-ttu-id="7c53b-114">Tenere presente che il server di database restituisce l'intero risultato della query anche se al **DataSet**viene aggiunta una sola pagina di record .</span><span class="sxs-lookup"><span data-stu-id="7c53b-114">Remember that the database server returns the entire query results even though only one page of records is added to the **DataSet**.</span></span> <span data-ttu-id="7c53b-115">Nell'esempio di codice seguente i contenuti delle tabelle vengono cancellati prima che tali tabelle siano compilate con la pagina successiva di dati.</span><span class="sxs-lookup"><span data-stu-id="7c53b-115">In the following code example, the table rows are cleared before they are filled with the next page of data.</span></span> <span data-ttu-id="7c53b-116">Per ridurre i percorsi al server database, è possibile archiviare in una cache locale un determinato numero di righe restituite.</span><span class="sxs-lookup"><span data-stu-id="7c53b-116">You might want to preserve a certain number of returned rows in a local cache to reduce trips to the database server.</span></span>  
  
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
  
 <span data-ttu-id="7c53b-117">Per restituire la pagina successiva di record senza che il server database restituisca l'intera query, specificare dei criteri restrittivi per l'istruzione SELECT.</span><span class="sxs-lookup"><span data-stu-id="7c53b-117">To return the next page of records without having the database server return the entire query, specify restrictive criteria to the SELECT statement.</span></span> <span data-ttu-id="7c53b-118">Poiché nell'esempio precedente l'ultimo record restituito viene conservato, è possibile usare tale record nella clausola WHERE per specificare un punto di partenza per la query, come illustrato nel seguente esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="7c53b-118">Because the preceding example preserved the last record returned, you can use it in the WHERE clause to specify a starting point for the query, as shown in the following code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7c53b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c53b-119">See also</span></span>

- [<span data-ttu-id="7c53b-120">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="7c53b-120">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="7c53b-121">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7c53b-121">ADO.NET Overview</span></span>](ado-net-overview.md)

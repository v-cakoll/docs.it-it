---
title: Aggiornamento di dati in un'origine dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
ms.openlocfilehash: 18bb03e17b19243ee1bc6e3f7ebd70afb4d4c60b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174446"
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="51dc6-102">Aggiornamento di dati in un'origine dati</span><span class="sxs-lookup"><span data-stu-id="51dc6-102">Updating Data in a Data Source</span></span>
<span data-ttu-id="51dc6-103">Le istruzioni SQL che modificano i dati, ad esempio INSERT, UPDATE o DELETE, non restituiscono righe.</span><span class="sxs-lookup"><span data-stu-id="51dc6-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="51dc6-104">Analogamente, molte stored procedure eseguono un'operazione ma non restituiscono righe.</span><span class="sxs-lookup"><span data-stu-id="51dc6-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="51dc6-105">Per eseguire comandi che non restituiscono righe, creare un oggetto **Command** con il comando SQL appropriato e un **oggetto Connection**, inclusi i **parametri**necessari.</span><span class="sxs-lookup"><span data-stu-id="51dc6-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="51dc6-106">Eseguire il comando con il metodo **ExecuteNonQuery** dell'oggetto **Command.**</span><span class="sxs-lookup"><span data-stu-id="51dc6-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="51dc6-107">Il **metodo ExecuteNonQuery** restituisce un numero intero che rappresenta il numero di righe interessate dall'istruzione o dalla stored procedure eseguita.</span><span class="sxs-lookup"><span data-stu-id="51dc6-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="51dc6-108">Se si eseguono più istruzioni, il valore restituito sarà la somma dei record interessati da ognuna delle istruzioni eseguite.</span><span class="sxs-lookup"><span data-stu-id="51dc6-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51dc6-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="51dc6-109">Example</span></span>  
 <span data-ttu-id="51dc6-110">Nell'esempio di codice riportato di seguito viene eseguita un'istruzione INSERT per inserire un record in un database utilizzando **ExecuteNonQuery**.</span><span class="sxs-lookup"><span data-stu-id="51dc6-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 <span data-ttu-id="51dc6-111">Nell'esempio di codice riportato di seguito viene eseguita la stored procedure creata dal codice di esempio in [Esecuzione di operazioni](performing-catalog-operations.md)di catalogo .</span><span class="sxs-lookup"><span data-stu-id="51dc6-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](performing-catalog-operations.md).</span></span> <span data-ttu-id="51dc6-112">Nessuna riga viene restituita dalla stored procedure, pertanto viene utilizzato il metodo **ExecuteNonQuery,** ma la stored procedure riceve un parametro di input e restituisce un parametro di output e un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="51dc6-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="51dc6-113">Per <xref:System.Data.OleDb.OleDbCommand> l'oggetto, il parametro **ReturnValue** deve essere aggiunto prima all'insieme **Parameters.**</span><span class="sxs-lookup"><span data-stu-id="51dc6-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="51dc6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51dc6-114">See also</span></span>

- [<span data-ttu-id="51dc6-115">Uso di comandi per modificare i dati</span><span class="sxs-lookup"><span data-stu-id="51dc6-115">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="51dc6-116">Aggiornamento di origini dati con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="51dc6-116">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="51dc6-117">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="51dc6-117">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="51dc6-118">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="51dc6-118">ADO.NET Overview</span></span>](ado-net-overview.md)

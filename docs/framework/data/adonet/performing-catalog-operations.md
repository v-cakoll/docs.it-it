---
title: Esecuzione di operazioni di catalogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: 1b13d1e3e210964331a710512876bd1f8503069e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648076"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="e4097-102">Esecuzione di operazioni di catalogo</span><span class="sxs-lookup"><span data-stu-id="e4097-102">Performing Catalog Operations</span></span>
<span data-ttu-id="e4097-103">Per eseguire un comando che modifica un database o un catalogo, ad esempio l'istruzione CREATE TABLE o CREATE PROCEDURE, creare un **comandi** usando le istruzioni SQL appropriate dell'oggetto e una **connessione** oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4097-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="e4097-104">Eseguire il comando con il **ExecuteNonQuery** metodo per il **comando** oggetto.</span><span class="sxs-lookup"><span data-stu-id="e4097-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="e4097-105">Nell'esempio di codice seguente viene creata una stored procedure in un database Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4097-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +   
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +   
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +   
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4097-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4097-106">See also</span></span>
- [<span data-ttu-id="e4097-107">Uso di comandi per modificare i dati</span><span class="sxs-lookup"><span data-stu-id="e4097-107">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [<span data-ttu-id="e4097-108">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="e4097-108">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="e4097-109">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="e4097-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

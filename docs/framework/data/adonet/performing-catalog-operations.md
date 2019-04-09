---
title: Esecuzione di operazioni di catalogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: beb5d2db898df1c98662d53190ac1432acc746e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141453"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="436f8-102">Esecuzione di operazioni di catalogo</span><span class="sxs-lookup"><span data-stu-id="436f8-102">Performing Catalog Operations</span></span>
<span data-ttu-id="436f8-103">Per eseguire un comando che modifica un database o un catalogo, ad esempio l'istruzione CREATE TABLE o CREATE PROCEDURE, creare un **comandi** usando le istruzioni SQL appropriate dell'oggetto e una **connessione** oggetto.</span><span class="sxs-lookup"><span data-stu-id="436f8-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="436f8-104">Eseguire il comando con il **ExecuteNonQuery** metodo per il **comando** oggetto.</span><span class="sxs-lookup"><span data-stu-id="436f8-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="436f8-105">Nell'esempio di codice seguente viene creata una stored procedure in un database Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="436f8-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="436f8-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="436f8-106">See also</span></span>

- [<span data-ttu-id="436f8-107">Utilizzo di comandi per modificare i dati</span><span class="sxs-lookup"><span data-stu-id="436f8-107">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [<span data-ttu-id="436f8-108">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="436f8-108">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="436f8-109">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="436f8-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

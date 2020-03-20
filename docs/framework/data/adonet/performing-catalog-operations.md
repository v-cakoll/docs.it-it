---
title: Esecuzione di operazioni di catalogo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: bedeb4e9c510a3feeedc038e9c4cef6c4721e345
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149245"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="b7d72-102">Esecuzione di operazioni di catalogo</span><span class="sxs-lookup"><span data-stu-id="b7d72-102">Performing Catalog Operations</span></span>
<span data-ttu-id="b7d72-103">Per eseguire un comando per modificare un database o un catalogo, ad esempio l'istruzione CREATE TABLE o CREATE PROCEDURE, creare un oggetto **Command** utilizzando le istruzioni SQL appropriate e un oggetto **Connection.**</span><span class="sxs-lookup"><span data-stu-id="b7d72-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="b7d72-104">Eseguire il comando con il metodo **ExecuteNonQuery** dell'oggetto **Command.**</span><span class="sxs-lookup"><span data-stu-id="b7d72-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="b7d72-105">Nell'esempio di codice seguente viene creata una stored procedure in un database Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7d72-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7d72-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7d72-106">See also</span></span>

- [<span data-ttu-id="b7d72-107">Uso di comandi per modificare i dati</span><span class="sxs-lookup"><span data-stu-id="b7d72-107">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="b7d72-108">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="b7d72-108">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="b7d72-109">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b7d72-109">ADO.NET Overview</span></span>](ado-net-overview.md)

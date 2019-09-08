---
title: Raccolte di schemi e GetSchema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: 4ac0216ce2965d555f7283ba66a085ea9d7cac3c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783834"
---
# <a name="getschema-and-schema-collections"></a><span data-ttu-id="9d7de-102">Raccolte di schemi e GetSchema</span><span class="sxs-lookup"><span data-stu-id="9d7de-102">GetSchema and Schema Collections</span></span>
<span data-ttu-id="9d7de-103">Le classi di **connessione** in ognuno dei provider .NET Framework gestiti implementano un metodo **GetSchema** utilizzato per recuperare le informazioni sullo schema relative al database attualmente connesso e le informazioni sullo schema restituite dalla classe  **Il metodo GetSchema** viene visualizzato sotto forma di <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="9d7de-103">The **Connection** classes in each of the .NET Framework managed providers implement a **GetSchema** method which is used to retrieve schema information about the database that is currently connected, and the schema information returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="9d7de-104">Il metodo **GetSchema** è un metodo di overload che fornisce parametri facoltativi per specificare la raccolta di schemi da restituire e per limitare la quantità di informazioni restituite.</span><span class="sxs-lookup"><span data-stu-id="9d7de-104">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
## <a name="specifying-the-schema-collections"></a><span data-ttu-id="9d7de-105">Specifica di raccolte di schemi</span><span class="sxs-lookup"><span data-stu-id="9d7de-105">Specifying the Schema Collections</span></span>  
 <span data-ttu-id="9d7de-106">Il primo parametro facoltativo del metodo **GetSchema** è il nome della raccolta specificato come stringa.</span><span class="sxs-lookup"><span data-stu-id="9d7de-106">The first optional parameter of the **GetSchema** method is the collection name which is specified as a string.</span></span> <span data-ttu-id="9d7de-107">Sono disponibili due tipi di raccolte di schemi: raccolte di schemi comuni a tutti i provider e raccolte di schemi specifici, ovvero schemi specifici per ciascun provider.</span><span class="sxs-lookup"><span data-stu-id="9d7de-107">There are two types of schema collections: common schema collections that are common to all providers, and specific schema collections which are specific to each provider.</span></span>  
  
 <span data-ttu-id="9d7de-108">È possibile eseguire una query su un provider gestito .NET Framework per determinare l'elenco delle raccolte di schemi supportate chiamando il metodo **GetSchema** senza argomenti oppure con il nome della raccolta di schemi "MetaDataCollections".</span><span class="sxs-lookup"><span data-stu-id="9d7de-108">You can query a .NET Framework managed provider to determine the list of supported schema collections by calling the **GetSchema** method with no arguments, or with the schema collection name "MetaDataCollections".</span></span> <span data-ttu-id="9d7de-109">In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco delle raccolte di schemi supportati, il numero delle restrizioni supportate da ciascuna raccolta e il numero di parti identificatore usate.</span><span class="sxs-lookup"><span data-stu-id="9d7de-109">This will return a <xref:System.Data.DataTable> with a list of the supported schema collections, the number of restrictions that they each support, and the number of identifier parts that they use.</span></span>  
  
### <a name="retrieving-schema-collections-example"></a><span data-ttu-id="9d7de-110">Esempio di recupero di raccolte di schemi</span><span class="sxs-lookup"><span data-stu-id="9d7de-110">Retrieving Schema Collections Example</span></span>  
 <span data-ttu-id="9d7de-111">Negli esempi seguenti viene illustrato come utilizzare il <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> metodo della .NET Framework provider di dati per la classe SQL Server <xref:System.Data.SqlClient.SqlConnection> per recuperare informazioni sullo schema relative a tutte le tabelle contenute nel database di esempio **AdventureWorks** :</span><span class="sxs-lookup"><span data-stu-id="9d7de-111">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
   Sub Main()  
      Dim connectionString As String = GetConnectionString()  
      Using connection As New SqlConnection(connectionString)  
         'Connect to the database then retrieve the schema information.  
         connection.Open()  
         Dim table As DataTable = connection.GetSchema("Tables")  
  
         ' Display the contents of the table.  
         DisplayData(table)  
         Console.WriteLine("Press any key to continue.")  
         Console.ReadKey()  
      End Using  
   End Sub  
  
   Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,    
      ' you can retrieve it from a configuration file.  
      Return "Data Source=(local);Database=AdventureWorks;" _  
         & "Integrated Security=true;"  
   End Function  
  
   Private Sub DisplayData(ByVal table As DataTable)  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
   End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
  string connectionString = GetConnectionString();  
  using (SqlConnection connection = new SqlConnection(connectionString))  
  {  
   // Connect to the database then retrieve the schema information.  
   connection.Open();  
   DataTable table = connection.GetSchema("Tables");  
  
   // Display the contents of the table.  
   DisplayData(table);  
   Console.WriteLine("Press any key to continue.");  
   Console.ReadKey();  
   }  
 }  
  
  private static string GetConnectionString()  
  {  
   // To avoid storing the connection string in your code,  
   // you can retrieve it from a configuration file.  
   return "Data Source=(local);Database=AdventureWorks;" +  
      "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9d7de-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d7de-112">See also</span></span>

- [<span data-ttu-id="9d7de-113">Recupero di informazioni sullo schema del database</span><span class="sxs-lookup"><span data-stu-id="9d7de-113">Retrieving Database Schema Information</span></span>](retrieving-database-schema-information.md)
- [<span data-ttu-id="9d7de-114">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9d7de-114">ADO.NET Overview</span></span>](ado-net-overview.md)

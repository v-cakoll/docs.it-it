---
title: Raccolte di schemi e GetSchema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
ms.openlocfilehash: e18c23e9bbec97a64110aba6eb7241761ecece06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149557"
---
# <a name="getschema-and-schema-collections"></a>Raccolte di schemi e GetSchema
Le classi **Connection** in ognuno dei provider gestiti di .NET Framework implementano un metodo **GetSchema** utilizzato per recuperare le informazioni sullo schema <xref:System.Data.DataTable>sul database attualmente connesso e le informazioni sullo schema restituite dal metodo **GetSchema** vengono fornite sotto forma di oggetto . Il **GetSchema** metodo è un metodo di overload che fornisce parametri facoltativi per specificare la raccolta di schemi da restituire e limitare la quantità di informazioni restituite.  
  
## <a name="specifying-the-schema-collections"></a>Specifica di raccolte di schemi  
 Il primo parametro facoltativo del **GetSchema** metodo è il nome della raccolta che viene specificato come stringa. Sono disponibili due tipi di raccolte di schemi: raccolte di schemi comuni a tutti i provider e raccolte di schemi specifici, ovvero schemi specifici per ciascun provider.  
  
 È possibile eseguire una query su un provider gestito .NET Framework per determinare l'elenco delle raccolte di schemi supportate chiamando il metodo **GetSchema** senza argomenti o con il nome della raccolta di schemi "MetaDataCollections". In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco delle raccolte di schemi supportati, il numero delle restrizioni supportate da ciascuna raccolta e il numero di parti identificatore usate.  
  
### <a name="retrieving-schema-collections-example"></a>Esempio di recupero di raccolte di schemi  
 Negli esempi seguenti viene <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> illustrato come utilizzare il metodo del <xref:System.Data.SqlClient.SqlConnection> provider di dati .NET Framework per la classe SQL Server per recuperare informazioni sullo schema relative a tutte le tabelle contenute nel database di esempio **AdventureWorks:**  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Recupero di informazioni sullo schema del database](retrieving-database-schema-information.md)
- [Panoramica di ADO.NET](ado-net-overview.md)

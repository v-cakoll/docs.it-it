---
title: Raccolte di schemi e GetSchema
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
ms.assetid: 7ab93b89-1221-427c-84ad-04803b3c64b4
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d982964b596528b091f5367edd38e0cee5f923c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getschema-and-schema-collections"></a>Raccolte di schemi e GetSchema
Il **connessione** classi in ogni implementazione di provider gestiti di .NET Framework un **GetSchema** metodo utilizzato per recuperare informazioni sullo schema relative al database che è attualmente connesso e le informazioni sullo schema restituite dal **GetSchema** metodo disponibile sotto forma di un <xref:System.Data.DataTable>. Il **GetSchema** è un metodo di overload che fornisce parametri facoltativi per specificare la raccolta di schemi da restituire e per limitare la quantità di informazioni restituite.  
  
## <a name="specifying-the-schema-collections"></a>Specifica di raccolte di schemi  
 Il primo parametro facoltativo del **GetSchema** metodo è il nome della raccolta specificata come una stringa. Sono disponibili due tipi di raccolte di schemi: raccolte di schemi comuni a tutti i provider e raccolte di schemi specifici, ovvero schemi specifici per ciascun provider.  
  
 È possibile eseguire query di un provider gestito .NET Framework per determinare l'elenco delle raccolte di schemi supportati chiamando il **GetSchema** metodo senza argomenti oppure con il nome di raccolta di schemi "MetaDataCollections". In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco delle raccolte di schemi supportati, il numero delle restrizioni supportate da ciascuna raccolta e il numero di parti identificatore usate.  
  
### <a name="retrieving-schema-collections-example"></a>Esempio di recupero di raccolte di schemi  
 Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> metodo del Provider di dati .NET Framework per SQL Server <xref:System.Data.SqlClient.SqlConnection> classe per recuperare informazioni sullo schema relative a tutte le tabelle contenute nel **AdventureWorks**database di esempio:  
  
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
 [Recupero di informazioni sullo schema del database](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Polling in applicazioni console
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
ms.assetid: 4ff084d5-5956-4db1-8e18-c5a66b000882
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 781fcd73dc56841eb7eadbf0bd6a0093643e608a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="polling-in-console-applications"></a><span data-ttu-id="ef24d-102">Polling in applicazioni console</span><span class="sxs-lookup"><span data-stu-id="ef24d-102">Polling in Console Applications</span></span>
<span data-ttu-id="ef24d-103">Le operazioni asincrone in ADO.NET consentono di avviare operazioni di database che potrebbero richiedere molto tempo su un singolo thread e di eseguire altre attività su un thread diverso.</span><span class="sxs-lookup"><span data-stu-id="ef24d-103">Asynchronous operations in ADO.NET allow you to initiate time-consuming database operations on one thread while performing other tasks on another thread.</span></span> <span data-ttu-id="ef24d-104">Tuttavia, nella maggior parte degli scenari si raggiungerà un punto in cui l'applicazione non continuerà finché l'operazione di database non è completata.</span><span class="sxs-lookup"><span data-stu-id="ef24d-104">In most scenarios, however, you will eventually reach a point where your application should not continue until the database operation is complete.</span></span> <span data-ttu-id="ef24d-105">In questi casi, risulta utile effettuare il polling dell'operazione asincrona per determinare se l'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ef24d-105">For such cases, it is useful to poll the asynchronous operation to determine whether the operation has completed or not.</span></span>  
  
 <span data-ttu-id="ef24d-106">È possibile usare la proprietà <xref:System.IAsyncResult.IsCompleted%2A> per verificare se l'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ef24d-106">You can use the <xref:System.IAsyncResult.IsCompleted%2A> property to find out whether or not the operation has completed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef24d-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef24d-107">Example</span></span>  
 <span data-ttu-id="ef24d-108">La seguente applicazione console Aggiorna dati all'interno di **AdventureWorks** database di esempio, in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="ef24d-108">The following console application updates data within the **AdventureWorks** sample database, doing its work asynchronously.</span></span> <span data-ttu-id="ef24d-109">Per emulare un processo a esecuzione prolungata, in questo esempio viene inserita un'istruzione WAITFOR nel testo del comando.</span><span class="sxs-lookup"><span data-stu-id="ef24d-109">In order to emulate a long-running process, this example inserts a WAITFOR statement in the command text.</span></span> <span data-ttu-id="ef24d-110">In genere, non si consiglia di rallentare l'esecuzione dei comandi, ma in questo caso ciò consente di illustrare in modo semplice il comportamento asincrono.</span><span class="sxs-lookup"><span data-stu-id="ef24d-110">Normally, you would not try to make your commands run slower, but doing so in this case makes it easier to demonstrate asynchronous behavior.</span></span>  
  
```vb  
Imports System  
Imports System.Data.SqlClient  
  
Module Module1  
  
    Sub Main()  
        ' The WAITFOR statement simply adds enough time to prove the   
        ' asynchronous nature of the command.  
        Dim commandText As String = _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint + 1 " & _  
         "WHERE ReorderPoint Is Not Null;" & _  
         "WAITFOR DELAY '0:0:3';" & _  
         "UPDATE Production.Product " & _  
         "SET ReorderPoint = ReorderPoint - 1 " & _  
         "WHERE ReorderPoint Is Not Null"  
  
        RunCommandAsynchronously(commandText, GetConnectionString())  
  
        Console.WriteLine("Press Enter to continue.")  
        Console.ReadLine()  
    End Sub  
  
    Private Sub RunCommandAsynchronously( _  
     ByVal commandText As String, ByVal connectionString As String)  
  
        ' Given command text and connection string, asynchronously   
        ' execute the specified command against the connection. For   
        ' this example, the code displays an indicator as it's working,   
        ' verifying the asynchronous behavior.   
        Using connection As New SqlConnection(connectionString)  
            Try  
                Dim count As Integer = 0  
                Dim command As New SqlCommand(commandText, connection)  
                connection.Open()  
                Dim result As IAsyncResult = _  
                 command.BeginExecuteNonQuery()  
                While Not result.IsCompleted  
                    Console.WriteLine("Waiting ({0})", count)  
                    ' Wait for 1/10 second, so the counter  
                    ' doesn't consume all available resources   
                    ' on the main thread.  
                    Threading.Thread.Sleep(100)  
                    count += 1  
                End While  
                Console.WriteLine( _  
                 "Command complete. Affected {0} rows.", _  
                 command.EndExecuteNonQuery(result))  
            Catch ex As SqlException  
                Console.WriteLine("Error ({0}): {1}", _  
                 ex.Number, ex.Message)  
            Catch ex As InvalidOperationException  
                Console.WriteLine("Error: {0}", ex.Message)  
            Catch ex As Exception  
                ' You might want to pass these errors  
                ' back out to the caller.  
                Console.WriteLine("Error: {0}", ex.Message)  
            End Try  
        End Using  
    End Sub  
  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,              
        ' you can retrieve it from a configuration file.   
  
        ' If you have not included "Asynchronous Processing=true"   
        ' in the connection string, the command will not be able  
        ' to execute asynchronously.  
        Return "Data Source=(local);Integrated Security=SSPI;" & _  
          "Initial Catalog=AdventureWorks; " & _  
          "Asynchronous Processing=true"  
    End Function  
End Module   
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Class1  
{  
    [STAThread]  
    static void Main()  
    {  
        // The WAITFOR statement simply adds enough time to   
        // prove the asynchronous nature of the command.  
  
        string commandText =  
          "UPDATE Production.Product SET ReorderPoint = " +  
          "ReorderPoint + 1 " +  
          "WHERE ReorderPoint Is Not Null;" +  
          "WAITFOR DELAY '0:0:3';" +  
          "UPDATE Production.Product SET ReorderPoint = " +  
          "ReorderPoint - 1 " +  
          "WHERE ReorderPoint Is Not Null";  
  
        RunCommandAsynchronously(  
            commandText, GetConnectionString());  
  
        Console.WriteLine("Press Enter to continue.");  
        Console.ReadLine();  
    }  
  
    private static void RunCommandAsynchronously(  
      string commandText, string connectionString)  
    {  
        // Given command text and connection string, asynchronously  
        // execute the specified command against the connection.   
        // For this example, the code displays an indicator as it's   
        // working, verifying the asynchronous behavior.   
        using (SqlConnection connection =  
          new SqlConnection(connectionString))  
        {  
            try  
            {  
                int count = 0;  
                SqlCommand command =   
                    new SqlCommand(commandText, connection);  
                connection.Open();  
  
                IAsyncResult result =   
                    command.BeginExecuteNonQuery();  
                while (!result.IsCompleted)  
                {  
                    Console.WriteLine(  
                                    "Waiting ({0})", count++);  
                    // Wait for 1/10 second, so the counter  
                    // doesn't consume all available   
                    // resources on the main thread.  
                    System.Threading.Thread.Sleep(100);  
                }  
                Console.WriteLine(  
                    "Command complete. Affected {0} rows.",  
                command.EndExecuteNonQuery(result));  
            }  
            catch (SqlException ex)  
            {  
                Console.WriteLine("Error ({0}): {1}",   
                    ex.Number, ex.Message);  
            }  
            catch (InvalidOperationException ex)  
            {  
                Console.WriteLine("Error: {0}", ex.Message);  
            }  
            catch (Exception ex)  
            {  
                // You might want to pass these errors  
                // back out to the caller.  
                Console.WriteLine("Error: {0}", ex.Message);  
            }  
        }  
    }  
  
    private static string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,              
        // you can retrieve it from a configuration file.   
  
        // If you have not included "Asynchronous Processing=true"  
        // in the connection string, the command will not be able  
        // to execute asynchronously.  
        return "Data Source=(local);Integrated Security=SSPI;" +  
        "Initial Catalog=AdventureWorks; " +   
        "Asynchronous Processing=true";  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef24d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef24d-111">See Also</span></span>  
 [<span data-ttu-id="ef24d-112">Operazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="ef24d-112">Asynchronous Operations</span></span>](../../../../../docs/framework/data/adonet/sql/asynchronous-operations.md)  
 [<span data-ttu-id="ef24d-113">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="ef24d-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: Programmazione asincrona
ms.date: 10/18/2018
ms.assetid: 85da7447-7125-426e-aa5f-438a290d1f77
ms.openlocfilehash: 7bf492e45a9ebabdd36caa8e21605739bb410695
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937582"
---
# <a name="asynchronous-programming"></a><span data-ttu-id="01cd7-102">Programmazione asincrona</span><span class="sxs-lookup"><span data-stu-id="01cd7-102">Asynchronous Programming</span></span>

<span data-ttu-id="01cd7-103">In questo argomento viene illustrato il supporto per la programmazione asincrona nella .NET Framework provider di dati per SQL Server (SqlClient), inclusi i miglioramenti apportati per supportare la funzionalità di programmazione asincrona introdotta in .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="01cd7-103">This topic discusses support for asynchronous programming in the .NET Framework Data Provider for SQL Server (SqlClient) including enhancements made to support asynchronous programming functionality that was introduced in .NET Framework 4.5.</span></span>

## <a name="legacy-asynchronous-programming"></a><span data-ttu-id="01cd7-104">Programmazione asincrona legacy</span><span class="sxs-lookup"><span data-stu-id="01cd7-104">Legacy Asynchronous Programming</span></span>

<span data-ttu-id="01cd7-105">Prima di .NET Framework 4,5, la programmazione asincrona con SqlClient veniva eseguita con i metodi e la proprietà di connessione `Asynchronous Processing=true` seguenti:</span><span class="sxs-lookup"><span data-stu-id="01cd7-105">Prior to .NET Framework 4.5, asynchronous programming with SqlClient was done with the following methods and the `Asynchronous Processing=true` connection property:</span></span>

1. <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A?displayProperty=nameWithType>

2. <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A?displayProperty=nameWithType>

3. <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A?displayProperty=nameWithType>

<span data-ttu-id="01cd7-106">Questa funzionalità rimane in SqlClient in .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="01cd7-106">This functionality remains in SqlClient in .NET Framework 4.5.</span></span>

> [!TIP]
> <span data-ttu-id="01cd7-107">A partire da .NET Framework 4,5, questi metodi legacy non richiedono più `Asynchronous Processing=true` nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="01cd7-107">Beginning in the .NET Framework 4.5, these legacy methods no longer require `Asynchronous Processing=true` in the connection string.</span></span>

## <a name="asynchronous-programming-features-added-in-net-framework-45"></a><span data-ttu-id="01cd7-108">Funzionalità di programmazione asincrona aggiunte in .NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="01cd7-108">Asynchronous Programming Features Added in .NET Framework 4.5</span></span>

<span data-ttu-id="01cd7-109">La nuova funzionalità di programmazione asincrona fornisce una tecnica semplice per rendere il codice asincrono.</span><span class="sxs-lookup"><span data-stu-id="01cd7-109">The new asynchronous programming feature provides a simple technique to make code asynchronous.</span></span>

<span data-ttu-id="01cd7-110">Per ulteriori informazioni sulla funzionalità di programmazione asincrona introdotta in .NET Framework 4,5, vedere:</span><span class="sxs-lookup"><span data-stu-id="01cd7-110">For more information about the asynchronous programming feature that was introduced in .NET Framework 4.5, see:</span></span>

- [<span data-ttu-id="01cd7-111">Programmazione asincrona in C#</span><span class="sxs-lookup"><span data-stu-id="01cd7-111">Asynchronous programming in C#</span></span>](../../../csharp/async.md)

- [<span data-ttu-id="01cd7-112">Programmazione asincrona con Async e Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01cd7-112">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)

- [<span data-ttu-id="01cd7-113">Uso dei nuovi metodi asincroni di SqlDataReader in .NET 4,5 (parte 1)</span><span class="sxs-lookup"><span data-stu-id="01cd7-113">Using SqlDataReader’s new async methods in .NET 4.5 (Part 1)</span></span>](https://docs.microsoft.com/archive/blogs/adonet/using-sqldatareaders-new-async-methods-in-net-4-5)

- [<span data-ttu-id="01cd7-114">Uso dei nuovi metodi asincroni di SqlDataReader in .NET 4,5 (parte 2)</span><span class="sxs-lookup"><span data-stu-id="01cd7-114">Using SqlDataReader’s new async methods in .NET 4.5 (Part 2)</span></span>](https://docs.microsoft.com/archive/blogs/adonet/using-sqldatareaders-new-async-methods-in-net-4-5-part-2-examples)

<span data-ttu-id="01cd7-115">Quando l'interfaccia utente non risponde o il server non è scalabile, si potrebbe aver bisogno di un codice più asincrono.</span><span class="sxs-lookup"><span data-stu-id="01cd7-115">When your user interface is unresponsive or your server does not scale, it is likely that you need your code to be more asynchronous.</span></span> <span data-ttu-id="01cd7-116">La scrittura di codice asincrono ha richiesto in genere l'installazione di un callback (denominato anche continuazione) per esprimere la logica che si verifica al termine dell'operazione asincrona.</span><span class="sxs-lookup"><span data-stu-id="01cd7-116">Writing asynchronous code has traditionally involved installing a callback (also called continuation) to express the logic that occurs after the asynchronous operation finishes.</span></span> <span data-ttu-id="01cd7-117">Ciò complica la struttura del codice asincrono rispetto al codice sincrono.</span><span class="sxs-lookup"><span data-stu-id="01cd7-117">This complicates the structure of asynchronous code as compared with synchronous code.</span></span>

<span data-ttu-id="01cd7-118">È ora possibile chiamare i metodi asincroni senza usare callback e senza suddividere il codice in più metodi o espressioni lambda.</span><span class="sxs-lookup"><span data-stu-id="01cd7-118">You can now call into asynchronous methods without using callbacks, and without splitting your code across multiple methods or lambda expressions.</span></span>

<span data-ttu-id="01cd7-119">Il modificatore `async` specifica che un metodo è asincrono.</span><span class="sxs-lookup"><span data-stu-id="01cd7-119">The `async` modifier specifies that a method is asynchronous.</span></span> <span data-ttu-id="01cd7-120">Quando si chiama un metodo `async`, viene restituita un'attività.</span><span class="sxs-lookup"><span data-stu-id="01cd7-120">When calling an `async` method, a task is returned.</span></span> <span data-ttu-id="01cd7-121">Quando l'operatore `await` viene applicato a un'attività, il metodo corrente si chiude immediatamente.</span><span class="sxs-lookup"><span data-stu-id="01cd7-121">When the `await` operator is applied to a task, the current method exits immediately.</span></span> <span data-ttu-id="01cd7-122">Al termine dell'attività, l'esecuzione riprende in corrispondenza dello stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="01cd7-122">When the task finishes, execution resumes in the same method.</span></span>

> [!WARNING]
> <span data-ttu-id="01cd7-123">Le chiamate asincrone non sono supportate se in un'applicazione viene inoltre usata la parola chiave della stringa di connessione `Context Connection`.</span><span class="sxs-lookup"><span data-stu-id="01cd7-123">Asynchronous calls are not supported if an application also uses the `Context Connection` connection string keyword.</span></span>

<span data-ttu-id="01cd7-124">La chiamata di un metodo `async` non assegna thread aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="01cd7-124">Calling an `async` method does not allocate any additional threads.</span></span> <span data-ttu-id="01cd7-125">È possibile usare brevemente il thread di completamento di I/O esistente alla fine.</span><span class="sxs-lookup"><span data-stu-id="01cd7-125">It may use the existing I/O completion thread briefly at the end.</span></span>

<span data-ttu-id="01cd7-126">In .NET Framework 4,5 sono stati aggiunti i metodi seguenti per supportare la programmazione asincrona:</span><span class="sxs-lookup"><span data-stu-id="01cd7-126">The following methods were added in .NET Framework 4.5 to support asynchronous programming:</span></span>

- <xref:System.Data.Common.DbConnection.OpenAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteDbDataReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteNonQueryAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbCommand.ExecuteScalarAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbDataReader.GetFieldValueAsync%2A>

- <xref:System.Data.Common.DbDataReader.IsDBNullAsync%2A>

- <xref:System.Data.Common.DbDataReader.NextResultAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.Common.DbDataReader.ReadAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlConnection.OpenAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQueryAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteScalarAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlCommand.ExecuteXmlReaderAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlDataReader.NextResultAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlDataReader.ReadAsync%2A?displayProperty=nameWithType>

- <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>

 <span data-ttu-id="01cd7-127">Sono stati aggiunti altri membri asincroni per supportare il [supporto del flusso SqlClient](sqlclient-streaming-support.md).</span><span class="sxs-lookup"><span data-stu-id="01cd7-127">Other asynchronous members were added to support [SqlClient Streaming Support](sqlclient-streaming-support.md).</span></span>

> [!TIP]
> <span data-ttu-id="01cd7-128">I nuovi metodi asincroni non richiedono `Asynchronous Processing=true` nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="01cd7-128">The new asynchronous methods don't require `Asynchronous Processing=true` in the connection string.</span></span>

### <a name="synchronous-to-asynchronous-connection-open"></a><span data-ttu-id="01cd7-129">Apertura della connessione da sincrona ad asincrona</span><span class="sxs-lookup"><span data-stu-id="01cd7-129">Synchronous to Asynchronous Connection Open</span></span>

<span data-ttu-id="01cd7-130">È possibile aggiornare un'applicazione esistente in modo da usare la nuova funzionalità asincrona.</span><span class="sxs-lookup"><span data-stu-id="01cd7-130">You can upgrade an existing application to use the new asynchronous feature.</span></span> <span data-ttu-id="01cd7-131">Ad esempio, si presupponga che un'applicazione disponga di un algoritmo di connessione sincrono e che blocchi il thread UI ogni volta che si connette al database e che, una volta che connessa, l'applicazione chiami una stored procedure che segnala agli altri utenti l'utente che ha appena effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="01cd7-131">For example, assume an application has a synchronous connection algorithm and blocks the UI thread every time it connects to the database and, once connected, the application calls a stored procedure that signals other users of the one who just signed in.</span></span>

```csharp
using SqlConnection conn = new SqlConnection("…");
{
   conn.Open();
   using (SqlCommand cmd = new SqlCommand("StoredProcedure_Logon", conn))
   {
      cmd.ExecuteNonQuery();
   }
}
```

<span data-ttu-id="01cd7-132">Una volta convertito per l'uso della nuova funzionalità asincrona, il programma sarà simile a quanto seguente:</span><span class="sxs-lookup"><span data-stu-id="01cd7-132">When converted to use the new asynchronous functionality, the program would look like:</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;

class A {

   static async Task<int> Method(SqlConnection conn, SqlCommand cmd) {
      await conn.OpenAsync();
      await cmd.ExecuteNonQueryAsync();
      return 1;
   }

   public static void Main() {
      using (SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI")) {
         SqlCommand command = new SqlCommand("select top 2 * from orders", conn);

         int result = A.Method(conn, command).Result;

         SqlDataReader reader = command.ExecuteReader();
         while (reader.Read())
            Console.WriteLine(reader[0]);
      }
   }
}
```

### <a name="adding-the-new-asynchronous-feature-in-an-existing-application-mixing-old-and-new-patterns"></a><span data-ttu-id="01cd7-133">Aggiunta della nuova funzionalità asincrona in un'applicazione esistente (combinazione di modelli vecchi e i nuovi)</span><span class="sxs-lookup"><span data-stu-id="01cd7-133">Adding the New Asynchronous Feature in an Existing Application (Mixing Old and New Patterns)</span></span>

<span data-ttu-id="01cd7-134">È anche possibile aggiungere la nuova funzionalità asincrona (SqlConnection::OpenAsync) senza modificare la logica asincrona esistente.</span><span class="sxs-lookup"><span data-stu-id="01cd7-134">It is also possible to add new asynchronous capability (SqlConnection::OpenAsync) without changing the existing asynchronous logic.</span></span> <span data-ttu-id="01cd7-135">Ad esempio, se un'applicazione attualmente usa:</span><span class="sxs-lookup"><span data-stu-id="01cd7-135">For example, if an application currently uses:</span></span>

```csharp
AsyncCallback productList = new AsyncCallback(ProductList);
SqlConnection conn = new SqlConnection("…");
conn.Open();
SqlCommand cmd = new SqlCommand("SELECT * FROM [Current Product List]", conn);
IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);
```

<span data-ttu-id="01cd7-136">È possibile iniziare a usare il nuovo modello asincrono senza modificare sostanzialmente l'algoritmo esistente.</span><span class="sxs-lookup"><span data-stu-id="01cd7-136">You can begin to use the new asynchronous pattern without substantially changing the existing algorithm.</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;

class A {
   static void ProductList(IAsyncResult result) { }

   public static void Main() {
      // AsyncCallback productList = new AsyncCallback(ProductList);
      // SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI");
      // conn.Open();
      // SqlCommand cmd = new SqlCommand("select top 2 * from orders", conn);
      // IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);

      AsyncCallback productList = new AsyncCallback(ProductList);
      SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI");
      conn.OpenAsync().ContinueWith((task) => {
         SqlCommand cmd = new SqlCommand("select top 2 * from orders", conn);
         IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);
      }, TaskContinuationOptions.OnlyOnRanToCompletion);
   }
}
```

### <a name="using-the-base-provider-model-and-the-new-asynchronous-feature"></a><span data-ttu-id="01cd7-137">Utilizzo del modello di provider di base e la nuova funzionalità asincrona</span><span class="sxs-lookup"><span data-stu-id="01cd7-137">Using the Base Provider Model and the New Asynchronous Feature</span></span>

<span data-ttu-id="01cd7-138">Potrebbe essere necessario creare uno strumento in grado di connettersi al database e di eseguire query.</span><span class="sxs-lookup"><span data-stu-id="01cd7-138">You may need to create a tool that is able to connect to different databases and execute queries.</span></span> <span data-ttu-id="01cd7-139">È possibile usare il modello di provider di base e la nuova funzionalità asincrona</span><span class="sxs-lookup"><span data-stu-id="01cd7-139">You can use the base provider model and the new asynchronous feature.</span></span>

<span data-ttu-id="01cd7-140">È necessario abilitare il servizio Microsoft Distributed Transaction Controller (MSDTC) sul server per usare transazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="01cd7-140">The Microsoft Distributed Transaction Controller (MSDTC) must be enabled on the server to use distributed transactions.</span></span> <span data-ttu-id="01cd7-141">Per informazioni su come abilitare MSDTC, vedere [How to Enable MSDTC on a Web Server](https://docs.microsoft.com/previous-versions/commerce-server/dd327979(v=cs.90)).</span><span class="sxs-lookup"><span data-stu-id="01cd7-141">For information on how to enable MSDTC, see [How to Enable MSDTC on a Web Server](https://docs.microsoft.com/previous-versions/commerce-server/dd327979(v=cs.90)).</span></span>

```csharp
using System;
using System.Data.Common;
using System.Data.SqlClient;
using System.Threading.Tasks;

class A {
   static async Task PerformDBOperationsUsingProviderModel(string connectionString, string providerName) {
      DbProviderFactory factory = DbProviderFactories.GetFactory(providerName);
      using (DbConnection connection = factory.CreateConnection()) {
         connection.ConnectionString = connectionString;
         await connection.OpenAsync();

         DbCommand command = connection.CreateCommand();
         command.CommandText = "SELECT * FROM AUTHORS";

         using (DbDataReader reader = await command.ExecuteReaderAsync()) {
            while (await reader.ReadAsync()) {
               for (int i = 0; i < reader.FieldCount; i++) {
                  // Process each column as appropriate
                  object obj = await reader.GetFieldValueAsync<object>(i);
                  Console.WriteLine(obj);
               }
            }
         }
      }
   }

   public static void Main()
   {
       SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder();
       // replace these with your own values
       builder.DataSource = "your_server";
       builder.InitialCatalog = "pubs";
       builder.IntegratedSecurity = true;
       string provider = "System.Data.SqlClient";

       Task task = PerformDBOperationsUsingProviderModel(builder.ConnectionString, provider);
       task.Wait();
   }
}
```

### <a name="using-sql-transactions-and-the-new-asynchronous-feature"></a><span data-ttu-id="01cd7-142">Uso di transazioni di SQL e della nuova funzionalità asincrona</span><span class="sxs-lookup"><span data-stu-id="01cd7-142">Using SQL Transactions and the New Asynchronous Feature</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;

class Program {
   static void Main() {
      string connectionString =
          "Persist Security Info=False;Integrated Security=SSPI;database=Northwind;server=(local)";
      Task task = ExecuteSqlTransaction(connectionString);
      task.Wait();
   }

   static async Task ExecuteSqlTransaction(string connectionString) {
      using (SqlConnection connection = new SqlConnection(connectionString)) {
         await connection.OpenAsync();

         SqlCommand command = connection.CreateCommand();
         SqlTransaction transaction = null;

         // Start a local transaction.
         transaction = await Task.Run<SqlTransaction>(
             () => connection.BeginTransaction("SampleTransaction")
             );

         // Must assign both transaction object and connection
         // to Command object for a pending local transaction
         command.Connection = connection;
         command.Transaction = transaction;

         try {
            command.CommandText =
                "Insert into Region (RegionID, RegionDescription) VALUES (555, 'Description')";
            await command.ExecuteNonQueryAsync();

            command.CommandText =
                "Insert into Region (RegionID, RegionDescription) VALUES (556, 'Description')";
            await command.ExecuteNonQueryAsync();

            // Attempt to commit the transaction.
            await Task.Run(() => transaction.Commit());
            Console.WriteLine("Both records are written to database.");
         }
         catch (Exception ex) {
            Console.WriteLine("Commit Exception Type: {0}", ex.GetType());
            Console.WriteLine("  Message: {0}", ex.Message);

            // Attempt to roll back the transaction.
            try {
               transaction.Rollback();
            }
            catch (Exception ex2) {
               // This catch block will handle any errors that may have occurred
               // on the server that would cause the rollback to fail, such as
               // a closed connection.
               Console.WriteLine("Rollback Exception Type: {0}", ex2.GetType());
               Console.WriteLine("  Message: {0}", ex2.Message);
            }
         }
      }
   }
}
```

### <a name="using-sql-transactions-and-the-new-asynchronous-feature"></a><span data-ttu-id="01cd7-143">Uso di transazioni di SQL e della nuova funzionalità asincrona</span><span class="sxs-lookup"><span data-stu-id="01cd7-143">Using SQL Transactions and the New Asynchronous Feature</span></span>

<span data-ttu-id="01cd7-144">In un'applicazione aziendale potrebbe essere necessario aggiungere transazioni distribuite in alcuni scenari, per abilitare le transazioni tra più server di database.</span><span class="sxs-lookup"><span data-stu-id="01cd7-144">In an enterprise application, you may need to add distributed transactions in some scenarios, to enable transactions between multiple database servers.</span></span> <span data-ttu-id="01cd7-145">È possibile usare lo spazio dei nomi System.Transactions e inserire una transazione distribuita, come segue:</span><span class="sxs-lookup"><span data-stu-id="01cd7-145">You can use the System.Transactions namespace and enlist a distributed transaction, as follows:</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading.Tasks;
using System.Transactions;

class Program {
   public static void Main()
   {
       SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder();
       // replace these with your own values
       builder.DataSource = "your_server";
       builder.InitialCatalog = "your_data_source";
       builder.IntegratedSecurity = true;

       Task task = ExecuteDistributedTransaction(builder.ConnectionString, builder.ConnectionString);
       task.Wait();
   }

   static async Task ExecuteDistributedTransaction(string connectionString1, string connectionString2) {
      using (SqlConnection connection1 = new SqlConnection(connectionString1))
      using (SqlConnection connection2 = new SqlConnection(connectionString2)) {
         using (CommittableTransaction transaction = new CommittableTransaction()) {
            await connection1.OpenAsync();
            connection1.EnlistTransaction(transaction);

            await connection2.OpenAsync();
            connection2.EnlistTransaction(transaction);

            try {
               SqlCommand command1 = connection1.CreateCommand();
               command1.CommandText = "Insert into RegionTable1 (RegionID, RegionDescription) VALUES (100, 'Description')";
               await command1.ExecuteNonQueryAsync();

               SqlCommand command2 = connection2.CreateCommand();
               command2.CommandText = "Insert into RegionTable2 (RegionID, RegionDescription) VALUES (100, 'Description')";
               await command2.ExecuteNonQueryAsync();

               transaction.Commit();
            }
            catch (Exception ex) {
               Console.WriteLine("Exception Type: {0}", ex.GetType());
               Console.WriteLine("  Message: {0}", ex.Message);

               try {
                  transaction.Rollback();
               }
               catch (Exception ex2) {
                  Console.WriteLine("Rollback Exception Type: {0}", ex2.GetType());
                  Console.WriteLine("  Message: {0}", ex2.Message);
               }
            }
         }
      }
   }
}
```

### <a name="cancelling-an-asynchronous-operation"></a><span data-ttu-id="01cd7-146">Annullamento di un'operazione asincrona</span><span class="sxs-lookup"><span data-stu-id="01cd7-146">Cancelling an Asynchronous Operation</span></span>

<span data-ttu-id="01cd7-147">È possibile annullare una richiesta asincrona tramite <xref:System.Threading.CancellationToken>.</span><span class="sxs-lookup"><span data-stu-id="01cd7-147">You can cancel an asynchronous request by using the <xref:System.Threading.CancellationToken>.</span></span>

```csharp
using System;
using System.Data.SqlClient;
using System.Threading;
using System.Threading.Tasks;

namespace Samples {
   class CancellationSample {
      public static void Main(string[] args) {
         CancellationTokenSource source = new CancellationTokenSource();
         source.CancelAfter(2000); // give up after 2 seconds
         try {
            Task result = CancellingAsynchronousOperations(source.Token);
            result.Wait();
         }
         catch (AggregateException exception) {
            if (exception.InnerException is SqlException) {
               Console.WriteLine("Operation canceled");
            }
            else {
               throw;
            }
         }
      }

      static async Task CancellingAsynchronousOperations(CancellationToken cancellationToken) {
         using (SqlConnection connection = new SqlConnection("Server=(local);Integrated Security=true")) {
            await connection.OpenAsync(cancellationToken);

            SqlCommand command = new SqlCommand("WAITFOR DELAY '00:10:00'", connection);
            await command.ExecuteNonQueryAsync(cancellationToken);
         }
      }
   }
}
```

### <a name="asynchronous-operations-with-sqlbulkcopy"></a><span data-ttu-id="01cd7-148">Operazioni asincrone con SqlBulkCopy</span><span class="sxs-lookup"><span data-stu-id="01cd7-148">Asynchronous Operations with SqlBulkCopy</span></span>

<span data-ttu-id="01cd7-149">Le funzionalità asincrone inoltre sono state aggiunte a <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType> con <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="01cd7-149">Asynchronous capabilities were also added to <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType> with <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Data;
using System.Data.Odbc;
using System.Data.SqlClient;
using System.Linq;
using System.Text;
using System.Threading;
using System.Threading.Tasks;

namespace SqlBulkCopyAsyncCodeSample {
   class Program {
      static string selectStatement = "SELECT * FROM [pubs].[dbo].[titles]";
      static string createDestTableStatement =
          @"CREATE TABLE {0} (
            [title_id] [varchar](6) NOT NULL,
            [title] [varchar](80) NOT NULL,
            [type] [char](12) NOT NULL,
            [pub_id] [char](4) NULL,
            [price] [money] NULL,
            [advance] [money] NULL,
            [royalty] [int] NULL,
            [ytd_sales] [int] NULL,
            [notes] [varchar](200) NULL,
            [pubdate] [datetime] NOT NULL)";

      // Replace the connection string if needed, for instance to connect to SQL Express: @"Server=(local)\SQLEXPRESS;Database=Demo;Integrated Security=true"
      // static string connectionString = @"Server=(localdb)\V11.0;Database=Demo";
      static string connectionString = @"Server=(local);Database=Demo;Integrated Security=true";

      // static string odbcConnectionString = @"Driver={SQL Server};Server=(localdb)\V11.0;UID=oledb;Pwd=1Password!;Database=Demo";
      static string odbcConnectionString = @"Driver={SQL Server};Server=(local);Database=Demo;Integrated Security=true";

      // static string marsConnectionString = @"Server=(localdb)\V11.0;Database=Demo;MultipleActiveResultSets=true;";
      static string marsConnectionString = @"Server=(local);Database=Demo;MultipleActiveResultSets=true;Integrated Security=true";

      // Replace the Server name with your actual sql azure server name and User ID/Password
      static string azureConnectionString = @"Server=SqlAzure;User ID=myUserID;Password=myPassword;Database=Demo";

      static void Main(string[] args) {
         SynchronousSqlBulkCopy();
         AsyncSqlBulkCopy().Wait();
         MixSyncAsyncSqlBulkCopy().Wait();
         AsyncSqlBulkCopyNotifyAfter().Wait();
         AsyncSqlBulkCopyDataRows().Wait();
         // AsyncSqlBulkCopySqlServerToSqlAzure().Wait();
         // AsyncSqlBulkCopyCancel().Wait();
         AsyncSqlBulkCopyMARS().Wait();
      }

      // 3.1.1 Synchronous bulk copy in .NET 4.5
      private static void SynchronousSqlBulkCopy() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            conn.Open();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               cmd.ExecuteNonQuery();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  bcp.WriteToServer(dt);
               }
            }
         }

      }

      // 3.1.2 Asynchronous bulk copy in .NET 4.5
      private static async Task AsyncSqlBulkCopy() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            await conn.OpenAsync();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               await cmd.ExecuteNonQueryAsync();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  await bcp.WriteToServerAsync(dt);
               }
            }
         }
      }

      // 3.2 Add new Async.NET capabilities in an existing application (Mixing synchronous and asynchronous calls)
      private static async Task MixSyncAsyncSqlBulkCopy() {
         using (OdbcConnection odbcconn = new OdbcConnection(odbcConnectionString)) {
            odbcconn.Open();
            using (OdbcCommand odbccmd = new OdbcCommand(selectStatement, odbcconn)) {
               using (OdbcDataReader odbcreader = odbccmd.ExecuteReader()) {
                  using (SqlConnection conn = new SqlConnection(connectionString)) {
                     await conn.OpenAsync();
                     string temptable = "temptable";//"[#" + Guid.NewGuid().ToString("N") + "]";
                     SqlCommand createCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), conn);
                     await createCmd.ExecuteNonQueryAsync();
                     using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                        bcp.DestinationTableName = temptable;
                        await bcp.WriteToServerAsync(odbcreader);
                     }
                  }
               }
            }
         }
      }

      // 3.3 Using the NotifyAfter property
      private static async Task AsyncSqlBulkCopyNotifyAfter() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            await conn.OpenAsync();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               await cmd.ExecuteNonQueryAsync();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  bcp.NotifyAfter = 5;
                  bcp.SqlRowsCopied += new SqlRowsCopiedEventHandler(OnSqlRowsCopied);
                  await bcp.WriteToServerAsync(dt);
               }
            }
         }
      }

      private static void OnSqlRowsCopied(object sender, SqlRowsCopiedEventArgs e) {
         Console.WriteLine("Copied {0} so far...", e.RowsCopied);
      }

      // 3.4 Using the new SqlBulkCopy Async.NET capabilities with DataRow[]
      private static async Task AsyncSqlBulkCopyDataRows() {
         using (SqlConnection conn = new SqlConnection(connectionString)) {
            await conn.OpenAsync();
            DataTable dt = new DataTable();
            using (SqlCommand cmd = new SqlCommand(selectStatement, conn)) {
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);
               adapter.Fill(dt);
               DataRow[] rows = dt.Select();

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               cmd.CommandText = string.Format(createDestTableStatement, temptable);
               await cmd.ExecuteNonQueryAsync();

               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {
                  bcp.DestinationTableName = temptable;
                  await bcp.WriteToServerAsync(rows);
               }
            }
         }
      }

      // 3.5 Copying data from SQL Server to SQL Azure in .NET 4.5
      //private static async Task AsyncSqlBulkCopySqlServerToSqlAzure() {
      //   using (SqlConnection srcConn = new SqlConnection(connectionString))
      //   using (SqlConnection destConn = new SqlConnection(azureConnectionString)) {
      //      await srcConn.OpenAsync();
      //      await destConn.OpenAsync();
      //      using (SqlCommand srcCmd = new SqlCommand(selectStatement, srcConn)) {
      //         using (SqlDataReader reader = await srcCmd.ExecuteReaderAsync()) {
      //            string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
      //            using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {
      //               await destCmd.ExecuteNonQueryAsync();
      //               using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {
      //                  bcp.DestinationTableName = temptable;
      //                  await bcp.WriteToServerAsync(reader);
      //               }
      //            }
      //         }
      //      }
      //   }
      //}

      // 3.6 Cancelling an Asynchronous Operation to SQL Azure
      //private static async Task AsyncSqlBulkCopyCancel() {
      //   CancellationTokenSource cts = new CancellationTokenSource();
      //   using (SqlConnection srcConn = new SqlConnection(connectionString))
      //   using (SqlConnection destConn = new SqlConnection(azureConnectionString)) {
      //      await srcConn.OpenAsync(cts.Token);
      //      await destConn.OpenAsync(cts.Token);
      //      using (SqlCommand srcCmd = new SqlCommand(selectStatement, srcConn)) {
      //         using (SqlDataReader reader = await srcCmd.ExecuteReaderAsync(cts.Token)) {
      //            string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
      //            using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {
      //               await destCmd.ExecuteNonQueryAsync(cts.Token);
      //               using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {
      //                  bcp.DestinationTableName = temptable;
      //                  await bcp.WriteToServerAsync(reader, cts.Token);
      //                  //Cancel Async SqlBulCopy Operation after 200 ms
      //                  cts.CancelAfter(200);
      //               }
      //            }
      //         }
      //      }
      //   }
      //}

      // 3.7 Using Async.Net and MARS
      private static async Task AsyncSqlBulkCopyMARS() {
         using (SqlConnection marsConn = new SqlConnection(marsConnectionString)) {
            await marsConn.OpenAsync();

            SqlCommand titlesCmd = new SqlCommand("SELECT * FROM [pubs].[dbo].[titles]", marsConn);
            SqlCommand authorsCmd = new SqlCommand("SELECT * FROM [pubs].[dbo].[authors]", marsConn);
            //With MARS we can have multiple active results sets on the same connection
            using (SqlDataReader titlesReader = await titlesCmd.ExecuteReaderAsync())
            using (SqlDataReader authorsReader = await authorsCmd.ExecuteReaderAsync()) {
               await authorsReader.ReadAsync();

               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";
               using (SqlConnection destConn = new SqlConnection(connectionString)) {
                  await destConn.OpenAsync();
                  using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {
                     await destCmd.ExecuteNonQueryAsync();
                     using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {
                        bcp.DestinationTableName = temptable;
                        await bcp.WriteToServerAsync(titlesReader);
                     }
                  }
               }
            }
         }
      }
   }
}
```

## <a name="asynchronously-using-multiple-commands-with-mars"></a><span data-ttu-id="01cd7-150">Utilizzo in modo asincrono di più comandi con MARS</span><span class="sxs-lookup"><span data-stu-id="01cd7-150">Asynchronously Using Multiple Commands with MARS</span></span>

<span data-ttu-id="01cd7-151">Nell'esempio viene aperta una singola connessione al database **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="01cd7-151">The example opens a single connection to the **AdventureWorks** database.</span></span> <span data-ttu-id="01cd7-152">Usando un oggetto <xref:System.Data.SqlClient.SqlCommand> viene creato un tipo <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="01cd7-152">Using a <xref:System.Data.SqlClient.SqlCommand> object, a <xref:System.Data.SqlClient.SqlDataReader> is created.</span></span> <span data-ttu-id="01cd7-153">Poiché viene usato il lettore, viene aperto un secondo <xref:System.Data.SqlClient.SqlDataReader>, usando i dati del primo <xref:System.Data.SqlClient.SqlDataReader> come input per la clausola WHERE per il secondo lettore.</span><span class="sxs-lookup"><span data-stu-id="01cd7-153">As the reader is used, a second <xref:System.Data.SqlClient.SqlDataReader> is opened, using data from the first <xref:System.Data.SqlClient.SqlDataReader> as input to the WHERE clause for the second reader.</span></span>

> [!NOTE]
> <span data-ttu-id="01cd7-154">Nell'esempio seguente viene usato il database di esempio **AdventureWorks** incluso in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01cd7-154">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="01cd7-155">Per la stringa di connessione fornita nel codice di esempio si presuppone che il database sia installato e disponibile nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="01cd7-155">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="01cd7-156">Modificare la stringa di connessione per adattarla all'ambiente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="01cd7-156">Modify the connection string as necessary for your environment.</span></span>

```csharp
using System;
using System.Data;
using System.Data.SqlClient;
using System.Threading.Tasks;

class Class1 {
   static void Main() {
      Task task = MultipleCommands();
      task.Wait();
   }

   static async Task MultipleCommands() {
      // By default, MARS is disabled when connecting to a MARS-enabled.
      // It must be enabled in the connection string.
      string connectionString = GetConnectionString();

      int vendorID;
      SqlDataReader productReader = null;
      string vendorSQL =
        "SELECT VendorId, Name FROM Purchasing.Vendor";
      string productSQL =
        "SELECT Production.Product.Name FROM Production.Product " +
        "INNER JOIN Purchasing.ProductVendor " +
        "ON Production.Product.ProductID = " +
        "Purchasing.ProductVendor.ProductID " +
        "WHERE Purchasing.ProductVendor.VendorID = @VendorId";

      using (SqlConnection awConnection =
        new SqlConnection(connectionString)) {
         SqlCommand vendorCmd = new SqlCommand(vendorSQL, awConnection);
         SqlCommand productCmd =
           new SqlCommand(productSQL, awConnection);

         productCmd.Parameters.Add("@VendorId", SqlDbType.Int);

         await awConnection.OpenAsync();
         using (SqlDataReader vendorReader = await vendorCmd.ExecuteReaderAsync()) {
            while (await vendorReader.ReadAsync()) {
               Console.WriteLine(vendorReader["Name"]);

               vendorID = (int)vendorReader["VendorId"];

               productCmd.Parameters["@VendorId"].Value = vendorID;
               // The following line of code requires a MARS-enabled connection.
               productReader = await productCmd.ExecuteReaderAsync();
               using (productReader) {
                  while (await productReader.ReadAsync()) {
                     Console.WriteLine("  " +
                       productReader["Name"].ToString());
                  }
               }
            }
         }
      }
   }

   private static string GetConnectionString() {
      // To avoid storing the connection string in your code, you can retrieve it from a configuration file.
      return "Data Source=(local);Integrated Security=SSPI;Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";
   }
}
```

## <a name="asynchronously-reading-and-updating-data-with-mars"></a><span data-ttu-id="01cd7-157">Lettura e aggiornamento asincroni dei dati con MARS</span><span class="sxs-lookup"><span data-stu-id="01cd7-157">Asynchronously Reading and Updating Data with MARS</span></span>

<span data-ttu-id="01cd7-158">MARS consente di usare una connessione per operazioni di lettura e operazioni DML (Data Manipulation Language) con più di un'operazione in sospeso.</span><span class="sxs-lookup"><span data-stu-id="01cd7-158">MARS allows a connection to be used for both read operations and data manipulation language (DML) operations with more than one pending operation.</span></span> <span data-ttu-id="01cd7-159">Questa funzionalità elimina la necessità, da parte di un'applicazione, di dover gestire errori dovuti a una connessione non disponibile.</span><span class="sxs-lookup"><span data-stu-id="01cd7-159">This feature eliminates the need for an application to deal with connection-busy errors.</span></span> <span data-ttu-id="01cd7-160">Inoltre, MARS è in grado di sostituire l'uso di cursori sul lato server, che di norma usano più risorse.</span><span class="sxs-lookup"><span data-stu-id="01cd7-160">In addition, MARS can replace the user of server-side cursors, which generally consume more resources.</span></span> <span data-ttu-id="01cd7-161">Infine, poiché su una singola connessione possono essere eseguite più operazioni, queste possono condividere lo stesso contesto di transazione, eliminando la necessità di usare le stored procedure di sistema **sp_getbindtoken** e **sp_bindsession**.</span><span class="sxs-lookup"><span data-stu-id="01cd7-161">Finally, because multiple operations can operate on a single connection, they can share the same transaction context, eliminating the need to use **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span>

<span data-ttu-id="01cd7-162">Nella seguente applicazione console viene mostrato come usare due oggetti <xref:System.Data.SqlClient.SqlDataReader> con tre oggetti <xref:System.Data.SqlClient.SqlCommand> e un singolo oggetto <xref:System.Data.SqlClient.SqlConnection> con MARS abilitato.</span><span class="sxs-lookup"><span data-stu-id="01cd7-162">The following Console application demonstrates how to use two <xref:System.Data.SqlClient.SqlDataReader> objects with three <xref:System.Data.SqlClient.SqlCommand> objects and a single <xref:System.Data.SqlClient.SqlConnection> object with MARS enabled.</span></span> <span data-ttu-id="01cd7-163">Il primo oggetto comando recupera un elenco di fornitori la cui posizione creditizia corrisponde a 5.</span><span class="sxs-lookup"><span data-stu-id="01cd7-163">The first command object retrieves a list of vendors whose credit rating is 5.</span></span> <span data-ttu-id="01cd7-164">Il secondo oggetto comando usa l'identificatore fornitore fornito da un oggetto <xref:System.Data.SqlClient.SqlDataReader> per caricare il secondo oggetto <xref:System.Data.SqlClient.SqlDataReader> con tutti i prodotti per il fornitore specifico.</span><span class="sxs-lookup"><span data-stu-id="01cd7-164">The second command object uses the vendor ID provided from a <xref:System.Data.SqlClient.SqlDataReader> to load the second <xref:System.Data.SqlClient.SqlDataReader> with all of the products for the particular vendor.</span></span> <span data-ttu-id="01cd7-165">Il record di ciascun prodotto viene visitato dal secondo <xref:System.Data.SqlClient.SqlDataReader>.</span><span class="sxs-lookup"><span data-stu-id="01cd7-165">Each product record is visited by the second <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="01cd7-166">Viene calcolato il nuovo valore di **OnOrderQty**.</span><span class="sxs-lookup"><span data-stu-id="01cd7-166">A calculation is performed to determine what the new **OnOrderQty** should be.</span></span> <span data-ttu-id="01cd7-167">Il terzo oggetto comando viene usato per aggiornare la tabella **ProductVendor** con il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="01cd7-167">The third command object is then used to update the **ProductVendor** table with the new value.</span></span> <span data-ttu-id="01cd7-168">L'intero processo viene eseguito all'interno di una singola transazione, che viene quindi sottoposta a rollback.</span><span class="sxs-lookup"><span data-stu-id="01cd7-168">This entire process takes place within a single transaction, which is rolled back at the end.</span></span>

> [!NOTE]
> <span data-ttu-id="01cd7-169">Nell'esempio seguente viene usato il database di esempio **AdventureWorks** incluso in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="01cd7-169">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="01cd7-170">Per la stringa di connessione fornita nel codice di esempio si presuppone che il database sia installato e disponibile nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="01cd7-170">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="01cd7-171">Modificare la stringa di connessione per adattarla all'ambiente, se necessario.</span><span class="sxs-lookup"><span data-stu-id="01cd7-171">Modify the connection string as necessary for your environment.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.Data;
using System.Data.SqlClient;
using System.Threading.Tasks;

class Program {
   static void Main() {
      Task task = ReadingAndUpdatingData();
      task.Wait();
   }

   static async Task ReadingAndUpdatingData() {
      // By default, MARS is disabled when connecting to a MARS-enabled host.
      // It must be enabled in the connection string.
      string connectionString = GetConnectionString();

      SqlTransaction updateTx = null;
      SqlCommand vendorCmd = null;
      SqlCommand prodVendCmd = null;
      SqlCommand updateCmd = null;

      SqlDataReader prodVendReader = null;

      int vendorID = 0;
      int productID = 0;
      int minOrderQty = 0;
      int maxOrderQty = 0;
      int onOrderQty = 0;
      int recordsUpdated = 0;
      int totalRecordsUpdated = 0;

      string vendorSQL =
          "SELECT VendorID, Name FROM Purchasing.Vendor " +
          "WHERE CreditRating = 5";
      string prodVendSQL =
          "SELECT ProductID, MaxOrderQty, MinOrderQty, OnOrderQty " +
          "FROM Purchasing.ProductVendor " +
          "WHERE VendorID = @VendorID";
      string updateSQL =
          "UPDATE Purchasing.ProductVendor " +
          "SET OnOrderQty = @OrderQty " +
          "WHERE ProductID = @ProductID AND VendorID = @VendorID";

      using (SqlConnection awConnection =
        new SqlConnection(connectionString)) {
         await awConnection.OpenAsync();
         updateTx = await Task.Run(() => awConnection.BeginTransaction());

         vendorCmd = new SqlCommand(vendorSQL, awConnection);
         vendorCmd.Transaction = updateTx;

         prodVendCmd = new SqlCommand(prodVendSQL, awConnection);
         prodVendCmd.Transaction = updateTx;
         prodVendCmd.Parameters.Add("@VendorId", SqlDbType.Int);

         updateCmd = new SqlCommand(updateSQL, awConnection);
         updateCmd.Transaction = updateTx;
         updateCmd.Parameters.Add("@OrderQty", SqlDbType.Int);
         updateCmd.Parameters.Add("@ProductID", SqlDbType.Int);
         updateCmd.Parameters.Add("@VendorID", SqlDbType.Int);

         using (SqlDataReader vendorReader = await vendorCmd.ExecuteReaderAsync()) {
            while (await vendorReader.ReadAsync()) {
               Console.WriteLine(vendorReader["Name"]);

               vendorID = (int)vendorReader["VendorID"];
               prodVendCmd.Parameters["@VendorID"].Value = vendorID;
               prodVendReader = await prodVendCmd.ExecuteReaderAsync();

               using (prodVendReader) {
                  while (await prodVendReader.ReadAsync()) {
                     productID = (int)prodVendReader["ProductID"];

                     if (prodVendReader["OnOrderQty"] == DBNull.Value) {
                        minOrderQty = (int)prodVendReader["MinOrderQty"];
                        onOrderQty = minOrderQty;
                     }
                     else {
                        maxOrderQty = (int)prodVendReader["MaxOrderQty"];
                        onOrderQty = (int)(maxOrderQty / 2);
                     }

                     updateCmd.Parameters["@OrderQty"].Value = onOrderQty;
                     updateCmd.Parameters["@ProductID"].Value = productID;
                     updateCmd.Parameters["@VendorID"].Value = vendorID;

                     recordsUpdated = await updateCmd.ExecuteNonQueryAsync();
                     totalRecordsUpdated += recordsUpdated;
                  }
               }
            }
         }
         Console.WriteLine("Total Records Updated: ", totalRecordsUpdated.ToString());
         await Task.Run(() => updateTx.Rollback());
         Console.WriteLine("Transaction Rolled Back");
      }
   }

   private static string GetConnectionString() {
      // To avoid storing the connection string in your code, you can retrieve it from a configuration file.
      return "Data Source=(local);Integrated Security=SSPI;Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";
   }
}
```

## <a name="see-also"></a><span data-ttu-id="01cd7-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01cd7-172">See also</span></span>

- [<span data-ttu-id="01cd7-173">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="01cd7-173">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)

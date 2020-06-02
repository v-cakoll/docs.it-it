---
title: Esempi di codice
description: Questi esempi illustrano .NET Framework programmatori come recuperare dati da un database usando i provider di dati ADO.NET e ADO.NET Entity Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 54df0e253716c970cf23446434d96b104b8e9b03
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287168"
---
# <a name="adonet-code-examples"></a><span data-ttu-id="9221a-103">Esempi di codice ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9221a-103">ADO.NET code examples</span></span>

<span data-ttu-id="9221a-104">Gli elenchi di codice in questa pagina illustrano come recuperare dati da un database usando le tecnologie ADO.NET seguenti:</span><span class="sxs-lookup"><span data-stu-id="9221a-104">The code listings on this page demonstrate how to retrieve data from a database by using the following ADO.NET technologies:</span></span>

- <span data-ttu-id="9221a-105">Provider di dati ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="9221a-105">ADO.NET data providers:</span></span>

  - <span data-ttu-id="9221a-106">[SqlClient](#sqlclient) ( `System.Data.SqlClient` )</span><span class="sxs-lookup"><span data-stu-id="9221a-106">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span></span>

  - <span data-ttu-id="9221a-107">[OleDb](#oledb) ( `System.Data.OleDb` )</span><span class="sxs-lookup"><span data-stu-id="9221a-107">[OleDb](#oledb) (`System.Data.OleDb`)</span></span>

  - <span data-ttu-id="9221a-108">[ODBC](#odbc) ( `System.Data.Odbc` )</span><span class="sxs-lookup"><span data-stu-id="9221a-108">[Odbc](#odbc) (`System.Data.Odbc`)</span></span>

  - <span data-ttu-id="9221a-109">[OracleClient](#oracleclient) ( `System.Data.OracleClient` )</span><span class="sxs-lookup"><span data-stu-id="9221a-109">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span></span>

- <span data-ttu-id="9221a-110">ADO.NET Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="9221a-110">ADO.NET Entity Framework:</span></span>

  - [<span data-ttu-id="9221a-111">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="9221a-111">LINQ to Entities</span></span>](#linq-to-entities)

  - [<span data-ttu-id="9221a-112">Oggetto ObjectQuery tipizzato</span><span class="sxs-lookup"><span data-stu-id="9221a-112">Typed ObjectQuery</span></span>](#typed-objectquery)

  - <span data-ttu-id="9221a-113">[EntityClient](#entityclient) ( `System.Data.EntityClient` )</span><span class="sxs-lookup"><span data-stu-id="9221a-113">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span></span>

- [<span data-ttu-id="9221a-114">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9221a-114">LINQ to SQL</span></span>](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a><span data-ttu-id="9221a-115">Esempi di provider di dati ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9221a-115">ADO.NET data provider examples</span></span>
<span data-ttu-id="9221a-116">Gli elenchi di codice seguenti illustrano come recuperare i dati da un database usando i provider di dati ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="9221a-116">The following code listings demonstrate how to retrieve data from a database using ADO.NET data providers.</span></span> <span data-ttu-id="9221a-117">I dati vengono restituiti in un `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="9221a-117">The data is returned in a `DataReader`.</span></span> <span data-ttu-id="9221a-118">Per altre informazioni, vedere [recupero di dati tramite DataReader](retrieving-data-using-a-datareader.md).</span><span class="sxs-lookup"><span data-stu-id="9221a-118">For more information, see [Retrieving Data Using a DataReader](retrieving-data-using-a-datareader.md).</span></span>

### <a name="sqlclient"></a><span data-ttu-id="9221a-119">SqlClient</span><span class="sxs-lookup"><span data-stu-id="9221a-119">SqlClient</span></span>
<span data-ttu-id="9221a-120">Nel codice di questo esempio si presuppone che sia possibile connettersi al `Northwind` database di esempio in Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9221a-120">The code in this example assumes that you can connect to the `Northwind` sample database on Microsoft SQL Server.</span></span> <span data-ttu-id="9221a-121">Tramite il codice viene creato un oggetto <xref:System.Data.SqlClient.SqlCommand> per selezionare le righe dalla tabella Products e viene aggiunto un oggetto <xref:System.Data.SqlClient.SqlParameter> per limitare i risultati alle righe in cui UnitPrice è maggiore del valore del parametro specificato, in questo caso 5.</span><span class="sxs-lookup"><span data-stu-id="9221a-121">The code creates a <xref:System.Data.SqlClient.SqlCommand> to select rows from the Products table, adding a <xref:System.Data.SqlClient.SqlParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="9221a-122"><xref:System.Data.SqlClient.SqlConnection>Viene aperto all'interno di un `using` blocco, che assicura che le risorse vengano chiuse ed eliminate al termine dell'uscita del codice.</span><span class="sxs-lookup"><span data-stu-id="9221a-122">The <xref:System.Data.SqlClient.SqlConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="9221a-123">Il comando viene eseguito dal codice tramite un oggetto <xref:System.Data.SqlClient.SqlDataReader> e i risultati vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="9221a-123">The code executes the command by using a <xref:System.Data.SqlClient.SqlDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a><span data-ttu-id="9221a-124">OleDb</span><span class="sxs-lookup"><span data-stu-id="9221a-124">OleDb</span></span>
<span data-ttu-id="9221a-125">Nel codice di questo esempio si presuppone che sia possibile effettuare la connessione al database di esempio Northwind di Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="9221a-125">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="9221a-126">Tramite il codice viene creato un oggetto <xref:System.Data.OleDb.OleDbCommand> per selezionare le righe dalla tabella Products e viene aggiunto un oggetto <xref:System.Data.OleDb.OleDbParameter> per limitare i risultati alle righe in cui UnitPrice è maggiore del valore del parametro specificato, in questo caso 5.</span><span class="sxs-lookup"><span data-stu-id="9221a-126">The code creates a <xref:System.Data.OleDb.OleDbCommand> to select rows from the Products table, adding a <xref:System.Data.OleDb.OleDbParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="9221a-127">L'oggetto <xref:System.Data.OleDb.OleDbConnection> viene aperto in un blocco `using`, garantendo che le risorse vengano chiuse ed eliminate al termine dell'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="9221a-127">The <xref:System.Data.OleDb.OleDbConnection> is opened inside of a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="9221a-128">Il comando viene eseguito dal codice tramite un oggetto <xref:System.Data.OleDb.OleDbDataReader> e i risultati vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="9221a-128">The code executes the command by using a <xref:System.Data.OleDb.OleDbDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a><span data-ttu-id="9221a-129">Odbc</span><span class="sxs-lookup"><span data-stu-id="9221a-129">Odbc</span></span>
<span data-ttu-id="9221a-130">Nel codice di questo esempio si presuppone che sia possibile effettuare la connessione al database di esempio Northwind di Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="9221a-130">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="9221a-131">Tramite il codice viene creato un oggetto <xref:System.Data.Odbc.OdbcCommand> per selezionare le righe dalla tabella Products e viene aggiunto un oggetto <xref:System.Data.Odbc.OdbcParameter> per limitare i risultati alle righe in cui UnitPrice è maggiore del valore del parametro specificato, in questo caso 5.</span><span class="sxs-lookup"><span data-stu-id="9221a-131">The code creates a <xref:System.Data.Odbc.OdbcCommand> to select rows from the Products table, adding a <xref:System.Data.Odbc.OdbcParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="9221a-132"><xref:System.Data.Odbc.OdbcConnection>Viene aperto all'interno di un `using` blocco, che assicura che le risorse vengano chiuse ed eliminate al termine dell'uscita del codice.</span><span class="sxs-lookup"><span data-stu-id="9221a-132">The <xref:System.Data.Odbc.OdbcConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="9221a-133">Il comando viene eseguito dal codice tramite un oggetto <xref:System.Data.Odbc.OdbcDataReader> e i risultati vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="9221a-133">The code executes the command by using a <xref:System.Data.Odbc.OdbcDataReader>, and displays the results in the console window.</span></span>

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)]
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)]

### <a name="oracleclient"></a><span data-ttu-id="9221a-134">OracleClient</span><span class="sxs-lookup"><span data-stu-id="9221a-134">OracleClient</span></span>
<span data-ttu-id="9221a-135">Nel codice di questo esempio si presuppone che sia stata effettuata una connessione a DEMO.CUSTOMER in un server Oracle.</span><span class="sxs-lookup"><span data-stu-id="9221a-135">The code in this example assumes a connection to DEMO.CUSTOMER on an Oracle server.</span></span> <span data-ttu-id="9221a-136">È inoltre necessario aggiungere un riferimento a System.Data.OracleClient.dll.</span><span class="sxs-lookup"><span data-stu-id="9221a-136">You must also add a reference to the System.Data.OracleClient.dll.</span></span> <span data-ttu-id="9221a-137">Il codice restituisce i dati in un oggetto <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="9221a-137">The code returns the data in an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a><span data-ttu-id="9221a-138">Esempi di Entity Framework</span><span class="sxs-lookup"><span data-stu-id="9221a-138">Entity Framework examples</span></span>
<span data-ttu-id="9221a-139">I listati di codice seguenti illustrano come recuperare i dati da un'origine dati eseguendo una query sulle entità in Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="9221a-139">The following code listings demonstrate how to retrieve data from a data source by querying entities in an Entity Data Model (EDM).</span></span> <span data-ttu-id="9221a-140">In questi esempi viene utilizzato un modello basato sul database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="9221a-140">These examples use a model based on the Northwind sample database.</span></span> <span data-ttu-id="9221a-141">Per ulteriori informazioni su Entity Framework, vedere [Panoramica di Entity Framework](./ef/overview.md).</span><span class="sxs-lookup"><span data-stu-id="9221a-141">For more information about Entity Framework, see [Entity Framework Overview](./ef/overview.md).</span></span>

### <a name="linq-to-entities"></a><span data-ttu-id="9221a-142">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="9221a-142">LINQ to Entities</span></span>
<span data-ttu-id="9221a-143">Nel codice di questo esempio viene usata una query LINQ per restituire i dati come oggetti Categories, proiettati come tipo anonimo che contiene solo le proprietà CategoryID e CategoryName.</span><span class="sxs-lookup"><span data-stu-id="9221a-143">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="9221a-144">Per ulteriori informazioni, vedere [LINQ to Entities Overview](./ef/language-reference/linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="9221a-144">For more information, see [LINQ to Entities Overview](./ef/language-reference/linq-to-entities.md).</span></span>

```csharp
using System;
using System.Linq;
using System.Data.Objects;
using NorthwindModel;

class LinqSample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            try
            {
                var query = from category in context.Categories
                            select new
                            {
                                categoryID = category.CategoryID,
                                categoryName = category.CategoryName
                            };

                foreach (var categoryInfo in query)
                {
                    Console.WriteLine("\t{0}\t{1}",
                        categoryInfo.categoryID, categoryInfo.categoryName);
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Linq
Imports System.Data.Objects
Imports NorthwindModel

Class LinqSample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Try
                Dim query = From category In context.Categories _
                            Select New With _
                            { _
                                .categoryID = category.CategoryID, _
                                .categoryName = category.CategoryName _
                            }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                        categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

### <a name="typed-objectquery"></a><span data-ttu-id="9221a-145">Oggetto ObjectQuery tipizzato</span><span class="sxs-lookup"><span data-stu-id="9221a-145">Typed ObjectQuery</span></span>
<span data-ttu-id="9221a-146">Nel codice di questo esempio viene usato un oggetto <xref:System.Data.Objects.ObjectQuery%601> per restituire i dati come oggetti Categories.</span><span class="sxs-lookup"><span data-stu-id="9221a-146">The code in this example uses an <xref:System.Data.Objects.ObjectQuery%601> to return data as Categories objects.</span></span> <span data-ttu-id="9221a-147">Per altre informazioni, vedere [query di oggetti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9221a-147">For more information, see [Object Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span></span>

```csharp
using System;
using System.Data.Objects;
using NorthwindModel;

class ObjectQuerySample
{
    public static void ExecuteQuery()
    {
        using (NorthwindEntities context = new NorthwindEntities())
        {
            ObjectQuery<Categories> categoryQuery = context.Categories;

            foreach (Categories category in
                categoryQuery.Execute(MergeOption.AppendOnly))
            {
                Console.WriteLine("\t{0}\t{1}",
                    category.CategoryID, category.CategoryName);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Data.Objects
Imports NorthwindModel

Class ObjectQuerySample
    Public Shared Sub ExecuteQuery()
        Using context As NorthwindEntities = New NorthwindEntities()
            Dim categoryQuery As ObjectQuery(Of Categories) = context.Categories

            For Each category As Categories In _
                categoryQuery.Execute(MergeOption.AppendOnly)
                Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                    category.CategoryID, category.CategoryName)
            Next
        End Using
    End Sub
End Class
```

### <a name="entityclient"></a><span data-ttu-id="9221a-148">EntityClient</span><span class="sxs-lookup"><span data-stu-id="9221a-148">EntityClient</span></span>
<span data-ttu-id="9221a-149">Nel codice di questo esempio viene usato un oggetto <xref:System.Data.EntityClient.EntityCommand> per eseguire una query Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="9221a-149">The code in this example uses an <xref:System.Data.EntityClient.EntityCommand> to execute an Entity SQL query.</span></span> <span data-ttu-id="9221a-150">Questa query restituisce un elenco di record che rappresentano istanze del tipo di entità Categories.</span><span class="sxs-lookup"><span data-stu-id="9221a-150">This query returns a list of records that represent instances of the Categories entity type.</span></span> <span data-ttu-id="9221a-151">Per accedere ai record di dati nel set di risultati viene usato un oggetto <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="9221a-151">An <xref:System.Data.EntityClient.EntityDataReader> is used to access data records in the result set.</span></span> <span data-ttu-id="9221a-152">Per ulteriori informazioni, vedere [Provider EntityClient per Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="9221a-152">For more information, see [EntityClient Provider for the Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).</span></span>

```csharp
using System;
using System.Data;
using System.Data.Common;
using System.Data.EntityClient;
using NorthwindModel;

class EntityClientSample
{
    public static void ExecuteQuery()
    {
        string queryString =
            @"SELECT c.CategoryID, c.CategoryName
                FROM NorthwindEntities.Categories AS c";

        using (EntityConnection conn =
            new EntityConnection("name=NorthwindEntities"))
        {
            try
            {
                conn.Open();
                using (EntityCommand query = new EntityCommand(queryString, conn))
                {
                    using (DbDataReader rdr =
                        query.ExecuteReader(CommandBehavior.SequentialAccess))
                    {
                        while (rdr.Read())
                        {
                            Console.WriteLine("\t{0}\t{1}", rdr[0], rdr[1]);
                        }
                    }
                }
            }
            catch (Exception ex)
            {
                Console.WriteLine(ex.Message);
            }
        }
    }
}
```

```vb
Option Explicit On
Option Strict On

Imports System.Data
Imports System.Data.Common
Imports System.Data.EntityClient
Imports NorthwindModel

Class EntityClientSample
    Public Shared Sub ExecuteQuery()
        Dim queryString As String = _
            "SELECT c.CategoryID, c.CategoryName " & _
                "FROM NorthwindEntities.Categories AS c"

        Using conn As EntityConnection = _
            New EntityConnection("name=NorthwindEntities")

            Try
                conn.Open()
                Using query As EntityCommand = _
                New EntityCommand(queryString, conn)
                    Using rdr As DbDataReader = _
                        query.ExecuteReader(CommandBehavior.SequentialAccess)
                        While rdr.Read()
                            Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                                              rdr(0), rdr(1))
                        End While
                    End Using
                End Using
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
        End Using
    End Sub
End Class
```

## <a name="linq-to-sql"></a><span data-ttu-id="9221a-153">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9221a-153">LINQ to SQL</span></span>
<span data-ttu-id="9221a-154">Nel codice di questo esempio viene usata una query LINQ per restituire i dati come oggetti Categories, proiettati come tipo anonimo che contiene solo le proprietà CategoryID e CategoryName.</span><span class="sxs-lookup"><span data-stu-id="9221a-154">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="9221a-155">Questo esempio è basato sul contesto dati di Northwind.</span><span class="sxs-lookup"><span data-stu-id="9221a-155">This example is based on the Northwind data context.</span></span> <span data-ttu-id="9221a-156">Per ulteriori informazioni, vedere [Introduzione](./sql/linq/getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="9221a-156">For more information, see [Getting Started](./sql/linq/getting-started.md).</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using Northwind;

    class LinqSqlSample
    {
        public static void ExecuteQuery()
        {
            using (NorthwindDataContext db = new NorthwindDataContext())
            {
                try
                {
                    var query = from category in db.Categories
                                select new
                                {
                                    categoryID = category.CategoryID,
                                    categoryName = category.CategoryName
                                };

                    foreach (var categoryInfo in query)
                    {
                        Console.WriteLine("vbTab {0} vbTab {1}",
                            categoryInfo.categoryID, categoryInfo.categoryName);
                    }
                }
                catch (Exception ex)
                {
                    Console.WriteLine(ex.Message);
                }
            }
        }
    }
```

```vb
Option Explicit On
Option Strict On

Imports System.Collections.Generic
Imports System.Linq
Imports System.Text
Imports Northwind

Class LinqSqlSample
    Public Shared Sub ExecuteQuery()
        Using db As NorthwindDataContext = New NorthwindDataContext()
            Try
                Dim query = From category In db.Categories _
                                Select New With _
                                { _
                                    .categoryID = category.CategoryID, _
                                    .categoryName = category.CategoryName _
                                }

                For Each categoryInfo In query
                    Console.WriteLine(vbTab & "{0}" & vbTab & "{1}", _
                            categoryInfo.categoryID, categoryInfo.categoryName)
                Next
            Catch ex As Exception
                Console.WriteLine(ex.Message)
            End Try
            End Using
    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="9221a-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9221a-157">See also</span></span>

- [<span data-ttu-id="9221a-158">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9221a-158">ADO.NET Overview</span></span>](ado-net-overview.md)
- [<span data-ttu-id="9221a-159">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9221a-159">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- <span data-ttu-id="9221a-160">[Creazione di applicazioni dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="9221a-160">[Creating Data Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span></span>
- <span data-ttu-id="9221a-161">[Esecuzione di query su Entity Data Model (attività di Entity Framework)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9221a-161">[Querying an Entity Data Model (Entity Framework Tasks)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span></span>
- <span data-ttu-id="9221a-162">[Procedura: eseguire una query che restituisce oggetti di tipo anonimo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9221a-162">[How to: Execute a Query that Returns Anonymous Type Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>

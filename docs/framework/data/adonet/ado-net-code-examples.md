---
title: Esempi di codice
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c119657a-9ce6-4940-91e4-ac1d5f0d9584
ms.openlocfilehash: 4f0cbc06c03c0d122fc69b8a396570919ac14970
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980288"
---
# <a name="adonet-code-examples"></a><span data-ttu-id="97e0c-102">Esempi di codice ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97e0c-102">ADO.NET code examples</span></span>
<span data-ttu-id="97e0c-103">Gli elenchi di codice inclusi in questo argomento illustrano come recuperare dati da un database usando le tecnologie ADO.NET seguenti:</span><span class="sxs-lookup"><span data-stu-id="97e0c-103">The code listings in this topic demonstrate how to retrieve data from a database by using the following ADO.NET technologies:</span></span>

- <span data-ttu-id="97e0c-104">Provider di dati ADO.NET:</span><span class="sxs-lookup"><span data-stu-id="97e0c-104">ADO.NET data providers:</span></span>

  - <span data-ttu-id="97e0c-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span><span class="sxs-lookup"><span data-stu-id="97e0c-105">[SqlClient](#sqlclient) (`System.Data.SqlClient`)</span></span>

  - <span data-ttu-id="97e0c-106">[OleDb](#oledb) (`System.Data.OleDb`)</span><span class="sxs-lookup"><span data-stu-id="97e0c-106">[OleDb](#oledb) (`System.Data.OleDb`)</span></span>

  - <span data-ttu-id="97e0c-107">[Odbc](#odbc) (`System.Data.Odbc`)</span><span class="sxs-lookup"><span data-stu-id="97e0c-107">[Odbc](#odbc) (`System.Data.Odbc`)</span></span>

  - <span data-ttu-id="97e0c-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span><span class="sxs-lookup"><span data-stu-id="97e0c-108">[OracleClient](#oracleclient) (`System.Data.OracleClient`)</span></span>

- <span data-ttu-id="97e0c-109">ADO.NET Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="97e0c-109">ADO.NET Entity Framework:</span></span>

  - [<span data-ttu-id="97e0c-110">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="97e0c-110">LINQ to Entities</span></span>](#linq-to-entities)

  - [<span data-ttu-id="97e0c-111">ObjectQuery tipizzato</span><span class="sxs-lookup"><span data-stu-id="97e0c-111">Typed ObjectQuery</span></span>](#typed-objectquery)

  - <span data-ttu-id="97e0c-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span><span class="sxs-lookup"><span data-stu-id="97e0c-112">[EntityClient](#entityclient) (`System.Data.EntityClient`)</span></span>

- [<span data-ttu-id="97e0c-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="97e0c-113">LINQ to SQL</span></span>](#linq-to-sql)

## <a name="adonet-data-provider-examples"></a><span data-ttu-id="97e0c-114">Esempi di provider di dati ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97e0c-114">ADO.NET data provider examples</span></span>
<span data-ttu-id="97e0c-115">Gli elenchi di codice seguenti illustrano come recuperare i dati da un database usando i provider di dati ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="97e0c-115">The following code listings demonstrate how to retrieve data from a database using ADO.NET data providers.</span></span> <span data-ttu-id="97e0c-116">I dati vengono restituiti in un `DataReader`.</span><span class="sxs-lookup"><span data-stu-id="97e0c-116">The data is returned in a `DataReader`.</span></span> <span data-ttu-id="97e0c-117">Per altre informazioni, vedere [recupero di dati tramite DataReader](retrieving-data-using-a-datareader.md).</span><span class="sxs-lookup"><span data-stu-id="97e0c-117">For more information, see [Retrieving Data Using a DataReader](retrieving-data-using-a-datareader.md).</span></span>

### <a name="sqlclient"></a><span data-ttu-id="97e0c-118">SqlClient</span><span class="sxs-lookup"><span data-stu-id="97e0c-118">SqlClient</span></span>
<span data-ttu-id="97e0c-119">Nel codice di questo esempio si presuppone che sia possibile connettersi al database di esempio `Northwind` in Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97e0c-119">The code in this example assumes that you can connect to the `Northwind` sample database on Microsoft SQL Server.</span></span> <span data-ttu-id="97e0c-120">Tramite il codice viene creato un oggetto <xref:System.Data.SqlClient.SqlCommand> per selezionare le righe dalla tabella Products e viene aggiunto un oggetto <xref:System.Data.SqlClient.SqlParameter> per limitare i risultati alle righe in cui UnitPrice è maggiore del valore del parametro specificato, in questo caso 5.</span><span class="sxs-lookup"><span data-stu-id="97e0c-120">The code creates a <xref:System.Data.SqlClient.SqlCommand> to select rows from the Products table, adding a <xref:System.Data.SqlClient.SqlParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="97e0c-121">Il <xref:System.Data.SqlClient.SqlConnection> viene aperto all'interno di un blocco `using`, che assicura che le risorse vengano chiuse ed eliminate al termine del codice.</span><span class="sxs-lookup"><span data-stu-id="97e0c-121">The <xref:System.Data.SqlClient.SqlConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="97e0c-122">Il comando viene eseguito dal codice tramite un oggetto <xref:System.Data.SqlClient.SqlDataReader> e i risultati vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="97e0c-122">The code executes the command by using a <xref:System.Data.SqlClient.SqlDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.SqlClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.SqlClient/VB/source.vb#1)]

### <a name="oledb"></a><span data-ttu-id="97e0c-123">OleDb</span><span class="sxs-lookup"><span data-stu-id="97e0c-123">OleDb</span></span>
<span data-ttu-id="97e0c-124">Nel codice di questo esempio si presume che sia possibile effettuare la connessione al database di esempio Northwind di Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="97e0c-124">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="97e0c-125">Tramite il codice viene creato un oggetto <xref:System.Data.OleDb.OleDbCommand> per selezionare le righe dalla tabella Products e viene aggiunto un oggetto <xref:System.Data.OleDb.OleDbParameter> per limitare i risultati alle righe in cui UnitPrice è maggiore del valore del parametro specificato, in questo caso 5.</span><span class="sxs-lookup"><span data-stu-id="97e0c-125">The code creates a <xref:System.Data.OleDb.OleDbCommand> to select rows from the Products table, adding a <xref:System.Data.OleDb.OleDbParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="97e0c-126">L'oggetto <xref:System.Data.OleDb.OleDbConnection> viene aperto in un blocco `using`, garantendo che le risorse vengano chiuse ed eliminate al termine dell'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="97e0c-126">The <xref:System.Data.OleDb.OleDbConnection> is opened inside of a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="97e0c-127">Il comando viene eseguito dal codice tramite un oggetto <xref:System.Data.OleDb.OleDbDataReader> e i risultati vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="97e0c-127">The code executes the command by using a <xref:System.Data.OleDb.OleDbDataReader>, and displays the results in the console window.</span></span>

 [!code-csharp[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.OleDb#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.OleDb/VB/source.vb#1)]

### <a name="odbc"></a><span data-ttu-id="97e0c-128">Odbc</span><span class="sxs-lookup"><span data-stu-id="97e0c-128">Odbc</span></span>
<span data-ttu-id="97e0c-129">Nel codice di questo esempio si presume che sia possibile effettuare la connessione al database di esempio Northwind di Microsoft Access.</span><span class="sxs-lookup"><span data-stu-id="97e0c-129">The code in this example assumes that you can connect to the Microsoft Access Northwind sample database.</span></span> <span data-ttu-id="97e0c-130">Tramite il codice viene creato un oggetto <xref:System.Data.Odbc.OdbcCommand> per selezionare le righe dalla tabella Products e viene aggiunto un oggetto <xref:System.Data.Odbc.OdbcParameter> per limitare i risultati alle righe in cui UnitPrice è maggiore del valore del parametro specificato, in questo caso 5.</span><span class="sxs-lookup"><span data-stu-id="97e0c-130">The code creates a <xref:System.Data.Odbc.OdbcCommand> to select rows from the Products table, adding a <xref:System.Data.Odbc.OdbcParameter> to restrict the results to rows with a UnitPrice greater than the specified parameter value, in this case 5.</span></span> <span data-ttu-id="97e0c-131">Il <xref:System.Data.Odbc.OdbcConnection> viene aperto all'interno di un blocco `using`, che assicura che le risorse vengano chiuse ed eliminate al termine del codice.</span><span class="sxs-lookup"><span data-stu-id="97e0c-131">The <xref:System.Data.Odbc.OdbcConnection> is opened inside a `using` block, which ensures that resources are closed and disposed when the code exits.</span></span> <span data-ttu-id="97e0c-132">Il comando viene eseguito dal codice tramite un oggetto <xref:System.Data.Odbc.OdbcDataReader> e i risultati vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="97e0c-132">The code executes the command by using a <xref:System.Data.Odbc.OdbcDataReader>, and displays the results in the console window.</span></span>

[!code-csharp[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/CS/source.cs#1)] 
[!code-vb[DataWorks SampleApp.Odbc#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Odbc/VB/source.vb#1)] 

### <a name="oracleclient"></a><span data-ttu-id="97e0c-133">OracleClient</span><span class="sxs-lookup"><span data-stu-id="97e0c-133">OracleClient</span></span>
<span data-ttu-id="97e0c-134">Nel codice di questo esempio si presuppone che sia stata effettuata una connessione a DEMO.CUSTOMER in un server Oracle.</span><span class="sxs-lookup"><span data-stu-id="97e0c-134">The code in this example assumes a connection to DEMO.CUSTOMER on an Oracle server.</span></span> <span data-ttu-id="97e0c-135">È inoltre necessario aggiungere un riferimento a System.Data.OracleClient.dll.</span><span class="sxs-lookup"><span data-stu-id="97e0c-135">You must also add a reference to the System.Data.OracleClient.dll.</span></span> <span data-ttu-id="97e0c-136">Il codice restituisce i dati in un oggetto <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="97e0c-136">The code returns the data in an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>

 [!code-csharp[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/CS/source.cs#1)]
 [!code-vb[DataWorks SampleApp.Oracle#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SampleApp.Oracle/VB/source.vb#1)]

## <a name="entity-framework-examples"></a><span data-ttu-id="97e0c-137">Esempi di Entity Framework</span><span class="sxs-lookup"><span data-stu-id="97e0c-137">Entity Framework examples</span></span>
<span data-ttu-id="97e0c-138">I listati di codice seguenti illustrano come recuperare i dati da un'origine dati eseguendo una query sulle entità in Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="97e0c-138">The following code listings demonstrate how to retrieve data from a data source by querying entities in an Entity Data Model (EDM).</span></span> <span data-ttu-id="97e0c-139">In questi esempi viene utilizzato un modello basato sul database Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="97e0c-139">These examples use a model based on the Northwind sample database.</span></span> <span data-ttu-id="97e0c-140">Per ulteriori informazioni su Entity Framework, vedere [Panoramica di Entity Framework](./ef/overview.md).</span><span class="sxs-lookup"><span data-stu-id="97e0c-140">For more information about Entity Framework, see [Entity Framework Overview](./ef/overview.md).</span></span>

### <a name="linq-to-entities"></a><span data-ttu-id="97e0c-141">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="97e0c-141">LINQ to Entities</span></span>
<span data-ttu-id="97e0c-142">Nel codice di questo esempio viene usata una query LINQ per restituire i dati come oggetti Categories, proiettati come tipo anonimo che contiene solo le proprietà CategoryID e CategoryName.</span><span class="sxs-lookup"><span data-stu-id="97e0c-142">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="97e0c-143">Per ulteriori informazioni, vedere [LINQ to Entities Overview](./ef/language-reference/linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="97e0c-143">For more information, see [LINQ to Entities Overview](./ef/language-reference/linq-to-entities.md).</span></span>

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

### <a name="typed-objectquery"></a><span data-ttu-id="97e0c-144">Oggetto ObjectQuery tipizzato</span><span class="sxs-lookup"><span data-stu-id="97e0c-144">Typed ObjectQuery</span></span>
<span data-ttu-id="97e0c-145">Nel codice di questo esempio viene usato un oggetto <xref:System.Data.Objects.ObjectQuery%601> per restituire i dati come oggetti Categories.</span><span class="sxs-lookup"><span data-stu-id="97e0c-145">The code in this example uses an <xref:System.Data.Objects.ObjectQuery%601> to return data as Categories objects.</span></span> <span data-ttu-id="97e0c-146">Per altre informazioni, vedere [query di oggetti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="97e0c-146">For more information, see [Object Queries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896241(v=vs.100)).</span></span>

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

### <a name="entityclient"></a><span data-ttu-id="97e0c-147">EntityClient</span><span class="sxs-lookup"><span data-stu-id="97e0c-147">EntityClient</span></span>
<span data-ttu-id="97e0c-148">Nel codice di questo esempio viene usato un oggetto <xref:System.Data.EntityClient.EntityCommand> per eseguire una query Entity SQL.</span><span class="sxs-lookup"><span data-stu-id="97e0c-148">The code in this example uses an <xref:System.Data.EntityClient.EntityCommand> to execute an Entity SQL query.</span></span> <span data-ttu-id="97e0c-149">Questa query restituisce un elenco di record che rappresentano istanze del tipo di entità Categories.</span><span class="sxs-lookup"><span data-stu-id="97e0c-149">This query returns a list of records that represent instances of the Categories entity type.</span></span> <span data-ttu-id="97e0c-150">Per accedere ai record di dati nel set di risultati viene usato un oggetto <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="97e0c-150">An <xref:System.Data.EntityClient.EntityDataReader> is used to access data records in the result set.</span></span> <span data-ttu-id="97e0c-151">Per ulteriori informazioni, vedere [provider EntityClient per la Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).</span><span class="sxs-lookup"><span data-stu-id="97e0c-151">For more information, see [EntityClient Provider for the Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).</span></span>

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

## <a name="linq-to-sql"></a><span data-ttu-id="97e0c-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="97e0c-152">LINQ to SQL</span></span>
<span data-ttu-id="97e0c-153">Nel codice di questo esempio viene usata una query LINQ per restituire i dati come oggetti Categories, proiettati come tipo anonimo che contiene solo le proprietà CategoryID e CategoryName.</span><span class="sxs-lookup"><span data-stu-id="97e0c-153">The code in this example uses a LINQ query to return data as Categories objects, which are projected as an anonymous type that contains only the CategoryID and CategoryName properties.</span></span> <span data-ttu-id="97e0c-154">Questo esempio è basato sul contesto dati di Northwind.</span><span class="sxs-lookup"><span data-stu-id="97e0c-154">This example is based on the Northwind data context.</span></span> <span data-ttu-id="97e0c-155">Per altre informazioni, vedere [Introduzione a .NET Framework](./sql/linq/getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="97e0c-155">For more information, see [Getting Started](./sql/linq/getting-started.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="97e0c-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97e0c-156">See also</span></span>

- [<span data-ttu-id="97e0c-157">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97e0c-157">ADO.NET Overview</span></span>](ado-net-overview.md)
- [<span data-ttu-id="97e0c-158">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97e0c-158">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- <span data-ttu-id="97e0c-159">[Creazione di applicazioni dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="97e0c-159">[Creating Data Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/h0y4a0f6(v=vs.120))</span></span>
- <span data-ttu-id="97e0c-160">[Esecuzione di query su un Entity Data Model (Entity Framework attività)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="97e0c-160">[Querying an Entity Data Model (Entity Framework Tasks)](https://docs.microsoft.com/previous-versions/bb738455(v=vs.90))</span></span>
- <span data-ttu-id="97e0c-161">[Procedura: eseguire una query che restituisce oggetti di tipo anonimo](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="97e0c-161">[How to: Execute a Query that Returns Anonymous Type Objects](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))</span></span>

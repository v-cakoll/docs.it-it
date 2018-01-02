---
title: Stabilire una connessione
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
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
caps.latest.revision: "7"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 416d89aef35fef5dd0ac2bca92fb8a90d757a2d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="establishing-the-connection"></a><span data-ttu-id="8fde4-102">Stabilire una connessione</span><span class="sxs-lookup"><span data-stu-id="8fde4-102">Establishing the Connection</span></span>
<span data-ttu-id="8fde4-103">Per eseguire la connessione a Microsoft SQL Server, usare l'oggetto <xref:System.Data.SqlClient.SqlConnection> del provider di dati .NET Framework per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8fde4-103">To connect to Microsoft SQL Server, use the <xref:System.Data.SqlClient.SqlConnection> object of the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="8fde4-104">Per eseguire la connessione a un'origine dati OLE DB, usare l'oggetto <xref:System.Data.OleDb.OleDbConnection> del provider di dati .NET Framework per OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8fde4-104">To connect to an OLE DB data source, use the <xref:System.Data.OleDb.OleDbConnection> object of the .NET Framework Data Provider for OLE DB.</span></span> <span data-ttu-id="8fde4-105">Per eseguire la connessione a un'origine dati ODBC, usare l'oggetto <xref:System.Data.Odbc.OdbcConnection> del provider di dati .NET Framework per ODBC.</span><span class="sxs-lookup"><span data-stu-id="8fde4-105">To connect to an ODBC data source, use the <xref:System.Data.Odbc.OdbcConnection> object of the .NET Framework Data Provider for ODBC.</span></span> <span data-ttu-id="8fde4-106">Per eseguire la connessione a un'origine dati Oracle, usare l'oggetto <xref:System.Data.OracleClient.OracleConnection> del provider di dati .NET Framework per Oracle.</span><span class="sxs-lookup"><span data-stu-id="8fde4-106">To connect to an Oracle data source, use the <xref:System.Data.OracleClient.OracleConnection> object of the .NET Framework Data Provider for Oracle.</span></span> <span data-ttu-id="8fde4-107">Per archiviare in modo sicuro e recuperare le stringhe di connessione, vedere [la protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="8fde4-107">For securely storing and retrieving connection strings, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="closing-connections"></a><span data-ttu-id="8fde4-108">Disconnessione</span><span class="sxs-lookup"><span data-stu-id="8fde4-108">Closing Connections</span></span>  
 <span data-ttu-id="8fde4-109">Al termine dell'utilizzo, chiudere sempre la connessione in modo che possa essere restituita al pool.</span><span class="sxs-lookup"><span data-stu-id="8fde4-109">We recommend that you always close the connection when you are finished using it, so that the connection can be returned to the pool.</span></span> <span data-ttu-id="8fde4-110">Il blocco `Using` in Visual Basic o C# elimina automaticamente la connessione quando il codice esce dal blocco, anche in caso di eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="8fde4-110">The `Using` block in Visual Basic or C# automatically disposes of the connection when the code exits the block, even in the case of an unhandled exception.</span></span> <span data-ttu-id="8fde4-111">Vedere [utilizzando l'istruzione](~/docs/csharp/language-reference/keywords/using-statement.md) e [istruzione Using](~/docs/visual-basic/language-reference/statements/using-statement.md) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="8fde4-111">See [using Statement](~/docs/csharp/language-reference/keywords/using-statement.md) and [Using Statement](~/docs/visual-basic/language-reference/statements/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="8fde4-112">È anche possibile usare il metodo `Close` o `Dispose` dell'oggetto connessione del provider in uso.</span><span class="sxs-lookup"><span data-stu-id="8fde4-112">You can also use the `Close` or `Dispose` methods of the connection object for the provider that you are using.</span></span> <span data-ttu-id="8fde4-113">Le connessioni che non vengono chiuse in modo esplicito potrebbero non essere aggiunte o restituite al pool.</span><span class="sxs-lookup"><span data-stu-id="8fde4-113">Connections that are not explicitly closed might not be added or returned to the pool.</span></span> <span data-ttu-id="8fde4-114">Ad esempio, una connessione che esce dall'ambito ma non viene chiusa in modo esplicito verrà restituita al pool di connessioni solo se è stata raggiunta la dimensione massima del pool e la connessione è ancora valida.</span><span class="sxs-lookup"><span data-stu-id="8fde4-114">For example, a connection that has gone out of scope but that has not been explicitly closed will only be returned to the connection pool if the maximum pool size has been reached and the connection is still valid.</span></span> <span data-ttu-id="8fde4-115">Per ulteriori informazioni, vedere [OLE DB, ODBC e Oracle Connection Pooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="8fde4-115">For more information, see [OLE DB, ODBC, and Oracle Connection Pooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fde4-116">Non chiamare `Close` o `Dispose` su un **connessione**, **DataReader**, o qualsiasi altro oggetto gestito nel `Finalize` metodo della classe.</span><span class="sxs-lookup"><span data-stu-id="8fde4-116">Do not call `Close` or `Dispose` on a **Connection**, a **DataReader**, or any other managed object in the `Finalize` method of your class.</span></span> <span data-ttu-id="8fde4-117">Nei finalizzatori rilasciare solo le risorse non gestite che la classe controlla direttamente.</span><span class="sxs-lookup"><span data-stu-id="8fde4-117">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="8fde4-118">Se nella classe non sono presenti risorse non gestite, non includere un metodo `Finalize` nella relativa definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="8fde4-118">If your class does not own any unmanaged resources, do not include a `Finalize` method in your class definition.</span></span> <span data-ttu-id="8fde4-119">Per ulteriori informazioni, vedere [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="8fde4-119">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fde4-120">Nel server non vengono generati eventi di accesso e di disconnessione quando una connessione viene recuperata dal o restituita al pool di connessioni, in quanto la connessione non viene effettivamente chiusa quando viene restituita al pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="8fde4-120">Login and logout events will not be raised on the server when a connection is fetched from or returned to the connection pool, because the connection is not actually closed when it is returned to the connection pool.</span></span> <span data-ttu-id="8fde4-121">Per ulteriori informazioni, vedere [SQL Server Connection Pooling (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="8fde4-121">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
## <a name="connecting-to-sql-server"></a><span data-ttu-id="8fde4-122">Connessione a SQL Server</span><span class="sxs-lookup"><span data-stu-id="8fde4-122">Connecting to SQL Server</span></span>  
 <span data-ttu-id="8fde4-123">Il formato della stringa di connessione supportato dal provider di dati .NET Framework per SQL Server è simile al formato della stringa di connessione OLE DB (ADO).</span><span class="sxs-lookup"><span data-stu-id="8fde4-123">The .NET Framework Data Provider for SQL Server supports a connection string format that is similar to the OLE DB (ADO) connection string format.</span></span> <span data-ttu-id="8fde4-124">Per informazioni sui nomi e sui valori validi del formato della stringa, vedere la proprietà <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> dell'oggetto <xref:System.Data.SqlClient.SqlConnection>.</span><span class="sxs-lookup"><span data-stu-id="8fde4-124">For valid string format names and values, see the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="8fde4-125">È anche possibile usare la classe <xref:System.Data.SqlClient.SqlConnectionStringBuilder> per creare stringhe di connessione sintatticamente valide in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8fde4-125">You can also use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="8fde4-126">Per ulteriori informazioni, vedere [generatori di stringhe di connessione](../../../../docs/framework/data/adonet/connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="8fde4-126">For more information, see [Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md).</span></span>  
  
 <span data-ttu-id="8fde4-127">Nel codice di esempio seguente viene descritta la procedura di creazione e di apertura di una connessione a un database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8fde4-127">The following code example demonstrates how to create and open a connection to a SQL Server database.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New SqlConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (SqlConnection connection = new SqlConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
### <a name="integrated-security-and-aspnet"></a><span data-ttu-id="8fde4-128">Sicurezza integrata e ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8fde4-128">Integrated Security and ASP.NET</span></span>  
 <span data-ttu-id="8fde4-129">La sicurezza integrata di SQL Server (connessioni trusted) consente di proteggere la connessione a SQL Server, poiché non espone l'identificatore utente e la password nella stringa di connessione ed è il metodo consigliato per l'autenticazione di una connessione.</span><span class="sxs-lookup"><span data-stu-id="8fde4-129">SQL Server integrated security (also known as trusted connections) helps to provide protection when connecting to SQL Server as it does not expose a user ID and password in the connection string and is the recommended method for authenticating a connection.</span></span> <span data-ttu-id="8fde4-130">La sicurezza integrata usa l'identità di sicurezza corrente, o token, del processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8fde4-130">Integrated security uses the current security identity, or token, of the executing process.</span></span> <span data-ttu-id="8fde4-131">Per le applicazioni desktop, tale identità corrisponde solitamente all'identità dell'utente attualmente connesso.</span><span class="sxs-lookup"><span data-stu-id="8fde4-131">For desktop applications, this is typically the identity of the currently logged-on user.</span></span>  
  
 <span data-ttu-id="8fde4-132">L'identità di sicurezza delle applicazioni ASP.NET può essere impostata su diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="8fde4-132">The security identity for ASP.NET applications can be set to one of several different options.</span></span> <span data-ttu-id="8fde4-133">Per comprendere meglio l'identità di sicurezza che un'applicazione ASP.NET utilizza per la connessione a SQL Server, vedere [rappresentazione ASP.NET](http://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d), [autenticazione ASP.NET](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1), e [come: accesso SQL La sicurezza integrata di Windows tramite server](http://msdn.microsoft.com/library/683f9c9f-4375-4de6-8111-943c4423fde5).</span><span class="sxs-lookup"><span data-stu-id="8fde4-133">To better understand the security identity that an ASP.NET application uses when connecting to SQL Server, see [ASP.NET Impersonation](http://msdn.microsoft.com/library/a0cb3024-562f-4184-9d3c-095504787d3d), [ASP.NET Authentication](http://msdn.microsoft.com/library/fc10b0ef-4ce4-4a7f-9174-886325221ee1), and [How to: Access SQL Server Using Windows Integrated Security](http://msdn.microsoft.com/library/683f9c9f-4375-4de6-8111-943c4423fde5).</span></span>  
  
## <a name="connecting-to-an-ole-db-data-source"></a><span data-ttu-id="8fde4-134">Connessione a un'origine dati OLE DB</span><span class="sxs-lookup"><span data-stu-id="8fde4-134">Connecting to an OLE DB Data Source</span></span>  
 <span data-ttu-id="8fde4-135">Il Provider di dati .NET Framework per OLE DB fornisce la connettività a origini dati esposte tramite OLE DB (tramite SQLOLEDB, il Provider OLE DB per SQL Server), utilizzando il **OleDbConnection** oggetto.</span><span class="sxs-lookup"><span data-stu-id="8fde4-135">The .NET Framework Data Provider for OLE DB provides connectivity to data sources exposed using OLE DB (through SQLOLEDB, the OLE DB Provider for SQL Server), using the **OleDbConnection** object.</span></span>  
  
 <span data-ttu-id="8fde4-136">Per il provider di dati .NET Framework per OLE DB, il formato della stringa di connessione è identico a quello usato in ADO, con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fde4-136">For the .NET Framework Data Provider for OLE DB, the connection string format is identical to the connection string format used in ADO, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="8fde4-137">Il **Provider** parola chiave è obbligatoria.</span><span class="sxs-lookup"><span data-stu-id="8fde4-137">The **Provider** keyword is required.</span></span>  
  
-   <span data-ttu-id="8fde4-138">Il **URL**, **Provider remoto**, e **Server remoto** parole chiave non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="8fde4-138">The **URL**, **Remote Provider**, and **Remote Server** keywords are not supported.</span></span>  
  
 <span data-ttu-id="8fde4-139">Per altre informazioni sulle stringhe di connessione OLE DB, vedere l'argomento relativo a <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="8fde4-139">For more information about OLE DB connection strings, see the <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> topic.</span></span> <span data-ttu-id="8fde4-140">È anche possibile usare <xref:System.Data.OleDb.OleDbConnectionStringBuilder> per creare stringhe di connessione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8fde4-140">You can also use the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> to create connection strings at run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fde4-141">Il **OleDbConnection** l'oggetto non supporta l'impostazione o il recupero delle proprietà dinamiche specifiche di un provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8fde4-141">The **OleDbConnection** object does not support setting or retrieving dynamic properties specific to an OLE DB provider.</span></span> <span data-ttu-id="8fde4-142">Sono supportate esclusivamente le proprietà che possono essere passate nella stringa di connessione per il provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8fde4-142">Only properties that can be passed in the connection string for the OLE DB provider are supported.</span></span>  
  
 <span data-ttu-id="8fde4-143">Nell'esempio di codice seguente viene illustrato come creare e aprire una connessione a un'origine dati OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8fde4-143">The following code example demonstrates how to create and open a connection to an OLE DB data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OleDbConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OleDbConnection connection =   
  new OleDbConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="do-not-use-universal-data-link-files"></a><span data-ttu-id="8fde4-144">Non usare file collegamento dati universali (UDL, Universal Data Link)</span><span class="sxs-lookup"><span data-stu-id="8fde4-144">Do Not Use Universal Data Link Files</span></span>  
 <span data-ttu-id="8fde4-145">È possibile fornire informazioni di connessione per un **OleDbConnection** in un file Universal Data Link (UDL); tuttavia è consigliabile evitare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="8fde4-145">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="8fde4-146">I file UDL non sono crittografati, pertanto espongono le informazioni nella stringa di connessione come testo non crittografato.</span><span class="sxs-lookup"><span data-stu-id="8fde4-146">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="8fde4-147">Poiché per l'applicazione si tratta di una risorsa esterna basata su file, un file UDL non può essere protetto tramite .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8fde4-147">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span>  
  
## <a name="connecting-to-an-odbc-data-source"></a><span data-ttu-id="8fde4-148">Connessione a un'origine dati ODBC</span><span class="sxs-lookup"><span data-stu-id="8fde4-148">Connecting to an ODBC Data Source</span></span>  
 <span data-ttu-id="8fde4-149">Il Provider di dati .NET Framework per ODBC offre connettività a origini dati esposte tramite ODBC mediante il **OdbcConnection** oggetto.</span><span class="sxs-lookup"><span data-stu-id="8fde4-149">The .NET Framework Data Provider for ODBC provides connectivity to data sources exposed using ODBC using the **OdbcConnection** object.</span></span>  
  
 <span data-ttu-id="8fde4-150">Il formato della stringa di connessione da usare con il provider di dati .NET Framework per ODBC è molto simile a quello della stringa di connessione ODBC.</span><span class="sxs-lookup"><span data-stu-id="8fde4-150">For the .NET Framework Data Provider for ODBC, the connection string format is designed to match the ODBC connection string format as closely as possible.</span></span> <span data-ttu-id="8fde4-151">È anche possibile specificare il nome di un'origine dati (DSN, Data Source Name) ODBC.</span><span class="sxs-lookup"><span data-stu-id="8fde4-151">You may also supply an ODBC data source name (DSN).</span></span> <span data-ttu-id="8fde4-152">Per informazioni dettagliate sul **OdbcConnection** , vedere il <xref:System.Data.Odbc.OdbcConnection>.</span><span class="sxs-lookup"><span data-stu-id="8fde4-152">For more detail on the **OdbcConnection** , see the <xref:System.Data.Odbc.OdbcConnection>.</span></span>  
  
 <span data-ttu-id="8fde4-153">Nell'esempio di codice seguente viene illustrato come creare e aprire una connessione a un'origine dati ODBC.</span><span class="sxs-lookup"><span data-stu-id="8fde4-153">The following code example demonstrates how to create and open a connection to an ODBC data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OdbcConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OdbcConnection connection =   
  new OdbcConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="connecting-to-an-oracle-data-source"></a><span data-ttu-id="8fde4-154">Connessione a un'origine dati Oracle</span><span class="sxs-lookup"><span data-stu-id="8fde4-154">Connecting to an Oracle Data Source</span></span>  
 <span data-ttu-id="8fde4-155">Il Provider di dati .NET Framework per Oracle fornisce la connettività alle origini dati Oracle tramite il **OracleConnection** oggetto.</span><span class="sxs-lookup"><span data-stu-id="8fde4-155">The .NET Framework Data Provider for Oracle provides connectivity to Oracle data sources using the **OracleConnection** object.</span></span>  
  
 <span data-ttu-id="8fde4-156">Il formato della stringa di connessione da usare con il provider di dati .NET Framework per Oracle è molto simile a quello della stringa di connessione del provider OLE DB per Oracle (MSDAORA).</span><span class="sxs-lookup"><span data-stu-id="8fde4-156">For the .NET Framework Data Provider for Oracle, the connection string format is designed to match the OLE DB Provider for Oracle (MSDAORA) connection string format as closely as possible.</span></span> <span data-ttu-id="8fde4-157">Per informazioni dettagliate sul **OracleConnection**, vedere il <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="8fde4-157">For more detail on the **OracleConnection**, see the <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
 <span data-ttu-id="8fde4-158">Nell'esempio di codice seguente viene illustrato come creare e aprire una connessione a un'origine dati Oracle.</span><span class="sxs-lookup"><span data-stu-id="8fde4-158">The following code example demonstrates how to create and open a connection to an Oracle data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OracleConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OracleConnection connection =   
  new OracleConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
OracleConnection nwindConn = new OracleConnection("Data Source=MyOracleServer;Integrated Security=yes;");  
nwindConn.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="8fde4-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8fde4-159">See Also</span></span>  
 [<span data-ttu-id="8fde4-160">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="8fde4-160">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="8fde4-161">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="8fde4-161">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="8fde4-162">Pool di connessioni OLE DB, ODBC e Oracle</span><span class="sxs-lookup"><span data-stu-id="8fde4-162">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 [<span data-ttu-id="8fde4-163">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="8fde4-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

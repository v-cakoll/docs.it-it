---
title: Recupero di informazioni dello schema del database
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 00cf0e36dd7886897c26adf50102f32892ebb18e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43562704"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="c9d98-102">Recupero di informazioni dello schema del database</span><span class="sxs-lookup"><span data-stu-id="c9d98-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="c9d98-103">Il recupero di informazioni sullo schema da un database viene eseguito tramite il processo di individuazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="c9d98-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="c9d98-104">Individuazione dello schema consente alle applicazioni di richiedere che i provider gestiti trovano e restituiscono informazioni sullo schema di database, noto anche come *metadati*, di un determinato database.</span><span class="sxs-lookup"><span data-stu-id="c9d98-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="c9d98-105">Nella raccolta di schemi vengono esposti vari elementi dello schema del database, quali tabelle, colonne e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="c9d98-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="c9d98-106">Ogni raccolta di schemi contiene una varietà di informazioni sullo schema specifiche del provider usato.</span><span class="sxs-lookup"><span data-stu-id="c9d98-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="c9d98-107">Ognuno di implementare il provider gestito .NET Framework la **GetSchema** metodo nella **connessione** classe e le informazioni sullo schema restituito dal **GetSchema**metodo è disponibile in forma di un <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="c9d98-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="c9d98-108">Il **GetSchema** metodo è un metodo di overload che fornisce i parametri facoltativi per specificare la raccolta di schema da restituire e limitare la quantità di informazioni restituite.</span><span class="sxs-lookup"><span data-stu-id="c9d98-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="c9d98-109">I provider di dati .NET Framework per OLE DB, ODBC, Oracle e SqlClient forniscono un **GetSchemaTable** metodo che restituisce un oggetto DataTable descrivente i metadati della colonna la **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="c9d98-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="c9d98-110">Il provider di dati .NET Framework per OLE DB presenta le informazioni sullo schema usando anche il metodo <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> dell'oggetto <xref:System.Data.OleDb.OleDbConnection>.</span><span class="sxs-lookup"><span data-stu-id="c9d98-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="c9d98-111">Come argomenti **GetOleDbSchemaTable** accetta un <xref:System.Data.OleDb.OleDbSchemaGuid> che identifica le informazioni sullo schema da restituire e una matrice di restrizioni sulle colonne restituite.</span><span class="sxs-lookup"><span data-stu-id="c9d98-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="c9d98-112">**GetOleDbSchemaTable** restituisce un <xref:System.Data.DataTable> popolato con le informazioni richieste sullo schema.</span><span class="sxs-lookup"><span data-stu-id="c9d98-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9d98-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c9d98-113">In This Section</span></span>  
 [<span data-ttu-id="c9d98-114">Raccolte di schemi e GetSchema</span><span class="sxs-lookup"><span data-stu-id="c9d98-114">GetSchema and Schema Collections</span></span>](../../../../docs/framework/data/adonet/getschema-and-schema-collections.md)  
 <span data-ttu-id="c9d98-115">Descrive la **GetSchema** (metodo) e come può essere usato per recuperare e limitare le informazioni sullo schema da un database.</span><span class="sxs-lookup"><span data-stu-id="c9d98-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="c9d98-116">Restrizione dello schema</span><span class="sxs-lookup"><span data-stu-id="c9d98-116">Schema Restrictions</span></span>  
 <span data-ttu-id="c9d98-117">Descrive le restrizioni dello schema che possono essere usate con **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="c9d98-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="c9d98-118">Raccolte di schemi comuni</span><span class="sxs-lookup"><span data-stu-id="c9d98-118">Common Schema Collections</span></span>](../../../../docs/framework/data/adonet/common-schema-collections.md)  
 <span data-ttu-id="c9d98-119">Vengono descritte tutte le raccolte di schemi comuni supportate dai provider .NET Framework gestiti.</span><span class="sxs-lookup"><span data-stu-id="c9d98-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="c9d98-120">Raccolte di schemi SQL Server</span><span class="sxs-lookup"><span data-stu-id="c9d98-120">SQL Server Schema Collections</span></span>](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)  
 <span data-ttu-id="c9d98-121">Viene illustrata la raccolta di schemi supportata dal provider .NET Framework per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c9d98-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="c9d98-122">Raccolte di schemi Oracle</span><span class="sxs-lookup"><span data-stu-id="c9d98-122">Oracle Schema Collections</span></span>](../../../../docs/framework/data/adonet/oracle-schema-collections.md)  
 <span data-ttu-id="c9d98-123">Viene illustrata la raccolta di schemi supportata dal provider .NET Framework per Oracle.</span><span class="sxs-lookup"><span data-stu-id="c9d98-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="c9d98-124">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="c9d98-124">ODBC Schema Collections</span></span>](../../../../docs/framework/data/adonet/odbc-schema-collections.md)  
 <span data-ttu-id="c9d98-125">Vengono illustrate le raccolte di schemi per i driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="c9d98-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="c9d98-126">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="c9d98-126">OLE DB Schema Collections</span></span>](../../../../docs/framework/data/adonet/ole-db-schema-collections.md)  
 <span data-ttu-id="c9d98-127">Vengono illustrate le raccolte di schemi per i provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c9d98-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c9d98-128">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c9d98-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="c9d98-129">Descrive la **GetSchema** metodo il <xref:System.Data.Common.DbConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="c9d98-130">Descrive la **GetSchema** metodo il <xref:System.Data.Odbc.OdbcConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="c9d98-131">Descrive la **GetSchema** metodo il <xref:System.Data.OleDb.OleDbConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="c9d98-132">Descrive la **GetSchema** metodo il <xref:System.Data.OracleClient.OracleConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="c9d98-133">Descrive la **GetSchema** metodo il <xref:System.Data.SqlClient.SqlConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c9d98-134">Descrive la **GetSchemaTable** metodo il <xref:System.Data.Common.DbDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c9d98-135">Descrive la **GetSchemaTable** metodo il <xref:System.Data.Odbc.OdbcDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c9d98-136">Descrive la **GetSchemaTable** metodo il <xref:System.Data.OleDb.OleDbDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c9d98-137">Descrive la **GetSchemaTable** metodo il <xref:System.Data.OracleClient.OracleDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="c9d98-138">Descrive la **GetSchemaTable** metodo il <xref:System.Data.SqlClient.SqlDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="c9d98-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9d98-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9d98-139">See Also</span></span>  
 [<span data-ttu-id="c9d98-140">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c9d98-140">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="c9d98-141">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="c9d98-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

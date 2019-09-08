---
title: Recupero di informazioni dello schema del database
ms.date: 03/30/2017
ms.assetid: 79038d52-f122-4fd4-9bfb-aaa22d6a114b
ms.openlocfilehash: 26b234e35a0d0849914d87b61f4e8c8a87599448
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782733"
---
# <a name="retrieving-database-schema-information"></a><span data-ttu-id="bea8c-102">Recupero di informazioni dello schema del database</span><span class="sxs-lookup"><span data-stu-id="bea8c-102">Retrieving Database Schema Information</span></span>
<span data-ttu-id="bea8c-103">Il recupero di informazioni sullo schema da un database viene eseguito tramite il processo di individuazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="bea8c-103">Obtaining schema information from a database is accomplished with the process of schema discovery.</span></span> <span data-ttu-id="bea8c-104">L'individuazione dello schema consente alle applicazioni di richiedere che i provider gestiti trovino e restituiscano informazioni sullo schema del database, noto anche come *metadati*, di un determinato database.</span><span class="sxs-lookup"><span data-stu-id="bea8c-104">Schema discovery allows applications to request that managed providers find and return information about the database schema, also known as *metadata*, of a given database.</span></span> <span data-ttu-id="bea8c-105">Nella raccolta di schemi vengono esposti vari elementi dello schema del database, quali tabelle, colonne e stored procedure.</span><span class="sxs-lookup"><span data-stu-id="bea8c-105">Different database schema elements such as tables, columns, and stored-procedures are exposed through schema collections.</span></span> <span data-ttu-id="bea8c-106">Ogni raccolta di schemi contiene una varietà di informazioni sullo schema specifiche del provider usato.</span><span class="sxs-lookup"><span data-stu-id="bea8c-106">Each schema collection contains a variety of schema information specific to the provider being used.</span></span>  
  
 <span data-ttu-id="bea8c-107">Ognuno dei provider .NET Framework gestiti implementa il metodo **GetSchema** nella classe **Connection** e le informazioni sullo schema restituite dal metodo **GetSchema** sono nel formato di un oggetto <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="bea8c-107">Each of the .NET Framework managed providers implement the **GetSchema** method in the **Connection** class, and the schema information that is returned from the **GetSchema** method comes in the form of a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="bea8c-108">Il metodo **GetSchema** è un metodo di overload che fornisce parametri facoltativi per specificare la raccolta di schemi da restituire e per limitare la quantità di informazioni restituite.</span><span class="sxs-lookup"><span data-stu-id="bea8c-108">The **GetSchema** method is an overloaded method that provides optional parameters for specifying the schema collection to return, and restricting the amount of information returned.</span></span>  
  
 <span data-ttu-id="bea8c-109">I provider di dati .NET Framework per OLE DB, ODBC, Oracle e SqlClient forniscono un metodo **GetSchemaTable** che restituisce un oggetto DataTable che descrive i metadati della colonna del **DataReader**.</span><span class="sxs-lookup"><span data-stu-id="bea8c-109">The .NET Framework Data Providers for OLE DB, ODBC, Oracle, and SqlClient provide a **GetSchemaTable** method that returns a DataTable describing the column metadata of the **DataReader**.</span></span>  
  
 <span data-ttu-id="bea8c-110">Il provider di dati .NET Framework per OLE DB presenta le informazioni sullo schema usando anche il metodo <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> dell'oggetto <xref:System.Data.OleDb.OleDbConnection>.</span><span class="sxs-lookup"><span data-stu-id="bea8c-110">The .NET Framework Data Provider for OLE DB also exposes schema information by using the <xref:System.Data.OleDb.OleDbConnection.GetOleDbSchemaTable%2A> method of the <xref:System.Data.OleDb.OleDbConnection> object.</span></span> <span data-ttu-id="bea8c-111">Come argomenti, **il metodo GetOleDbSchemaTable** accetta un <xref:System.Data.OleDb.OleDbSchemaGuid> oggetto che identifica le informazioni sullo schema da restituire e una matrice di restrizioni sulle colonne restituite.</span><span class="sxs-lookup"><span data-stu-id="bea8c-111">As arguments, **GetOleDbSchemaTable** takes an <xref:System.Data.OleDb.OleDbSchemaGuid> that identifies the schema information to return, and an array of restrictions on those returned columns.</span></span> <span data-ttu-id="bea8c-112">**Il metodo GetOleDbSchemaTable** restituisce un <xref:System.Data.DataTable> oggetto popolato con le informazioni sullo schema richieste.</span><span class="sxs-lookup"><span data-stu-id="bea8c-112">**GetOleDbSchemaTable** returns a <xref:System.Data.DataTable> populated with the requested schema information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bea8c-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="bea8c-113">In This Section</span></span>  
 [<span data-ttu-id="bea8c-114">Raccolte di schemi e GetSchema</span><span class="sxs-lookup"><span data-stu-id="bea8c-114">GetSchema and Schema Collections</span></span>](getschema-and-schema-collections.md)  
 <span data-ttu-id="bea8c-115">Descrive il metodo **GetSchema** e il modo in cui può essere utilizzato per recuperare e limitare le informazioni dello schema da un database.</span><span class="sxs-lookup"><span data-stu-id="bea8c-115">Describes the **GetSchema** method and how it can be used to retrieve and restrict schema information from a database.</span></span>  
  
 <span data-ttu-id="bea8c-116">Restrizione dello schema</span><span class="sxs-lookup"><span data-stu-id="bea8c-116">Schema Restrictions</span></span>  
 <span data-ttu-id="bea8c-117">Descrive le restrizioni dello schema che possono essere usate con **GetSchema**.</span><span class="sxs-lookup"><span data-stu-id="bea8c-117">Describes schema restrictions that can be used with **GetSchema**.</span></span>  
  
 [<span data-ttu-id="bea8c-118">Raccolte di schemi comuni</span><span class="sxs-lookup"><span data-stu-id="bea8c-118">Common Schema Collections</span></span>](common-schema-collections.md)  
 <span data-ttu-id="bea8c-119">Vengono descritte tutte le raccolte di schemi comuni supportate dai provider .NET Framework gestiti.</span><span class="sxs-lookup"><span data-stu-id="bea8c-119">Describes all of the common schema collections supported by all of the .NET Framework managed providers.</span></span>  
  
 [<span data-ttu-id="bea8c-120">Raccolte di schemi SQL Server</span><span class="sxs-lookup"><span data-stu-id="bea8c-120">SQL Server Schema Collections</span></span>](sql-server-schema-collections.md)  
 <span data-ttu-id="bea8c-121">Viene illustrata la raccolta di schemi supportata dal provider .NET Framework per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bea8c-121">Describes the schema collection supported by the .NET Framework provider for SQL Server.</span></span>  
  
 [<span data-ttu-id="bea8c-122">Raccolte di schemi Oracle</span><span class="sxs-lookup"><span data-stu-id="bea8c-122">Oracle Schema Collections</span></span>](oracle-schema-collections.md)  
 <span data-ttu-id="bea8c-123">Viene illustrata la raccolta di schemi supportata dal provider .NET Framework per Oracle.</span><span class="sxs-lookup"><span data-stu-id="bea8c-123">Describes the schema collection supported by the .NET Framework provider for Oracle.</span></span>  
  
 [<span data-ttu-id="bea8c-124">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="bea8c-124">ODBC Schema Collections</span></span>](odbc-schema-collections.md)  
 <span data-ttu-id="bea8c-125">Vengono illustrate le raccolte di schemi per i driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="bea8c-125">Describes the schema collections for ODBC drivers.</span></span>  
  
 [<span data-ttu-id="bea8c-126">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="bea8c-126">OLE DB Schema Collections</span></span>](ole-db-schema-collections.md)  
 <span data-ttu-id="bea8c-127">Vengono illustrate le raccolte di schemi per i provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="bea8c-127">Describes the schema collections for OLE DB providers.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bea8c-128">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="bea8c-128">Reference</span></span>  
 <xref:System.Data.Common.DbConnection.GetSchema%2A>  
 <span data-ttu-id="bea8c-129">Viene descritto il metodo **GetSchema** della <xref:System.Data.Common.DbConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-129">Describes the **GetSchema** method of the <xref:System.Data.Common.DbConnection> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcConnection.GetSchema%2A>  
 <span data-ttu-id="bea8c-130">Viene descritto il metodo **GetSchema** della <xref:System.Data.Odbc.OdbcConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-130">Describes the **GetSchema** method of the <xref:System.Data.Odbc.OdbcConnection> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbConnection.GetSchema%2A>  
 <span data-ttu-id="bea8c-131">Viene descritto il metodo **GetSchema** della <xref:System.Data.OleDb.OleDbConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-131">Describes the **GetSchema** method of the <xref:System.Data.OleDb.OleDbConnection> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleConnection.GetSchema%2A>  
 <span data-ttu-id="bea8c-132">Viene descritto il metodo **GetSchema** della <xref:System.Data.OracleClient.OracleConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-132">Describes the **GetSchema** method of the <xref:System.Data.OracleClient.OracleConnection> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>  
 <span data-ttu-id="bea8c-133">Viene descritto il metodo **GetSchema** della <xref:System.Data.SqlClient.SqlConnection> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-133">Describes the **GetSchema** method of the <xref:System.Data.SqlClient.SqlConnection> class.</span></span>  
  
 <xref:System.Data.Common.DbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bea8c-134">Descrive il metodo **GetSchemaTable** della <xref:System.Data.Common.DbDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-134">Describes the **GetSchemaTable** method of the <xref:System.Data.Common.DbDataReader> class.</span></span>  
  
 <xref:System.Data.Odbc.OdbcDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bea8c-135">Descrive il metodo **GetSchemaTable** della <xref:System.Data.Odbc.OdbcDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-135">Describes the **GetSchemaTable** method of the <xref:System.Data.Odbc.OdbcDataReader> class.</span></span>  
  
 <xref:System.Data.OleDb.OleDbDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bea8c-136">Descrive il metodo **GetSchemaTable** della <xref:System.Data.OleDb.OleDbDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-136">Describes the **GetSchemaTable** method of the <xref:System.Data.OleDb.OleDbDataReader> class.</span></span>  
  
 <xref:System.Data.OracleClient.OracleDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bea8c-137">Descrive il metodo **GetSchemaTable** della <xref:System.Data.OracleClient.OracleDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-137">Describes the **GetSchemaTable** method of the <xref:System.Data.OracleClient.OracleDataReader> class.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>  
 <span data-ttu-id="bea8c-138">Descrive il metodo **GetSchemaTable** della <xref:System.Data.SqlClient.SqlDataReader> classe.</span><span class="sxs-lookup"><span data-stu-id="bea8c-138">Describes the **GetSchemaTable** method of the <xref:System.Data.SqlClient.SqlDataReader> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea8c-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bea8c-139">See also</span></span>

- [<span data-ttu-id="bea8c-140">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bea8c-140">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="bea8c-141">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bea8c-141">ADO.NET Overview</span></span>](ado-net-overview.md)

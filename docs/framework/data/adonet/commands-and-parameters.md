---
title: Comandi e parametri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b623f810-d871-49a5-b0f5-078cc3c34db6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e1bfd3e88df4bd90cbcebfa645c2a50159f836db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="commands-and-parameters"></a><span data-ttu-id="328e9-102">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="328e9-102">Commands and Parameters</span></span>
<span data-ttu-id="328e9-103">Una volta stabilita una connessione a un'origine dati, è possibile eseguire i comandi e restituire i risultati dell'origine dati usando un oggetto <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="328e9-103">After establishing a connection to a data source, you can execute commands and return results from the data source using a <xref:System.Data.Common.DbCommand> object.</span></span> <span data-ttu-id="328e9-104">È possibile creare un comando usando uno dei costruttori di comando del provider di dati .NET Framework usato.</span><span class="sxs-lookup"><span data-stu-id="328e9-104">You can create a command using one of the command constructors for the .NET Framework data provider you are working with.</span></span> <span data-ttu-id="328e9-105">I costruttori possono accettare argomenti facoltativi, ad esempio un'istruzione SQL da eseguire nell'origine dati, un oggetto <xref:System.Data.Common.DbConnection> o un oggetto <xref:System.Data.Common.DbTransaction>.</span><span class="sxs-lookup"><span data-stu-id="328e9-105">Constructors can take optional arguments, such as an SQL statement to execute at the data source, a <xref:System.Data.Common.DbConnection> object, or a <xref:System.Data.Common.DbTransaction> object.</span></span> <span data-ttu-id="328e9-106">È inoltre possibile configurare tali oggetti come proprietà del comando,</span><span class="sxs-lookup"><span data-stu-id="328e9-106">You can also configure those objects as properties of the command.</span></span> <span data-ttu-id="328e9-107">nonché creare un comando per una particolare connessione usando il metodo <xref:System.Data.Common.DbConnection.CreateCommand%2A> di un oggetto `DbConnection`.</span><span class="sxs-lookup"><span data-stu-id="328e9-107">You can also create a command for a particular connection using the <xref:System.Data.Common.DbConnection.CreateCommand%2A> method of a `DbConnection` object.</span></span> <span data-ttu-id="328e9-108">È possibile configurare l'istruzione SQL eseguita dal comando tramite la proprietà <xref:System.Data.Common.DbCommand.CommandText%2A>.</span><span class="sxs-lookup"><span data-stu-id="328e9-108">The SQL statement being executed by the command can be configured using the <xref:System.Data.Common.DbCommand.CommandText%2A> property.</span></span>  
  
 <span data-ttu-id="328e9-109">In ogni provider di dati .NET Framework fornito con .NET Framework è incluso un oggetto `Command`.</span><span class="sxs-lookup"><span data-stu-id="328e9-109">Each .NET Framework data provider included with the .NET Framework has a `Command` object.</span></span> <span data-ttu-id="328e9-110">Nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbCommand>, in quello per SQL Server un oggetto <xref:System.Data.SqlClient.SqlCommand>, in quello per ODBC un oggetto <xref:System.Data.Odbc.OdbcCommand> e in quello per Oracle un oggetto <xref:System.Data.OracleClient.OracleCommand>.</span><span class="sxs-lookup"><span data-stu-id="328e9-110">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="328e9-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="328e9-111">In This Section</span></span>  
 [<span data-ttu-id="328e9-112">Esegue un comando</span><span class="sxs-lookup"><span data-stu-id="328e9-112">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 <span data-ttu-id="328e9-113">Viene descritto l'oggetto `Command` di ADO.NET e viene illustrato come usarlo per eseguire query e comandi su un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="328e9-113">Describes the ADO.NET `Command` object and how to use it to execute queries and commands against a data source.</span></span>  
  
 [<span data-ttu-id="328e9-114">Configurazione di parametri e tipi di dati di parametro</span><span class="sxs-lookup"><span data-stu-id="328e9-114">Configuring Parameters and Parameter Data Types</span></span>](../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 <span data-ttu-id="328e9-115">Viene descritto l'uso dei parametri di `Command`, inclusa la direzione, i tipi di dati e la sintassi.</span><span class="sxs-lookup"><span data-stu-id="328e9-115">Describes working with `Command` parameters, including direction, data types, and parameter syntax.</span></span>  
  
 [<span data-ttu-id="328e9-116">Generazione di comandi tramite commandbuilders</span><span class="sxs-lookup"><span data-stu-id="328e9-116">Generating Commands with CommandBuilders</span></span>](../../../../docs/framework/data/adonet/generating-commands-with-commandbuilders.md)  
 <span data-ttu-id="328e9-117">Viene descritto come usare compilatori di comandi per generare automaticamente i comandi INSERT, UPDATE e DELETE per un `DataAdapter` in cui è presente il comando SELECT di una singola tabella.</span><span class="sxs-lookup"><span data-stu-id="328e9-117">Describes how to use command builders to automatically generate INSERT, UPDATE, and DELETE commands for a `DataAdapter` that has a single-table SELECT command.</span></span>  
  
 [<span data-ttu-id="328e9-118">Recupero di un singolo valore da un Database</span><span class="sxs-lookup"><span data-stu-id="328e9-118">Obtaining a Single Value from a Database</span></span>](../../../../docs/framework/data/adonet/obtaining-a-single-value-from-a-database.md)  
 <span data-ttu-id="328e9-119">Viene descritto come usare il metodo `ExecuteScalar` di un oggetto `Command` per restituire un singolo valore in una query sul database.</span><span class="sxs-lookup"><span data-stu-id="328e9-119">Describes how to use the `ExecuteScalar` method of a `Command` object to return a single value from a database query.</span></span>  
  
 [<span data-ttu-id="328e9-120">Utilizzo di comandi per modificare i dati</span><span class="sxs-lookup"><span data-stu-id="328e9-120">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 <span data-ttu-id="328e9-121">Viene descritto come usare un provider di dati per eseguire stored procedure o istruzioni DDL (Data Definition Language).</span><span class="sxs-lookup"><span data-stu-id="328e9-121">Describes how to use a data provider to execute stored procedures or data definition language (DDL) statements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328e9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="328e9-122">See Also</span></span>  
 [<span data-ttu-id="328e9-123">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="328e9-123">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="328e9-124">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="328e9-124">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="328e9-125">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="328e9-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="328e9-126">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="328e9-126">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

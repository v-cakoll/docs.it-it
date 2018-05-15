---
title: Connessione a un'origine dati in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 27653c3e1f14e08fc8b5e1225a441072778a0cc8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="fc191-102">Connessione a un'origine dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fc191-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="fc191-103">In ADO.NET viene utilizzato un **connessione** oggetto per la connessione a un'origine dati specifica fornendo informazioni di autenticazione necessarie in una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="fc191-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="fc191-104">Il **connessione** utilizzato dipende dal tipo di origine dati.</span><span class="sxs-lookup"><span data-stu-id="fc191-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="fc191-105">Per ogni provider di dati .NET Framework incluso in .NET Framework è disponibile un oggetto <xref:System.Data.Common.DbConnection>: nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbConnection>, in quello per SQL Server è incluso un oggetto <xref:System.Data.SqlClient.SqlConnection>, in quello per ODBC è incluso un oggetto <xref:System.Data.Odbc.OdbcConnection> e in quello per Oracle è incluso un oggetto <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="fc191-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc191-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="fc191-106">In This Section</span></span>  
 [<span data-ttu-id="fc191-107">Stabilire una connessione</span><span class="sxs-lookup"><span data-stu-id="fc191-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="fc191-108">Viene descritto come utilizzare un **connessione** oggetto per stabilire una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="fc191-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="fc191-109">Eventi di connessione</span><span class="sxs-lookup"><span data-stu-id="fc191-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="fc191-110">Viene descritto come utilizzare un **InfoMessage** recuperare messaggi informativi da un'origine dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="fc191-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc191-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc191-111">See Also</span></span>  
 [<span data-ttu-id="fc191-112">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="fc191-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="fc191-113">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="fc191-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="fc191-114">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="fc191-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="fc191-115">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="fc191-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="fc191-116">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="fc191-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="fc191-117">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="fc191-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

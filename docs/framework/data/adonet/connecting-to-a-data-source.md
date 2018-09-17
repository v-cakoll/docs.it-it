---
title: Connessione a un'origine dati in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: f5788b9b0b19f32d03c917575db7b3f40324c0a2
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964579"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="9e6b3-102">Connessione a un'origine dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9e6b3-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="9e6b3-103">In ADO.NET si utilizza un **connessione** oggetto per la connessione a un'origine dati specifica, fornendo informazioni di autenticazione necessarie in una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="9e6b3-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="9e6b3-104">Il **connessione** oggetto da usare dipende dal tipo di origine dati.</span><span class="sxs-lookup"><span data-stu-id="9e6b3-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="9e6b3-105">Per ogni provider di dati .NET Framework incluso in .NET Framework è disponibile un oggetto <xref:System.Data.Common.DbConnection>: nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbConnection>, in quello per SQL Server è incluso un oggetto <xref:System.Data.SqlClient.SqlConnection>, in quello per ODBC è incluso un oggetto <xref:System.Data.Odbc.OdbcConnection> e in quello per Oracle è incluso un oggetto <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="9e6b3-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e6b3-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="9e6b3-106">In This Section</span></span>  
 [<span data-ttu-id="9e6b3-107">Stabilire una connessione</span><span class="sxs-lookup"><span data-stu-id="9e6b3-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="9e6b3-108">Viene descritto come utilizzare un **connessione** oggetto per stabilire una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="9e6b3-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="9e6b3-109">Eventi di connessione</span><span class="sxs-lookup"><span data-stu-id="9e6b3-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="9e6b3-110">Viene descritto come utilizzare un **InfoMessage** recuperare messaggi informativi da un'origine dati dell'evento.</span><span class="sxs-lookup"><span data-stu-id="9e6b3-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e6b3-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e6b3-111">See Also</span></span>  
 [<span data-ttu-id="9e6b3-112">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="9e6b3-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="9e6b3-113">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="9e6b3-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="9e6b3-114">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="9e6b3-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="9e6b3-115">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="9e6b3-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="9e6b3-116">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="9e6b3-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="9e6b3-117">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="9e6b3-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

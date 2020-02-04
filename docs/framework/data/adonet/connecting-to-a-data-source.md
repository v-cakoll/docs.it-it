---
title: Connessione a un'origine dati
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 84dc15c0965b7ac8209bd9115d611162e57d6dda
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980249"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="783f1-102">Connessione a un'origine dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="783f1-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="783f1-103">In ADO.NET si usa un oggetto **Connection** per connettersi a un'origine dati specifica fornendo le informazioni di autenticazione necessarie in una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="783f1-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="783f1-104">L'oggetto **connessione** utilizzato dipende dal tipo di origine dati.</span><span class="sxs-lookup"><span data-stu-id="783f1-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="783f1-105">Per ogni provider di dati .NET Framework incluso in .NET Framework è disponibile un oggetto <xref:System.Data.Common.DbConnection>: nel provider di dati .NET Framework per OLE DB è incluso un oggetto <xref:System.Data.OleDb.OleDbConnection>, in quello per SQL Server è incluso un oggetto <xref:System.Data.SqlClient.SqlConnection>, in quello per ODBC è incluso un oggetto <xref:System.Data.Odbc.OdbcConnection> e in quello per Oracle è incluso un oggetto <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="783f1-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="783f1-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="783f1-106">In This Section</span></span>  
 [<span data-ttu-id="783f1-107">Stabilire una connessione</span><span class="sxs-lookup"><span data-stu-id="783f1-107">Establishing the Connection</span></span>](establishing-the-connection.md)  
 <span data-ttu-id="783f1-108">Viene descritto come utilizzare un oggetto **Connection** per stabilire una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="783f1-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="783f1-109">Eventi di connessione</span><span class="sxs-lookup"><span data-stu-id="783f1-109">Connection Events</span></span>](connection-events.md)  
 <span data-ttu-id="783f1-110">Viene descritto come utilizzare un evento **InfoMessage** per recuperare messaggi informativi da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="783f1-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="783f1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="783f1-111">See also</span></span>

- [<span data-ttu-id="783f1-112">Stringhe di connessione</span><span class="sxs-lookup"><span data-stu-id="783f1-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="783f1-113">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="783f1-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="783f1-114">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="783f1-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="783f1-115">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="783f1-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="783f1-116">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="783f1-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="783f1-117">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="783f1-117">ADO.NET Overview</span></span>](ado-net-overview.md)

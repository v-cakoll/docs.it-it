---
title: Pool di connessioni
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c7398fbea3b59cafed6f9a7f2f4f0440ef29b80a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="connection-pooling"></a><span data-ttu-id="49496-102">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="49496-102">Connection Pooling</span></span>
<span data-ttu-id="49496-103">La connessione a un'origine dati può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="49496-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="49496-104">Per ridurre al minimo il costo dell'apertura delle connessioni, ADO.NET usa una tecnica di ottimizzazione denominata *il pool di connessioni*, che consente di ridurre il costo di apertura e chiusura delle connessioni ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="49496-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="49496-105">Per i provider di dati .NET Framework il pool di connessioni viene gestito in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="49496-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="49496-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="49496-106">In This Section</span></span>  
 [<span data-ttu-id="49496-107">SQL Server pool di connessioni (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="49496-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="49496-108">Viene fornita una panoramica sul pool di connessioni e ne viene descritto il funzionamento in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49496-108">Provides an overview of connection pooling and describes how connection pooling works in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="49496-109">OLE DB, ODBC e Oracle Connection Pooling</span><span class="sxs-lookup"><span data-stu-id="49496-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="49496-110">Viene descritto l'uso del pool di connessioni con i provider di dati .NET Framework per OLE DB, ODBC e Oracle.</span><span class="sxs-lookup"><span data-stu-id="49496-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49496-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49496-111">See Also</span></span>  
 [<span data-ttu-id="49496-112">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="49496-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="49496-113">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="49496-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

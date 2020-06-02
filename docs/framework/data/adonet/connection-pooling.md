---
title: Pool di connessioni
description: Informazioni sul pool di connessioni, una tecnica di ottimizzazione utilizzata da ADO.NET per ridurre al minimo il costo dell'apertura delle connessioni alle origini dati.
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: b8f89dfda7edbde14dbb5945f10f2284ac43c3d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287090"
---
# <a name="connection-pooling"></a><span data-ttu-id="e947d-103">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="e947d-103">Connection Pooling</span></span>
<span data-ttu-id="e947d-104">La connessione a un'origine dati può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="e947d-104">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="e947d-105">Per ridurre al minimo il costo dell'apertura delle connessioni, ADO.NET usa una tecnica di ottimizzazione denominata *pool*di connessioni, che riduce al minimo il costo di apertura e chiusura ripetute delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="e947d-105">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="e947d-106">Per i provider di dati .NET Framework il pool di connessioni viene gestito in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="e947d-106">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e947d-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e947d-107">In This Section</span></span>  
 [<span data-ttu-id="e947d-108">Pool di connessioni di SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="e947d-108">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="e947d-109">Viene fornita una panoramica del pool di connessioni e viene descritto il funzionamento del pool di connessioni in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e947d-109">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="e947d-110">Pool di connessioni OLE DB, ODBC e Oracle</span><span class="sxs-lookup"><span data-stu-id="e947d-110">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="e947d-111">Viene descritto l'uso del pool di connessioni con i provider di dati .NET Framework per OLE DB, ODBC e Oracle.</span><span class="sxs-lookup"><span data-stu-id="e947d-111">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e947d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e947d-112">See also</span></span>

- [<span data-ttu-id="e947d-113">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e947d-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="e947d-114">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e947d-114">ADO.NET Overview</span></span>](ado-net-overview.md)

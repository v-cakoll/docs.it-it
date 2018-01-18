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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7205bc307af6a4a9f307b84a7b3875b77dadb765
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="connection-pooling"></a><span data-ttu-id="ecc24-102">Pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="ecc24-102">Connection Pooling</span></span>
<span data-ttu-id="ecc24-103">La connessione a un'origine dati può richiedere molto tempo.</span><span class="sxs-lookup"><span data-stu-id="ecc24-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="ecc24-104">Per ridurre al minimo il costo dell'apertura delle connessioni, ADO.NET usa una tecnica di ottimizzazione denominata *il pool di connessioni*, che consente di ridurre il costo di apertura e chiusura delle connessioni ripetutamente.</span><span class="sxs-lookup"><span data-stu-id="ecc24-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="ecc24-105">Per i provider di dati .NET Framework il pool di connessioni viene gestito in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="ecc24-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ecc24-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ecc24-106">In This Section</span></span>  
 [<span data-ttu-id="ecc24-107">Pool di connessioni SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="ecc24-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="ecc24-108">Viene fornita una panoramica sul pool di connessioni e ne viene descritto il funzionamento in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecc24-108">Provides an overview of connection pooling and describes how connection pooling works in [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ecc24-109">Pool di connessioni OLE DB, ODBC e Oracle</span><span class="sxs-lookup"><span data-stu-id="ecc24-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="ecc24-110">Viene descritto l'uso del pool di connessioni con i provider di dati .NET Framework per OLE DB, ODBC e Oracle.</span><span class="sxs-lookup"><span data-stu-id="ecc24-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc24-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecc24-111">See Also</span></span>  
 [<span data-ttu-id="ecc24-112">Recupero e modifica di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ecc24-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="ecc24-113">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="ecc24-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

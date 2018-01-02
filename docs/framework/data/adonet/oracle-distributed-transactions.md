---
title: Transazioni distribuite Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 104befd25d30d050fee0a053a413b13fe6d1fc51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="a0066-102">Transazioni distribuite Oracle</span><span class="sxs-lookup"><span data-stu-id="a0066-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="a0066-103">Se rileva una transazione attiva, l'oggetto <xref:System.Data.OracleClient.OracleConnection> esegue l'inserimento automatico in una transazione distribuita esistente.</span><span class="sxs-lookup"><span data-stu-id="a0066-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="a0066-104">L'inserimento automatico in una transazione viene eseguito anche quando la connessione viene aperta o recuperata dal pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="a0066-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="a0066-105">È possibile disabilitare l'inserimento automatico in transazioni esistenti specificando</span><span class="sxs-lookup"><span data-stu-id="a0066-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="a0066-106">come parametro della stringa di connessione per un tipo <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="a0066-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0066-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0066-107">See Also</span></span>  
 [<span data-ttu-id="a0066-108">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a0066-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="a0066-109">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="a0066-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

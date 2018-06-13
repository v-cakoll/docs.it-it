---
title: Transazioni distribuite Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 0e9dcb30eb1962071d7154d4bbf929871c8a12d2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765201"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="9ddc2-102">Transazioni distribuite Oracle</span><span class="sxs-lookup"><span data-stu-id="9ddc2-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="9ddc2-103">Se rileva una transazione attiva, l'oggetto <xref:System.Data.OracleClient.OracleConnection> esegue l'inserimento automatico in una transazione distribuita esistente.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="9ddc2-104">L'inserimento automatico in una transazione viene eseguito anche quando la connessione viene aperta o recuperata dal pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="9ddc2-105">È possibile disabilitare l'inserimento automatico in transazioni esistenti specificando</span><span class="sxs-lookup"><span data-stu-id="9ddc2-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="9ddc2-106">come parametro della stringa di connessione per un tipo <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="9ddc2-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddc2-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ddc2-107">See Also</span></span>  
 [<span data-ttu-id="9ddc2-108">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9ddc2-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="9ddc2-109">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="9ddc2-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

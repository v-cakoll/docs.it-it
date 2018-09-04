---
title: Transazioni distribuite Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: a3b8a50b42b945a0cdc1cbfbc4cc9eab835e90e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505399"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="f0321-102">Transazioni distribuite Oracle</span><span class="sxs-lookup"><span data-stu-id="f0321-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="f0321-103">Se rileva una transazione attiva, l'oggetto <xref:System.Data.OracleClient.OracleConnection> esegue l'inserimento automatico in una transazione distribuita esistente.</span><span class="sxs-lookup"><span data-stu-id="f0321-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="f0321-104">L'inserimento automatico in una transazione viene eseguito anche quando la connessione viene aperta o recuperata dal pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="f0321-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="f0321-105">È possibile disabilitare l'inserimento automatico in transazioni esistenti specificando</span><span class="sxs-lookup"><span data-stu-id="f0321-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="f0321-106">come parametro della stringa di connessione per un tipo <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="f0321-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0321-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0321-107">See Also</span></span>  
 [<span data-ttu-id="f0321-108">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f0321-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [<span data-ttu-id="f0321-109">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="f0321-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

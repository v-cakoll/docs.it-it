---
title: Transazioni distribuite Oracle
ms.date: 03/30/2017
ms.assetid: c340ca81-ef79-402f-b204-c5156b890fe5
ms.openlocfilehash: 4af1c98818f1929850c5ae78892c64993a93d4d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116217"
---
# <a name="oracle-distributed-transactions"></a><span data-ttu-id="67c29-102">Transazioni distribuite Oracle</span><span class="sxs-lookup"><span data-stu-id="67c29-102">Oracle Distributed Transactions</span></span>
<span data-ttu-id="67c29-103">Se rileva una transazione attiva, l'oggetto <xref:System.Data.OracleClient.OracleConnection> esegue l'inserimento automatico in una transazione distribuita esistente.</span><span class="sxs-lookup"><span data-stu-id="67c29-103">The <xref:System.Data.OracleClient.OracleConnection> object automatically enlists in an existing distributed transaction if it determines that a transaction is active.</span></span> <span data-ttu-id="67c29-104">L'inserimento automatico in una transazione viene eseguito anche quando la connessione viene aperta o recuperata dal pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="67c29-104">Automatic transaction enlistment occurs when the connection is opened or retrieved from the connection pool.</span></span> <span data-ttu-id="67c29-105">È possibile disabilitare l'inserimento automatico in transazioni esistenti specificando</span><span class="sxs-lookup"><span data-stu-id="67c29-105">You can disable auto-enlistment in existing transactions by specifying</span></span>  
  
```  
Enlist=false  
```  
  
 <span data-ttu-id="67c29-106">come parametro della stringa di connessione per un tipo <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="67c29-106">as a connection string parameter for an <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c29-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67c29-107">See also</span></span>

- [<span data-ttu-id="67c29-108">Oracle e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="67c29-108">Oracle and ADO.NET</span></span>](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [<span data-ttu-id="67c29-109">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="67c29-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

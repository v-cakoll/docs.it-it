---
title: 'Mitigazione: Periodo di blocco del pool'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8749e2d7b91e611ee153c6f36708fa34a44ecccd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-pool-blocking-period"></a><span data-ttu-id="a47c1-102">Mitigazione: Periodo di blocco del pool</span><span class="sxs-lookup"><span data-stu-id="a47c1-102">Mitigation: Pool Blocking Period</span></span>
<span data-ttu-id="a47c1-103">Il periodo di blocco del pool di connessioni è stato rimosso per le connessioni ai database SQL di Azure.</span><span class="sxs-lookup"><span data-stu-id="a47c1-103">The connection pool blocking period has been removed for connections to Azure SQL databases.</span></span>  
  
## <a name="additional-description"></a><span data-ttu-id="a47c1-104">Descrizione aggiuntiva</span><span class="sxs-lookup"><span data-stu-id="a47c1-104">Additional description</span></span>  
 <span data-ttu-id="a47c1-105">In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] e versioni precedenti, se un'applicazione rileva un errore di connessione temporanea mentre si connette a un database, non è possibile ritentare subito la connessione, perché il pool di connessioni memorizza l'errore nella cache e lo rigenera per un periodo compreso tra 5 secondi e 1 minuto. Per altre informazioni, vedere [Pool di connessioni di SQL Server (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="a47c1-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, when an app encounters a transient connection failure when connecting to a database, the connection attempt cannot be retried quickly, because the connection pool caches the error and re-throws it for 5 seconds to 1 min. For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span> <span data-ttu-id="a47c1-106">Questo comportamento può causare problemi con le connessioni a database SQL di Azure, che spesso hanno esito negativo in caso di errori temporanei che vengono generalmente ripristinati nell'arco di pochi secondi.</span><span class="sxs-lookup"><span data-stu-id="a47c1-106">This behavior is problematic for connections to Azure SQL databases, which often fail with transient errors that are typically recovered from within a few seconds.</span></span> <span data-ttu-id="a47c1-107">Con la funzionalità di blocco del pool di connessioni, l'app non può connettersi al database per un periodo esteso, anche se il database è disponibile.</span><span class="sxs-lookup"><span data-stu-id="a47c1-107">The connection pool blocking feature means that the app cannot connect to the database for an extensive period, even though the database is available.</span></span> <span data-ttu-id="a47c1-108">Questo può generare problemi soprattutto alle app Web che si connettono a database SQL di Azure e devono eseguire il rendering entro pochi secondi.</span><span class="sxs-lookup"><span data-stu-id="a47c1-108">This behavior is particularly problematic for web apps that connect to Azure SQL databases and that need to render within a few seconds.</span></span>  
  
 <span data-ttu-id="a47c1-109">A partire da [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], in caso di richieste di apertura connessioni a database SQL di Azure noti (*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), eventuali errori di apertura connessioni non vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="a47c1-109">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], for connection open requests to known Azure SQL databases (*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), connection open errors are not cached.</span></span> <span data-ttu-id="a47c1-110">Per tutti gli altri tentativi di connessione continua a essere applicato il periodo di blocco del pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="a47c1-110">For all other connection attempts, the connection pool blocking period continues to be enforced.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="a47c1-111">Impatto</span><span class="sxs-lookup"><span data-stu-id="a47c1-111">Impact</span></span>  
 <span data-ttu-id="a47c1-112">Questa modifica consente di ritentare immediatamente l'apertura di una connessione a database SQL di Azure, migliorando così le prestazioni delle app abilitate per il cloud.</span><span class="sxs-lookup"><span data-stu-id="a47c1-112">This change allows the connection open attempt to be retried immediately for Azure SQL databases, thereby improving the performance of cloud-enabled apps.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="a47c1-113">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="a47c1-113">Mitigation</span></span>  
 <span data-ttu-id="a47c1-114">Per le app che subiscono effetti negativi da questa modifica, è possibile configurare il periodo di blocco del pool di connessioni impostando la nuova proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A>.</span><span class="sxs-lookup"><span data-stu-id="a47c1-114">For apps that are adversely affected by this change, the connection pool blocking period can be configured by setting the new <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property.</span></span>  <span data-ttu-id="a47c1-115">Il valore della proprietà è un membro dell'enumerazione <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> che può assumere uno dei tre valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="a47c1-115">The value of the property is a member of the <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> enumeration that can take either of three values:</span></span>  
  
-   `PoolBlockingPeriod.AlwaysBlock` 
  
-   `PoolBlockingPeriod.Auto`  
  
-   `PoolBlockingPeriod.NeverBlock` 
  
 <span data-ttu-id="a47c1-116">È possibile ripristinare il comportamento precedente impostando la proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> su `PoolBlockingPeriod.AlwaysBlock`.</span><span class="sxs-lookup"><span data-stu-id="a47c1-116">The previous behavior can be restored by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property to `PoolBlockingPeriod.AlwaysBlock`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47c1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a47c1-117">See Also</span></span>  
 [<span data-ttu-id="a47c1-118">Modifiche al runtime</span><span class="sxs-lookup"><span data-stu-id="a47c1-118">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)

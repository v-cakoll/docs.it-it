---
title: 'Mitigazione: periodo di blocco del pool'
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4c90a75ebbb9e4bc6248aadd709be8b5285ecd6
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409120"
---
# <a name="mitigation-pool-blocking-period"></a>Mitigazione: periodo di blocco del pool
Il periodo di blocco del pool di connessioni è stato rimosso per le connessioni ai database SQL di Azure.  
  
## <a name="additional-description"></a>Descrizione aggiuntiva  
 In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] e versioni precedenti, se un'applicazione rileva un errore di connessione temporanea mentre si connette a un database, non è possibile ritentare subito la connessione, perché il pool di connessioni memorizza l'errore nella cache e lo rigenera per un periodo compreso tra 5 secondi e 1 minuto. Per altre informazioni, vedere [Pool di connessioni di SQL Server (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md). Questo comportamento può causare problemi con le connessioni a database SQL di Azure, che spesso hanno esito negativo in caso di errori temporanei che vengono generalmente ripristinati nell'arco di pochi secondi. Con la funzionalità di blocco del pool di connessioni, l'app non può connettersi al database per un periodo esteso, anche se il database è disponibile. Questo può generare problemi soprattutto alle app Web che si connettono a database SQL di Azure e devono eseguire il rendering entro pochi secondi.  
  
 A partire da [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], in caso di richieste di apertura connessioni a database SQL di Azure noti (*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), eventuali errori di apertura connessioni non vengono memorizzati nella cache. Per tutti gli altri tentativi di connessione continua a essere applicato il periodo di blocco del pool di connessioni.  
  
## <a name="impact"></a>Impatto  
 Questa modifica consente di ritentare immediatamente l'apertura di una connessione a database SQL di Azure, migliorando così le prestazioni delle app abilitate per il cloud.  
  
## <a name="mitigation"></a>Mitigazione  
 Per le app che subiscono effetti negativi da questa modifica, è possibile configurare il periodo di blocco del pool di connessioni impostando la nuova proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType>.  Il valore della proprietà è un membro dell'enumerazione <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> che può assumere uno dei tre valori seguenti:  
  
-   <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>
  
-   <xref:System.Data.SqlClient.PoolBlockingPeriod.Auto?displayProperty=nameWithType>
  
-   <xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock?displayProperty=nameWithType>
  
 È possibile ripristinare il comportamento precedente impostando la proprietà <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> su <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche
- [Modifiche al runtime](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)

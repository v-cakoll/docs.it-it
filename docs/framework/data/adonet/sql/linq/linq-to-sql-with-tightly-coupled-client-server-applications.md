---
title: LINQ to SQL con applicazioni client/server strettamente accoppiate
ms.date: 03/30/2017
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
ms.openlocfilehash: f094bb319a4ca5241e60993770c9c49c3151635c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="linq-to-sql-with-tightly-coupled-client-server-applications"></a>LINQ to SQL con applicazioni client/server strettamente accoppiate
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] può essere utilizzato nel livello intermedio con i client intelligenti strettamente collegati nel livello di presentazione. Gli scenari che prevedono l'accesso ai dati di sola lettura, nessun controllo di concorrenza ottimistica o concorrenza ottimistica con timestamp, non sono molto più complessi degli scenari non remoti. Tuttavia, quando un database richiede i controlli di concorrenza ottimistica con valori originali, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non fornisce il livello di supporto per eseguire un round trip dei dati presenti nei dataset. Un livello intermedio di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] può però scambiare dati con client su qualsiasi piattaforma.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in [!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)] non fornisce alcuna infrastruttura per il rilevamento dello stato dell'entità dopo serializzate a un client. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] consente le architetture orientate ai servizi dove le interazioni tra i livelli di dati e la presentazione sono piccole e relativamente atomiche ma non esegue alcun round trip dei valori originali. Pertanto, se si desidera usare un client intelligente strettamente collegato con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e un database usa la concorrenza ottimistica con i valori originali, sarà necessario implementare il meccanismo personalizzato di comunicazione delle modifiche tra il livello di presentazione e il livello intermedio. Usare Progettazione sistemi per stabilire se effettuare questa operazione aggiuntiva a fronte dei vantaggi che [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornisce nel livello intermedio. D'altra parte, se il database ha timestamp, non è necessario una logica personalizzata per il rilevamento delle modifiche.  
  
## <a name="see-also"></a>Vedere anche  
 [Applicazioni a più livelli e remote con LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [Più livelli di LINQ to SQL con Servizi Web](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
 [Uso dei set di dati nelle applicazioni a più livelli](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)

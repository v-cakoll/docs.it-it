---
title: '&lt;activityScheduledQueries&gt; di WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97726c7faa08477351d4496650b6c08b643cdb76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a>&lt;activityScheduledQueries&gt; di WCF
Rappresenta una raccolta di query usate per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre. La query è necessaria affinché un partecipante del rilevamento sottoscriva i record pianificati dell'attività.  
  
 Per ulteriori informazioni sulla query del profilo di rilevamento, vedere [profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
 \<System. ServiceModel >  
\<rilevamento >  
\<trackingProfile >  
\<flusso di lavoro >  
\<activityScheduledQueries >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<activityScheduledQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|Query usata per rilevare un'attività pianificata per l'esecuzione da parte di un'attività padre.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<flusso di lavoro >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|Elemento di configurazione contenente tutte le query per un flusso di lavoro specifico identificato dalla proprietà `activityDefinitionId`.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [Rilevamento e analisi del flusso di lavoro](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Profili di rilevamento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

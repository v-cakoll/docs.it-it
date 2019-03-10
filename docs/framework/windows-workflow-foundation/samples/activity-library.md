---
title: Libreria di attività
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: b701d382c25644181b23f3c0f0cd8e019b8d37d1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709836"
---
# <a name="activity-library"></a>Libreria di attività
In questa sezione è inclusi esempi che illustrano attività personalizzate avanzate in Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>In questa sezione

 [Attività personalizzata SendMail](sendmail-custom-activity.md)  
 Viene illustrato come creare un'attività personalizzata che deriva da <xref:System.Activities.AsyncCodeActivity> per inviare messaggi di posta elettronica tramite il protocollo SMTP da usare in un'applicazione flusso di lavoro.  
  
 [ThrottledParallelForEach](throttled-parallel-foreach.md)  
 Viene illustrato che l'attività `ThrottleParallelForEach` è simile all'attività <xref:System.Activities.Statements.ParallelForEach%601> con l'unica eccezione che consente l'impostazione di un fattore di concorrenza per limitare il numero di rami simultanei da eseguire.
  
 [Attività di accesso al database](database-access-activities.md)  
 Viene illustrato come creare attività che consentono l'accesso ai database per recuperare o modificare informazioni e utilizzare [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) per accedere al database.  
  
 [Attività ExternalizedPolicy in .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Viene illustrato come l'attività ExternalizedPolicy4 consenta l'esecuzione esistenti di Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> gli oggetti in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) direttamente tramite il motore regole vale a dire disponibile in WF 3.5. 
  
 [Attività ForEach non generica](non-generic-foreach.md)  
 Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ForEach%601>.  
  
 [Attività ParallelForEach non generica](non-generic-parallelforeach.md)  
 Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Ottenere WorkflowInstanceId](get-workflowinstanceid.md)  
 Viene illustrato come usare l'attività personalizzata, `GetWorkflowInstanceId`, per restituire l'ID istanza del flusso di lavoro.

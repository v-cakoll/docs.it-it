---
title: Libreria di attività
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 7e8777d0068e6cca9c9324a6fd2668e6ff9e9da7
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778960"
---
# <a name="activity-library"></a>Libreria di attività
In questa sezione è inclusi esempi che illustrano attività personalizzate avanzate in Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>In questa sezione

 [Attività personalizzata SendMail](../../../../docs/framework/windows-workflow-foundation/samples/sendmail-custom-activity.md)  
 Viene illustrato come creare un'attività personalizzata che deriva da <xref:System.Activities.AsyncCodeActivity> per inviare messaggi di posta elettronica tramite il protocollo SMTP da usare in un'applicazione flusso di lavoro.  
  
 [ThrottledParallelForEach](../../../../docs/framework/windows-workflow-foundation/samples/throttled-parallel-foreach.md)  
 Viene illustrato che l'attività `ThrottleParallelForEach` è simile all'attività <xref:System.Activities.Statements.ParallelForEach%601> con l'unica eccezione che consente l'impostazione di un fattore di concorrenza per limitare il numero di rami simultanei da eseguire.
  
 [Attività di accesso al database](../../../../docs/framework/windows-workflow-foundation/samples/database-access-activities.md)  
 Viene illustrato come creare attività che consentono l'accesso ai database per recuperare o modificare informazioni e utilizzare [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) per accedere al database.  
  
 [Attività ExternalizedPolicy in .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/externalized-policy-activity-in-net-framework-4-5.md)  
 Viene illustrato come l'attività ExternalizedPolicy4 consenta l'esecuzione esistenti di Windows Workflow Foundation in [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> gli oggetti in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) direttamente tramite il motore regole vale a dire disponibile in WF 3.5. 
  
 [Attività ForEach non generica](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-foreach.md)  
 Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ForEach%601>.  
  
 [Attività ParallelForEach non generica](../../../../docs/framework/windows-workflow-foundation/samples/non-generic-parallelforeach.md)  
 Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Ottenere WorkflowInstanceId](../../../../docs/framework/windows-workflow-foundation/samples/get-workflowinstanceid.md)  
 Viene illustrato come usare l'attività personalizzata, `GetWorkflowInstanceId`, per restituire l'ID istanza del flusso di lavoro.

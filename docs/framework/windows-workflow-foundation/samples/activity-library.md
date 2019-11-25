---
title: Libreria di attività
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: 15260fc2ad96e1761a8a41ccc84b2c199e3d448a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283148"
---
# <a name="activity-library"></a>Libreria di attività
Questa sezione contiene esempi che illustrano le attività personalizzate avanzate in Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>Contenuto della sezione

 [Attività personalizzata SendMail](sendmail-custom-activity.md)  
 Viene illustrato come creare un'attività personalizzata che deriva da <xref:System.Activities.AsyncCodeActivity> per inviare messaggi di posta elettronica tramite il protocollo SMTP da usare in un'applicazione flusso di lavoro.  
  
 [ThrottledParallelForEach](throttled-parallel-foreach.md)  
 Viene illustrato che l'attività `ThrottleParallelForEach` è simile all'attività <xref:System.Activities.Statements.ParallelForEach%601> con l'unica eccezione che consente l'impostazione di un fattore di concorrenza per limitare il numero di rami simultanei da eseguire.
  
 [Attività di accesso al database](database-access-activities.md)  
 Viene illustrato come creare attività che consentono l'accesso ai database per recuperare o modificare informazioni e utilizzare [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) per accedere al database.  
  
 [Attività ExternalizedPolicy in .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Viene illustrato il modo in cui l'attività ExternalizedPolicy4 consente l'esecuzione di Windows Workflow Foundation esistenti in .NET Framework 3,5 (WF 3,5) <xref:System.Workflow.Activities.Rules.RuleSet> oggetti in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4,5) direttamente tramite il motore regole fornito in WF 3,5. 
  
 [Attività ForEach non generica](non-generic-foreach.md)  
 Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ForEach%601>.  
  
 [Attività ParallelForEach non generica](non-generic-parallelforeach.md)  
 Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Ottenere WorkflowInstanceId](get-workflowinstanceid.md)  
 Viene illustrato come usare l'attività personalizzata, `GetWorkflowInstanceId`, per restituire l'ID istanza del flusso di lavoro.

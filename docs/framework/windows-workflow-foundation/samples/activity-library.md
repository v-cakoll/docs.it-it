---
title: Libreria di attività
ms.date: 03/30/2017
ms.assetid: 5323e9d4-71d6-47eb-bfa6-31feac62044d
ms.openlocfilehash: fae2a94b5e5e776625aa7f26700980640b66afd4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142901"
---
# <a name="activity-library"></a>Libreria di attività
Questa sezione contiene esempi che illustrano le attività personalizzate avanzate in Windows Workflow Foundation (WF).  
  
## <a name="in-this-section"></a>Contenuto della sezione

 [Attività personalizzata SendMail](sendmail-custom-activity.md)  
 Viene illustrato come creare un'attività personalizzata che deriva da <xref:System.Activities.AsyncCodeActivity> per inviare messaggi di posta elettronica tramite il protocollo SMTP da usare in un'applicazione flusso di lavoro.  
  
 [ThrottledParallelForEach](throttled-parallel-foreach.md)  
 Viene illustrato che l'attività `ThrottleParallelForEach` è simile all'attività <xref:System.Activities.Statements.ParallelForEach%601> con l'unica eccezione che consente l'impostazione di un fattore di concorrenza per limitare il numero di rami simultanei da eseguire.
  
 [Attività di accesso al database](database-access-activities.md)  
 Viene illustrato come creare attività che consentono l'accesso ai database per recuperare o modificare le informazioni e utilizzare [ADO.NET](../../data/adonet/index.md) per accedere al database.  
  
 [Attività ExternalizedPolicy in .NET Framework 4.5](externalized-policy-activity-in-net-framework-4-5.md)  
 Viene illustrato come l'attività ExternalizedPolicy4 consente l'esecuzione di oggetti Windows Workflow <xref:System.Workflow.Activities.Rules.RuleSet> Foundation in .NET Framework 3.5 (WF 3.5) esistenti in Windows Workflow Foundation in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) direttamente utilizzando il motore regole fornito in WF 3.5.
  
 [Attività ForEach non generica](non-generic-foreach.md)  
 Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ForEach%601>.  
  
 [Attività ParallelForEach non generica](non-generic-parallelforeach.md)  
 Viene illustrato come creare una versione non generica dell'attività <xref:System.Activities.Statements.ParallelForEach%601>.  
  
 [Ottenere WorkflowInstanceId](get-workflowinstanceid.md)  
 Viene illustrato come usare l'attività personalizzata, `GetWorkflowInstanceId`, per restituire l'ID istanza del flusso di lavoro.

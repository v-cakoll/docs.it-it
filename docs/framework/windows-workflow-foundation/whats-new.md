---
title: Novità&#39;s New in Windows Workflow Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Workflow Foundation [WF], what's new
- WF [WF], what's new
ms.assetid: 11f96014-001e-41a0-bcc2-d0684a52fa43
ms.openlocfilehash: d45c16d4f16c239d1c1c8116b4b41dd41f8a953d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518437"
---
# <a name="what39s-new-in-windows-workflow-foundation"></a>Novità&#39;s New in Windows Workflow Foundation
Windows Workflow Foundation (WF) in [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] cambia diversi paradigmi di sviluppo rispetto alle versioni precedenti. I flussi di lavoro sono ora più facili da creare, eseguire e gestire e consentono di implementare un host della nuova funzionalità. Per ulteriori informazioni sulla migrazione .NET 3.0 e 3.5 di .NET del flusso di lavoro di applicazioni di utilizzare la versione più recente, vedere [materiale sussidiario sulla migrazione](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
## <a name="workflow-activity-model"></a>Modello di attività del flusso di lavoro  
 L'attività è ora l'unità di base della creazione di un flusso di lavoro in sostituzione delle classi <xref:System.Workflow.Activities.SequentialWorkflowActivity> o <xref:System.Workflow.Activities.StateMachineWorkflowActivity>. La classe <xref:System.Activities.Activity> fornisce l'astrazione di base del comportamento del flusso di lavoro. Gli autori di attività possono implementare <xref:System.Activities.CodeActivity> per sfruttare la funzionalità di base delle attività personalizzate oppure <xref:System.Activities.NativeActivity> per sfruttare la funzionalità delle attività personalizzate che usa l'intera gamma del runtime. <xref:System.Activities.Activity> è una classe utilizzata dagli autori di attività per esprimere nuovi comportamenti in modo dichiarativo in altri termini <xref:System.Activities.NativeActivity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, oppure <xref:System.Activities.DynamicActivity> oggetti, se vengono sviluppati in modo personalizzato o incluso nel [attività incorporata Libreria](../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md).  
  
## <a name="rich-composite-activity-options"></a>Opzioni delle attività composite avanzate  
 <xref:System.Activities.Statements.Flowchart> è una nuova e potente attività del flusso di controllo che consente agli autori di creare modelli di cicli arbitrari e di branching condizionale. <xref:System.Activities.Statements.Flowchart> fornisce un modello di programmazione basato sugli eventi che in precedenza era disponibile solo con <xref:System.Workflow.Activities.StateMachineWorkflowActivity>. I flussi di lavoro procedurali traggono profitto dalle nuove attività di controllo del flusso che modellano le strutture tradizionali di controllo del flusso, ad esempio gli oggetti <xref:System.Activities.Statements.TryCatch> e <xref:System.Activities.Statements.Switch%601>.  
  
## <a name="expanded-built-in-activity-library"></a>Libreria di attività incorporata estesa  
 Le nuove funzionalità della libreria di attività includono:  
  
-   Nuove attività di controllo del flusso, ad esempio <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.Pick>, <xref:System.Activities.Statements.TryCatch>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Switch%601> e <xref:System.Activities.Statements.ParallelForEach%601>.  
  
-   Attività per la modifica dei dati dei membri, ad esempio <xref:System.Activities.Statements.Assign> e attività di raccolta come <xref:System.Activities.Statements.AddToCollection%601>.  
  
-   Attività per il controllo delle transazioni, ad esempio <xref:System.Activities.Statements.TransactionScope> e <xref:System.Activities.Statements.Compensate>.  
  
-   Nuove attività di messaggistica come <xref:System.ServiceModel.Activities.SendContent> e <xref:System.ServiceModel.Activities.ReceiveReply>.  
  
## <a name="explicit-activity-data-model"></a>Modello di dati delle attività esplicite  
 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] include nuove opzioni per l'archiviazione o lo spostamento di dati. I dati possono essere archiviati in un'attività tramite l'oggetto <xref:System.Activities.Variable>. Quando si spostano dati all'interno e all'esterno di un'attività, i tipi di argomento specializzati vengono usati per determinare in quale direzione si stanno spostando i dati. Questi tipi sono <xref:System.Activities.InArgument>, <xref:System.Activities.InOutArgument> e <xref:System.Activities.OutArgument>. Per altre informazioni, vedere [modello di dati di Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/data-model.md).  
  
## <a name="enhanced-hosting-persistence-and-tracking-options"></a>Opzioni migliorate di hosting, persistenza e rilevamento  
 In [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] sono stati apportati i seguenti miglioramenti di persistenza:  
  
-   Sono disponibili più opzioni per l'esecuzione dei flussi di lavoro, inclusi gli oggetti <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.Activities.WorkflowApplication> e <xref:System.Activities.WorkflowInvoker>.  
  
-   I dati relativi allo stato del flusso di lavoro possono essere resi persistenti in modo esplicito usando l'attività <xref:System.Activities.Statements.Persist>.  
  
-   Un host può rendere persistente un oggetto <xref:System.Activities.ActivityInstance> senza scaricarlo.  
  
-   Un flusso di lavoro può specificare aree di non persistenza durante l'uso di dati che non possono essere resi persistenti in modo che la persistenza venga posticipata finché l'area di non persistenza non viene chiusa.  
  
-   Le transazioni possono essere propagate in un flusso di lavoro tramite l'oggetto <xref:System.Activities.Statements.TransactionScope>.  
  
-   Il rilevamento viene portato a termine più facilmente usando l'oggetto <xref:System.Activities.Tracking.TrackingParticipant>.  
  
-   Il rilevamento nel registro eventi di sistema viene fornito tramite l'oggetto <xref:System.Activities.Tracking.EtwTrackingParticipant>.  
  
-   La ripresa di un flusso di lavoro in sospeso è ora gestita usando un oggetto <xref:System.Activities.Bookmark>.  
  
## <a name="easier-ability-to-extend-wf-designer-experience"></a>Estensione più semplice dell'esperienza dell'utilità di progettazione di WF  
 La nuova finestra di progettazione di WF si basa su Windows Presentation Foundation (WPF) e fornisce un modello più semplice da utilizzare durante la riallocazione della finestra di progettazione di WF all'esterno di Visual Studio e fornisce meccanismi più facili per la creazione di ActivityDesigner personalizzati. Per altre informazioni, vedere [personalizzare l'esperienza di progettazione del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md).

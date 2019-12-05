---
title: Utilizzo delle attività WF di .NET Framework 3.0 in .NET Framework 4 con l'attività Interop
ms.date: 03/30/2017
ms.assetid: 71f112ba-abb0-46f7-b05f-a5d2eb9d0c5c
ms.openlocfilehash: fb9536d5ee7a31039d77deffc3c0b0c7a6263b66
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802570"
---
# <a name="using-net-framework-30-wf-activities-in-net-framework-4-with-the-interop-activity"></a>Utilizzo delle attività WF di .NET Framework 3.0 in .NET Framework 4 con l'attività Interop
L'attività <xref:System.Activities.Statements.Interop> è un'attività [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] (WF 4,5) che esegue il wrapping di un'attività .NET Framework 3,5 (WF 3,5) in un flusso di lavoro [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. L'attività di WF 3 può essere una singola attività foglia o un intero albero di attività. L'esecuzione (incluso l'annullamento e la gestione delle eccezioni) e la persistenza dell'attività .NET Framework 3,5 si verificano nel contesto dell'istanza del flusso di lavoro [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] in esecuzione.  
  
> [!NOTE]
> L'attività <xref:System.Activities.Statements.Interop> non viene visualizzata nella casella degli strumenti di progettazione flussi di lavoro a meno che l'impostazione del **Framework di destinazione** del progetto del flusso di lavoro non sia impostata su **.NET Framework 4,5**.  
  
## <a name="criteria-for-using-a-wf-3-activity-with-an-interop-activity"></a>Criteri per l'uso di un'attività di WF 3 con un'attività di interoperabilità  
 Affinché un'attività di WF 3 venga eseguita correttamente all'interno di un'attività <xref:System.Activities.Statements.Interop>, devono essere soddisfatti i seguenti criteri:  
  
- L'attività di WF 3 deve derivare dall'oggetto <xref:System.Workflow.ComponentModel.Activity?displayProperty=nameWithType>.  
  
- L'attività di WF 3 deve essere dichiarata come `public` e non può essere `abstract`.  
  
- L'attività di WF 3 deve avere un costruttore pubblico senza parametri.  
  
- A causa delle limitazioni nei tipi di interfaccia che possono essere supportati dall'attività <xref:System.Activities.Statements.Interop>, gli oggetti <xref:System.Workflow.Activities.HandleExternalEventActivity> e <xref:System.Workflow.Activities.CallExternalMethodActivity> non possono essere usati direttamente, tuttavia è possibile usare attività derivative create usando lo strumento relativo alle attività di comunicazione del flusso di lavoro (WCA.exe). Per informazioni dettagliate, vedere [Windows Workflow Foundation Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms734408(v=vs.90)) .  
  
## <a name="configuring-a-wf-3-activity-within-an-interop-activity"></a>Configurazione di un'attività di WF 3 all'interno di un'attività di interoperabilità  
 Per configurare e passare dati all'interno e all'esterno di un'attività di WF 3, nel limite dell'interazione, le proprietà dei metadati e quelle dell'attività di WF 3 sono esposte dall'attività <xref:System.Activities.Statements.Interop>. Le proprietà dei metadati dell'attività di WF 3 (ad esempio <xref:System.Workflow.ComponentModel.Activity.Name%2A>) sono esposte tramite la raccolta <xref:System.Activities.Statements.Interop.ActivityMetaProperties%2A>. Si tratta di una raccolta di coppie nome-valore usata per definire i valori delle proprietà dei metadati dell'attività di WF 3. Una proprietà dei metadati è una proprietà supportata dalla proprietà di dipendenza per la quale viene impostato il flag <xref:System.Workflow.ComponentModel.DependencyPropertyOptions.Metadata>.  
  
 Le proprietà dei metadati dell'attività di WF 3 sono esposte tramite la raccolta <xref:System.Activities.Statements.Interop.ActivityProperties%2A>. Si tratta di un set di coppie nome-valore, in cui ogni valore è un oggetto <xref:System.Activities.Argument>, usato per definire gli argomenti per le proprietà dell'attività di WF 3. Poiché non è possibile dedurre la direzione di una proprietà dell'attività di WF 3, ogni proprietà viene rilevata come <xref:System.Activities.InArgument>/<xref:System.Activities.OutArgument> coppia. A seconda dell'utilizzo dell'attività della proprietà, è possibile fornire una voce <xref:System.Activities.InArgument>, una voce <xref:System.Activities.OutArgument> o entrambe. Il nome previsto della voce <xref:System.Activities.InArgument> nella raccolta è il nome della proprietà come definito nell'attività di WF 3. Il nome previsto della voce <xref:System.Activities.OutArgument> nella raccolta è una concatenazione del nome della proprietà e della stringa "out".  
  
## <a name="limitations-of-using-a-wf-3-activity-within-an-interop-activity"></a>Limitazioni sull'utilizzo di un'attività di WF 3 all'interno di un'attività di interoperabilità  
 Le attività di WF 3 fornite dal sistema non possono essere sottoposte a wrapping direttamente in un'attività <xref:System.Activities.Statements.Interop>. Per alcune attività di WF 3, ad esempio <xref:System.Workflow.Activities.DelayActivity>, ciò è dovuto alla presenza di un'attività di WF 4.5 analoga. Per altre, è invece dovuto al fatto che la funzionalità dell'attività non è supportata. Molte attività di WF 3 fornite dal sistema possono essere usate all'interno di flussi di lavoro sottoposti a wrapping dall'attività <xref:System.Activities.Statements.Interop>, soggette alle seguenti restrizioni:  
  
1. Gli oggetti <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.Receive> non possono essere usati in un'attività <xref:System.Activities.Statements.Interop>.  
  
2. Gli oggetti <xref:System.Workflow.Activities.WebServiceInputActivity>, <xref:System.Workflow.Activities.WebServiceOutputActivity> e <xref:System.Workflow.Activities.WebServiceFaultActivity> non possono essere usati all'interno di un'attività <xref:System.Activities.Statements.Interop>.  
  
3. L'oggetto <xref:System.Workflow.Activities.InvokeWorkflowActivity> non può essere usato all'interno di un'attività <xref:System.Activities.Statements.Interop>.  
  
4. L'oggetto <xref:System.Workflow.ComponentModel.SuspendActivity> non può essere usato all'interno di un'attività <xref:System.Activities.Statements.Interop>.  
  
5. Le attività correlate alla compensazione non possono essere usate all'interno di un'attività <xref:System.Activities.Statements.Interop>.  
  
 Per quanto riguarda l'uso delle attività di WF 3 all'interno dell'attività <xref:System.Activities.Statements.Interop> è necessario comprendere alcune specifiche di comportamento:  
  
1. Le attività di WF 3 contenute all'interno di un'attività <xref:System.Activities.Statements.Interop> vengono inizializzate quando viene eseguita l'attività <xref:System.Activities.Statements.Interop>. In WF 4.5 non esiste alcuna fase di inizializzazione di un'istanza del flusso di lavoro precedente alla relativa esecuzione.  
  
2. Il runtime di WF 4.5 non esegue il checkpoint dello stato dell'istanza del flusso di lavoro quando inizia una transazione, indipendentemente dal punto in cui inizia quella transazione (all'interno o all'esterno di un'attività <xref:System.Activities.Statements.Interop>).  
  
3. I record di rilevamento WF 3 per attività all'interno di un'attività <xref:System.Activities.Statements.Interop> vengono forniti ai partecipanti del rilevamento WF 4.5 come oggetti <xref:System.Activities.Tracking.InteropTrackingRecord>. <xref:System.Activities.Tracking.InteropTrackingRecord> è un derivato di <xref:System.Activities.Tracking.CustomTrackingRecord>.  
  
4. Un'attività personalizzata di WF 3 può accedere ai dati usando le code del flusso di lavoro all'interno dell'ambiente di interazione, esattamente come avviene all'interno del runtime del flusso di lavoro WF 3. Non è richiesta alcuna modifica al codice di attività personalizzata. Sull'host, i dati vengono accodati a una coda del flusso di lavoro WF 3 riprendendo un oggetto <xref:System.Activities.Bookmark>. Il nome del segnalibro è il formato di stringa del nome della coda del flusso di lavoro <xref:System.IComparable>.

---
title: Modellazione del comportamento di annullamento nei flussi di lavoro
ms.date: 03/30/2017
ms.assetid: d48f6cf3-cdde-4dd3-8265-a665acf32a03
ms.openlocfilehash: 8738afa838f1d0ca36b7fd6def00f0794bcf47ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143044"
---
# <a name="modeling-cancellation-behavior-in-workflows"></a>Modellazione del comportamento di annullamento nei flussi di lavoro
Le attività possono essere annullate all'interno di un flusso di lavoro, ad esempio da un'attività <xref:System.Activities.Statements.Parallel> che annulla i rami incompleti quando la proprietà <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> restituisce `true` oppure all'esterno del flusso di lavoro, se l'host chiama il metodo <xref:System.Activities.WorkflowApplication.Cancel%2A>. Per assicurare la gestione dell'annullamento, gli autori del flusso di lavoro possono usare le attività <xref:System.Activities.Statements.CancellationScope> e <xref:System.Activities.Statements.CompensableActivity> o creare attività personalizzate che forniscono la logica di annullamento. In questo argomento viene fornita una panoramica sull'annullamento nei flussi di lavoro.  
  
## <a name="cancellation-compensation-and-transactions"></a>Annullamento, compensazione e transazioni  
 Le transazioni consentono all'applicazione di interrompere, ovvero eseguire il rollback, tutte le modifiche eseguite all'interno della transazione se si verificano errori durante qualsiasi parte del processo di transazione. Tuttavia, non tutte le operazioni che potrebbero dover essere annullate sono appropriate per le transazioni, ad esempio operazioni con esecuzione prolungata o che non implicano risorse transazionali. La compensazione fornisce un modello per annullare operazioni non transazionali completate precedentemente se, in seguito, si verifica un errore nel flusso di lavoro. L'annullamento fornisce agli autori di flussi di lavoro e attività un modello per gestire le operazioni non transazionali che non sono state completate. Se l'attività viene annullata poiché non ne è stata completata l'esecuzione, sarà richiamata la relativa logica di annullamento, se disponibile.  
  
> [!NOTE]
> Per ulteriori informazioni sulle transazioni e sulla retribuzione, vedere [Transazioni](workflow-transactions.md) e [retribuzione](compensation.md).  
  
## <a name="using-cancellationscope"></a>Utilizzo dell'attività CancellationScope  
 L'attività <xref:System.Activities.Statements.CancellationScope> dispone di due sezioni che possono contenere le attività figlio <xref:System.Activities.Statements.CancellationScope.Body%2A> e <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>. Nella proprietà <xref:System.Activities.Statements.CancellationScope.Body%2A> vengono posizionate le attività che costituiscono la logica dell'attività e nella proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> vengono posizionate le attività che forniscono la logica di annullamento per l'attività. Un'attività può essere annullata solo se non è stata completata. Nel caso dell'attività <xref:System.Activities.Statements.CancellationScope>, con completamento si intende il completamento delle attività nella proprietà <xref:System.Activities.Statements.CancellationScope.Body%2A>. Se viene pianificata una richiesta di annullamento e le attività nella proprietà <xref:System.Activities.Statements.CancellationScope.Body%2A> non sono state completate, l'attività <xref:System.Activities.Statements.CancellationScope> sarà contrassegnata come <xref:System.Activities.ActivityInstanceState.Canceled> e saranno eseguite le attività della proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>.  
  
### <a name="canceling-a-workflow-from-the-host"></a>Annullamento di un flusso di lavoro dall'host  
 Un host può annullare un flusso di lavoro chiamando il metodo <xref:System.Activities.WorkflowApplication.Cancel%2A> dell'istanza <xref:System.Activities.WorkflowApplication> che sta ospitando il flusso di lavoro. Nell'esempio seguente, viene creato un flusso di lavoro che dispone di un'attività <xref:System.Activities.Statements.CancellationScope>. Una volta richiamato il flusso di lavoro, l'host effettua una chiamata al metodo <xref:System.Activities.WorkflowApplication.Cancel%2A>. L'esecuzione principale del flusso di lavoro viene interrotta, viene richiamata la proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> dell'attività <xref:System.Activities.Statements.CancellationScope>, quindi il flusso di lavoro viene completato con lo stato <xref:System.Activities.ActivityInstanceState.Canceled>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#35](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#35)]  
  
 Quando questo flusso di lavoro viene richiamato, nella console viene visualizzato l'output seguente.  
  
 **Avvio del flusso di lavoro.**  
**CancellationHandler richiamato.** 
Flusso di **lavoro b30ebb30-df46-4d90-a211-e31c38d8db3c Annullato.**
> [!NOTE]
> Quando un'attività <xref:System.Activities.Statements.CancellationScope> viene annullata e viene richiamata la proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>, l'autore del flusso di lavoro deve determinare lo stato dell'attività prima del relativo annullamento al fine di fornire la logica di annullamento appropriata. La proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> non fornisce alcuna informazione sullo stato dell'attività annullata.  
  
 Un flusso di lavoro può essere annullato anche dall'host se un'eccezione non gestita viene propagata oltre la radice del flusso di lavoro e il gestore della proprietà <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A> restituisce <xref:System.Activities.UnhandledExceptionAction.Cancel>. In questo esempio, viene avviato il flusso di lavoro che, successivamente, genera un'eccezione <xref:System.ApplicationException>. Questa eccezione non viene gestita dal flusso di lavoro, pertanto viene richiamato il gestore della proprietà <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>. Il gestore indica al runtime di annullare il flusso di lavoro e viene richiamata la proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> dell'attività <xref:System.Activities.Statements.CancellationScope> attualmente in corso di esecuzione.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#36](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#36)]  
  
 Quando questo flusso di lavoro viene richiamato, nella console viene visualizzato l'output seguente.  
  
 **Avvio del flusso di lavoro.**  
**OnUnhandledException nel flusso di lavoro 6bb2d5d6-f49a-4c6d-a988-478afb86dbe9**
**È stata generata un'eccezione ApplicationException.** 
 **CancellationHandler richiamato.** 
Flusso di **lavoro 6bb2d5d6-f49a-4c6d-a988-478afb86dbe9 Annullato.**
### <a name="canceling-an-activity-from-inside-a-workflow"></a>Annullamento di un'attività dall'interno di un flusso di lavoro  
 Un'attività può essere annullata anche dal relativo elemento padre. Ad esempio, se un'attività <xref:System.Activities.Statements.Parallel> dispone di più rami in esecuzione e la relativa proprietà <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> restituisce `true`, i rami incompleti corrispondenti saranno annullati. In questo esempio viene creata un'attività <xref:System.Activities.Statements.Parallel> che dispone di due rami. La relativa proprietà <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> è impostata su `true`, pertanto l'oggetto <xref:System.Activities.Statements.Parallel> viene completato non appena si verifica la stessa condizione per uno dei relativi rami. In questo esempio viene completato il ramo 2, pertanto il ramo 1 viene annullato.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#37](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#37)]  
  
 Quando questo flusso di lavoro viene richiamato, nella console viene visualizzato l'output seguente.  
  
 **Avvio del ramo 1.**  
**Ramo 2 completato.** 
 **Ramo 1 annullato.** 
Flusso di **lavoro e0685e24-18ef-4a47-acf3-5c638732f3be completato.**  Le attività vengono annullate anche se un'eccezione viene propagata oltre la radice dell'attività, ma viene gestita a un livello superiore nel flusso di lavoro. In questo esempio la logica principale del flusso di lavoro è costituita da un'attività <xref:System.Activities.Statements.Sequence>. <xref:System.Activities.Statements.Sequence> è specificato come  <xref:System.Activities.Statements.CancellationScope.Body%2A> di un'attività <xref:System.Activities.Statements.CancellationScope> che è contenuta da un'attività <xref:System.Activities.Statements.TryCatch>. Dal corpo dell'attività <xref:System.Activities.Statements.Sequence> viene generata un'eccezione che viene gestita dall'attività padre <xref:System.Activities.Statements.TryCatch>. L'attività <xref:System.Activities.Statements.Sequence> viene quindi annullata.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#39](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#39)]  
  
 Quando questo flusso di lavoro viene richiamato, nella console viene visualizzato l'output seguente.  
  
 **Avvio dell'attività Sequence.**  
**Sequenza annullata.** 
 **Eccezione rilevata.** 
Flusso di **lavoro e3c18939-121e-4c43-af1c-ba1ce977ce55 Completato.**
### <a name="throwing-exceptions-from-a-cancellationhandler"></a>Generazione di eccezioni da un oggetto CancellationHandler  
 Qualsiasi eccezione generata dalla proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> di un'attività <xref:System.Activities.Statements.CancellationScope> è irreversibile per il flusso di lavoro. Se è possibile che le eccezioni escano da una proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>, usare un oggetto <xref:System.Activities.Statements.TryCatch> nella proprietà <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A> per rilevare e gestire tali eccezioni.  
  
### <a name="cancellation-using-compensableactivity"></a>Annullamento tramite l'oggetto CompensableActivity  
 Analogamente all'attività <xref:System.Activities.Statements.CancellationScope>, l'oggetto <xref:System.Activities.Statements.CompensableActivity> dispone di una proprietà <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>. Se un oggetto <xref:System.Activities.Statements.CompensableActivity> viene annullato, viene richiamata qualsiasi attività nella relativa proprietà <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>. Tale operazione può essere utile per annullare operazioni compensabili completate parzialmente. Per informazioni su <xref:System.Activities.Statements.CompensableActivity> come utilizzare la compensazione e l'annullamento, vedere [Compensazione](compensation.md).  
  
## <a name="cancellation-using-custom-activities"></a>Annullamento tramite attività personalizzate  
 Gli autori di attività personalizzate possono implementare la logica di annullamento nelle proprie attività personalizzate in molti modi diversi. Le attività personalizzate che derivano da <xref:System.Activities.Activity> possono implementare la logica di annullamento inserendo <xref:System.Activities.Statements.CancellationScope> o un'altra attività personalizzata che contiene la logica di annullamento nel corpo dell'attività. Le attività derivate <xref:System.Activities.AsyncCodeActivity> e <xref:System.Activities.NativeActivity> possono eseguire l'override del rispettivo metodo <xref:System.Activities.NativeActivity.Cancel%2A> e fornire qui la logica di annullamento. Le attività derivate <xref:System.Activities.CodeActivity> non forniscono alcuna misura per l'annullamento poiché tutto il lavoro viene eseguito in un unico picco di esecuzione quando il runtime chiama il metodo <xref:System.Activities.CodeActivity.Execute%2A>. Se il metodo Execute non è ancora stato chiamato e viene annullata un'attività basata sull'oggetto <xref:System.Activities.CodeActivity>, l'attività viene chiusa con lo stato <xref:System.Activities.ActivityInstanceState.Canceled> e il metodo <xref:System.Activities.CodeActivity.Execute%2A> non viene chiamato.  
  
### <a name="cancellation-using-nativeactivity"></a>Annullamento tramite l'oggetto NativeActivity  
 Le classi derivate <xref:System.Activities.NativeActivity> possono eseguire l'override del metodo <xref:System.Activities.NativeActivity.Cancel%2A> per fornire la logica di annullamento personalizzata. Se questo metodo non viene sottoposto a override, viene applicata la logica di annullamento del flusso di lavoro predefinita. L'annullamento predefinito è <xref:System.Activities.NativeActivity> il processo che <xref:System.Activities.NativeActivity.Cancel%2A> si <xref:System.Activities.NativeActivity.Cancel%2A> verifica per <xref:System.Activities.NativeActivity> <xref:System.Activities.NativeActivity.Cancel%2A> un oggetto che non esegue l'override del metodo o il cui metodo chiama il metodo di base. Quando un'attività viene annullata, il runtime contrassegna l'attività per l'annullamento e gestisce automaticamente la pulizia. Se l'attività dispone solo di segnalibri in attesa, questi ultimi saranno rimossi e l'attività sarà contrassegnata come <xref:System.Activities.ActivityInstanceState.Canceled>. Qualsiasi attività figlio in attesa dell'attività annullata sarà annullata a sua volta. Qualsiasi tentativo di pianificare attività figlio aggiuntive verrà ignorato e l'attività sarà contrassegnata come <xref:System.Activities.ActivityInstanceState.Canceled>. Se qualsiasi attività figlio in attesa viene completata nello stato <xref:System.Activities.ActivityInstanceState.Canceled> o <xref:System.Activities.ActivityInstanceState.Faulted>, l'attività sarà contrassegnata come <xref:System.Activities.ActivityInstanceState.Canceled>. Si noti che è possibile ignorare una richiesta di annullamento. Se un'attività non dispone di segnalibri in attesa o di attività figlio in esecuzione e non pianifica alcun elemento di lavoro aggiuntivo dopo essere stata contrassegnata per l'annullamento, verrà completata correttamente. Questo annullamento predefinito è sufficiente per molti scenari, tuttavia se è necessaria un'ulteriore logica di annullamento, è possibile usare le attività di annullamento incorporate o le attività personalizzate.  
  
 Nell'esempio seguente, viene definito l'override <xref:System.Activities.NativeActivity.Cancel%2A> di un'attività <xref:System.Activities.NativeActivity> personalizzata basata sull'oggetto `ParallelForEach`. Quando l'attività viene annullata, questo override gestisce la logica di annullamento per l'attività. Questo esempio fa parte dell'esempio [ParallelForEach non generico.](./samples/non-generic-parallelforeach.md)  
  
```csharp  
protected override void Cancel(NativeActivityContext context)  
{  
    // If we do not have a completion condition then we can just  
    // use default logic.  
    if (this.CompletionCondition == null)  
    {  
        base.Cancel(context);  
    }  
    else  
    {  
        context.CancelChildren();  
    }  
}  
```  
  
 Le attività derivate da <xref:System.Activities.NativeActivity> possono determinare se l'annullamento è stato richiesto in seguito al controllo della proprietà <xref:System.Activities.NativeActivityContext.IsCancellationRequested%2A> e possono contrassegnarsi come annullate chiamando il metodo <xref:System.Activities.NativeActivityContext.MarkCanceled%2A>. La chiamata al metodo <xref:System.Activities.NativeActivityContext.MarkCanceled%2A> non completa immediatamente l'attività. Come al solito, il runtime completerà l'attività quando non dispone più di alcuna operazione in attesa, tuttavia se viene chiamato il metodo <xref:System.Activities.NativeActivityContext.MarkCanceled%2A>, lo stato finale sarà <xref:System.Activities.ActivityInstanceState.Canceled> anziché <xref:System.Activities.ActivityInstanceState.Closed>.  
  
### <a name="cancellation-using-asynccodeactivity"></a>Annullamento tramite l'oggetto AsyncCodeActivity  
 Anche le attività basate sull'oggetto <xref:System.Activities.AsyncCodeActivity> possono fornire la logica di annullamento personalizzata eseguendo l'override del metodo <xref:System.Activities.AsyncCodeActivity.Cancel%2A>. Se questo metodo non viene sottoposto a override, non viene eseguita alcuna gestione dell'annullamento se l'attività viene annullata. Nell'esempio seguente, viene definito l'override <xref:System.Activities.AsyncCodeActivity.Cancel%2A> di un'attività <xref:System.Activities.AsyncCodeActivity> personalizzata basata sull'oggetto `ExecutePowerShell`. Quando l'attività viene annullata, esegue il comportamento di annullamento desiderato.
  
 [!code-csharp[CFX_WorkflowApplicationExample#1020](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#1020)]  
  
 Le attività derivate da <xref:System.Activities.AsyncCodeActivity> possono determinare se l'annullamento è stato richiesto in seguito al controllo della proprietà <xref:System.Activities.AsyncCodeActivityContext.IsCancellationRequested%2A> e possono contrassegnarsi come annullate chiamando il metodo <xref:System.Activities.AsyncCodeActivityContext.MarkCanceled%2A>.

---
title: Conferma
ms.date: 03/30/2017
ms.assetid: 8637aeaf-ac9e-49b8-93f4-da15dee45277
ms.openlocfilehash: caa712aa52da01ce44335a361fd6c9f5215316bf
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43419490"
---
# <a name="confirmation"></a>Conferma
In questo esempio vengono illustrati quattro scenari comuni riguardanti l'uso di <xref:System.Activities.Statements.CompensableActivity> e la conferma. L'esempio esegue quattro flussi di lavoro per illustrare la conferma. Questo esempio è disponibile nelle versioni dichiarativa e imperativa.  
  
## <a name="confirm-a-compensable-activity"></a>Confermare una CompensableActivity  
 Il primo flusso di lavoro illustra come confermare un'attività CompensableActivity ed è costituito da una sequenza di due istanze di <xref:System.Activities.Statements.CompensableActivity>. Dopo il completamento della seconda <xref:System.Activities.Statements.CompensableActivity>, un'attività Confirm conferma la prima attività. Quando il flusso di lavoro viene completato correttamente, tutte le istanze di <xref:System.Activities.Statements.CompensableActivity> che non sono state confermate o compensate vengono confermate automaticamente usando l'ordine predefinito. Senza la conferma, la seconda <xref:System.Activities.Statements.CompensableActivity> sarebbe stata confermata per prima.  
  
## <a name="explicit-compensation"></a>Compensazione esplicita  
 Il secondo scenario illustra l'effetto sulla conferma predefinita quando una <xref:System.Activities.Statements.CompensableActivity> viene compensata in modo esplicito. Il flusso di lavoro è costituito da una sequenza di due attività <xref:System.Activities.Statements.CompensableActivity>. Dopo il completamento della seconda, la prima viene compensata in modo esplicito. Di conseguenza, quando il flusso di lavoro viene completato, solo la seconda <xref:System.Activities.Statements.CompensableActivity> viene confermata.  
  
## <a name="controlling-the-order-of-confirmation-for-nested-compensableactivity-activities"></a>Controllo dell'ordine di conferma per le attività CompensableActivity annidate  
 Il terzo scenario illustra come controllare l'ordine di conferma per <xref:System.Activities.Statements.CompensableActivity> annidate. Lo scenario è costituito da una <xref:System.Activities.Statements.CompensableActivity> come radice del flusso di lavoro. Il corpo della <xref:System.Activities.Statements.CompensableActivity> radice è una sequenza di tre <xref:System.Activities.Statements.CompensableActivity>. <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> per la <xref:System.Activities.Statements.CompensableActivity> radice è una sequenza che specifica di confermare la prima, quindi la seconda <xref:System.Activities.Statements.CompensableActivity> annidata. Quando il flusso di lavoro viene completato, conferma la <xref:System.Activities.Statements.CompensableActivity> radice che quindi conferma la prima, la seconda e la terza <xref:System.Activities.Statements.CompensableActivity> annidate, in tale ordine. Di conseguenza, l'ordine di conferma predefinito viene essenzialmente invertito. Poiché la terza <xref:System.Activities.Statements.CompensableActivity> non è stata confermata in modo esplicito come parte della <xref:System.Activities.Statements.CompensableActivity> radice da parte di <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>, viene confermata secondo l'ordine predefinito. Poiché, tuttavia, è la sola <xref:System.Activities.Statements.CompensableActivity> non confermata, ciò significa solo che viene confermata.  
  
## <a name="scoping-of-variables"></a>Ambito di variabili  
 Il quarto scenario illustra come la durata di variabili definite per una <xref:System.Activities.Statements.CompensableActivity> o una delle relative attività padri sia ancora nell'ambito quando vengono eseguiti i gestori compensazione, <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> o <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, anche se l'attività o il flusso di lavoro è stato completato. Il flusso di lavoro è costituito da una sequenza di due <xref:System.Activities.Statements.CompensableActivity>. Nel corpo della prima, la variabile `mySum` viene impostata sulla somma di 5 e 10 e il risultato viene stampato. Nel corpo della seconda <xref:System.Activities.Statements.CompensableActivity> la somma viene impostata sulla somma della somma esistente più 7 e il risultato viene stampato. Viene definito un gestore conferma personalizzato per la prima <xref:System.Activities.Statements.CompensableActivity>, che stampa la somma, sottrae 7 e stampa nuovamente la somma. Controllando le somme stampate risulta chiaro che la variabile è nell'ambito non solo per i corpi di entrambe le <xref:System.Activities.Statements.CompensableActivity>, ma anche per <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Caricare la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Eseguire l'applicazione ConfirmationSample.exe.  
  
3.  Osservare il seguente output:  
  
 **Conferma esplicita: inizio della workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: HandlerEnd conferma di workflowCompensableActivity2: conferma HandlerExplicit compensazione: avvio di workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: HandlerEnd compensazione di workflowCompensableActivity2: conferma HandlerCustom conferma gestore: avvio di workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity3: BodyEnd di workflowCompensableActivity1: conferma HandlerCompensableActivity2: conferma HandlerCompensableActivity3: HandlerVariable conferma l'accesso in un gestore della conferma: Inizio della workflowCompensableActivity1: BodyCompensableActivity1: è la somma: 15CompensableActivity2: BodyCompensableActivity2: aggiunta di 7 per il sumCompensableActivity2: la somma è ora: 22End di workflowCompensableActivity2: conferma HandlerCompensableActivity1: Conferma HandlerCompensableActivity2: la somma è: 22CompensableActivity2: dopo la sottrazione di 12 la somma è ora: 10Press invio per uscire.**  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\Confirmation`
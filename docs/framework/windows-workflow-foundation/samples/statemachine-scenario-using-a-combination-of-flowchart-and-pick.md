---
title: Scenario StateMachine utilizzando una combinazione attività FlowChart e Pick
ms.date: 03/30/2017
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
ms.openlocfilehash: b0f8e884a8a6c62c4e7edaf5cc9727bf7bfe8603
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43558066"
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a>Scenario StateMachine utilizzando una combinazione attività FlowChart e Pick
In questo esempio, viene illustrato come implementare uno scenario StopWatch semplice usando una combinazione di attività <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Pick>. Vengono usate attività Receive e Send all'interno dell'attività Pick per rimanere in ascolto di eventi Stopwatch.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, passare a (pagina di download) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Nella tabella seguente vengono elencati i progetti contenuti in questo esempio.  
  
|Nome progetto|Descrizione|  
|-|-|  
|StopWatchService|Questo progetto contiene l'implementazione di una macchina a stati per l'esempio del cronometro usando una combinazione di attività <xref:System.Activities.Statements.Flowchart> e <xref:System.Activities.Statements.Pick>.<br /><br /> L'attività <xref:System.Activities.Statements.Pick> dispone di 3 istruzioni <xref:System.Activities.Statements.PickBranch> all'interno della proprietà <xref:System.Activities.Statements.Pick.Branches%2A> che rimane in ascolto di eventi `GetStart`, `GetStop` e `GetOff`. In base all'evento in ingresso, si attivano i trigger per uno dei rami e viene attivato l'oggetto <xref:System.Activities.Statements.PickBranch.Action%2A> corrispondente. Nella proprietà <xref:System.Activities.Statements.PickBranch.Action%2A> è presente un'istruzione <xref:System.Activities.Statements.Switch%601> che valuta se la transizione è valida e, tal caso, la proprietà `currentState` viene aggiornata allo stato di transizione e inviata al client.<br /><br /> L'attività <xref:System.Activities.Statements.FlowDecision> alla fine di <xref:System.Activities.Statements.Flowchart> valuta la proprietà `currentState` per determinare se lo stato è finale. In caso affermativo, il flusso di lavoro viene terminato. In caso contrario il controllo esegue il loopback all'inizio dell'attività <xref:System.Activities.Statements.Pick> dove il flusso di lavoro attende più eventi Stopwatch.|  
|StopWatchClient|Si tratta di una semplice applicazione console del flusso di lavoro sequenziale che invia vari eventi Stopwatch con semplici combinazioni di attività Send o Receive.|  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione StateMachineWithPick.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Avviare il StopWatchService.exe dal [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] come amministratore con il pulsante destro facendo clic su file .exe e selezionando **Esegui come amministratore**.  
  
    1.  Passare alla cartella StateMachineWithPick\CS\StopWatchService\bin\Debug.  
  
    2.  Fare doppio clic sul file StopWatchService.exe e selezionare **Esegui come amministratore**.  
  
4.  Avviare l'applicazione client StopWatchClient dall'interno di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    1.  Nelle **Esplora soluzioni**, selezionare la **StopWatchClient** del progetto e fare doppio clic su **imposta come progetto di avvio**.  
  
    2.  Per eseguire la soluzione, premere CTRL+F5.  
  
5.  Tornare alla finestra della console di StopWatchService.exe per visualizzare le transizioni di stato.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`
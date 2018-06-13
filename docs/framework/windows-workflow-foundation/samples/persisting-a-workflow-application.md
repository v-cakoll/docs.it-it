---
title: Persistenza di un'applicazione flusso di lavoro
ms.date: 03/30/2017
ms.assetid: abcff14c-f047-4195-ba26-d27f4a82c24e
ms.openlocfilehash: e5c0cf23dd238c0c5a81519b5e6c415f4ef75f1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519187"
---
# <a name="persisting-a-workflow-application"></a>Persistenza di un'applicazione flusso di lavoro
In questo esempio viene illustrato come eseguire un oggetto <xref:System.Activities.WorkflowApplication>, scaricarlo quando diventa inattivo, quindi ricaricarlo per continuare l'esecuzione.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 <xref:System.Activities.WorkflowApplication> è un host per una singola istanza del flusso di lavoro che fornisce un'interfaccia semplice e abilita alcuni degli scenari di hosting più comuni. Uno scenario di questo tipo è rappresentato da flussi di lavoro a esecuzione prolungata facilitati dalla persistenza. Il controllo host di persistenza viene eseguito chiamando un'operazione di persistenza sull'oggetto <xref:System.Activities.WorkflowApplication> o gestendo un evento <xref:System.Activities.WorkflowApplication> e indicando che l'oggetto <xref:System.Activities.WorkflowApplication> deve essere persistente.  
  
 Il flusso di lavoro di esempio è un'attività <xref:System.Activities.Statements.WriteLine> che richiede il nome dell'utente, un'attività `ReadLine` per ricevere il nome come input tramite la ripresa di un oggetto <xref:System.Activities.Bookmark> e un altro oggetto <xref:System.Activities.Statements.WriteLine> per la ripetizione di un saluto all'utente. Quando un flusso di lavoro è in attesa dell'input, fornisce un punto naturale per la persistenza. Ciò viene spesso definito come punto <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle>. <xref:System.Activities.WorkflowApplication> genera l'evento <xref:System.Workflow.Runtime.Tracking.TrackingWorkflowEvent.Idle> ogni volta che il programma del flusso di lavoro può essere reso persistente, è in attesa della ripresa di un segnalibro e non è in esecuzione alcun altro lavoro. Nel flusso di lavoro di questo esempio, tale punto viene immediatamente dopo l'inizio dell'esecuzione dell'attività `ReadLine`.  
  
 Oggetto <xref:System.Activities.WorkflowApplication> è configurato per eseguire la persistenza con un <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`. In questo esempio viene usato l'oggetto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>. Il <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` devono essere assegnati al <xref:System.Activities.WorkflowApplication.InstanceStore%2A> proprietà prima di <xref:System.Activities.WorkflowApplication> viene eseguito.  
  
 Nell'esempio viene aggiunto un gestore all'evento <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>. Il gestore per questo evento indica l'operazione che l'oggetto <xref:System.Activities.WorkflowApplication> deve effettuare restituendo un oggetto <xref:System.Activities.PersistableIdleAction>. Quando viene restituito il campo <xref:System.Activities.PersistableIdleAction.Unload>, l'oggetto <xref:System.Activities.WorkflowApplication> viene scaricato.  
  
 Nell'esempio viene quindi accettato l'input dall'utente e viene caricato il flusso di lavoro persistente in un nuovo oggetto <xref:System.Activities.WorkflowApplication>. Esegue l'operazione creando un nuovo <xref:System.Activities.WorkflowApplication>, ricrea il <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore`e associare gli eventi completati e scaricati all'istanza e chiamando quindi <xref:System.Activities.WorkflowApplication.Load%2A> con l'identificatore dell'istanza del flusso di lavoro di destinazione. Una volta acquisita l'istanza, viene ripreso il segnalibro dell'attività `ReadLine`. Il flusso di lavoro continua l'esecuzione dall'interno dell'attività `ReadLine` fino al completamento. Quando il flusso di lavoro viene completato e scaricato, il <!--zz <xref:System.Runtime.Persistence.InstanceStore> --> `System.Runtime.Persistence.InstanceStore` viene chiamato un'ultima volta per eliminare il flusso di lavoro.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
     In questo esempio viene richiesto SQL Server Express, installato per impostazione predefinita con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Passare alla directory di esempio (\WF\Basic\Persistence\InstancePersistence\CS) ed eseguire CreateInstanceStore.cmd.  
  
    > [!CAUTION]
    >  Lo script CreateInstanceStore.cmd tenta di creare il database nell'istanza predefinita di SQL Server 2008 Express. Se si desidera installare il database in un'istanza diversa, modificare lo script.  
  
3.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione Persistence.sln e premere CTRL+MAIUSC+B per compilarlo.  
  
    > [!CAUTION]
    >  Se il database è stato installato in un'istanza non predefinita di SQL Server, aggiornare la stringa di connessione nel codice prima di compilare la soluzione.  
  
4.  Eseguire l'esempio con privilegi di amministratore passando alla directory bin del progetto (\WF\Basic\Persistence\InstancePersistence\bin\Debug) in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], destro del mouse su Workflow.exe e scegliendo **Esegui come amministratore**.  
  
#### <a name="to-remove-the-instance-store-database"></a>Per rimuovere il database dell'archivio di istanze  
  
1.  Aprire il prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Passare alla directory di esempio ed eseguire RemoveInstanceStore.cmd.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\InstancePersistence`  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting di AppFabric ed esempi di persistenza](http://go.microsoft.com/fwlink/?LinkId=193961)

---
title: Utilizzo di TransactedReceiveScope
ms.date: 03/30/2017
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
ms.openlocfilehash: bc1c418f3fa116f5e1c1647af3543a38122842f5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481471"
---
# <a name="use-of-transactedreceivescope"></a>Utilizzo di TransactedReceiveScope
In questo esempio viene illustrato come propagare una transazione da un client a un server usando <xref:System.Activities.Statements.TransactionScope> per creare una nuova transazione nel client e un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> per ricevere un messaggio con una transazione propagata, esaminando la durata della transazione nel server. L'esempio è costituito da due progetti che coprono i ruoli di client e server.  
  
## <a name="client-application"></a>Applicazione client  
 L'applicazione client esegue un flusso di lavoro che stampa l'ID della transazione distribuita, invia un messaggio al server, propaga la transazione, riceve la risposta, stampa nuovamente l'ID della transazione distribuita e viene completato. Quando l'ID della transazione distribuita viene stampato inizialmente, è un GUID vuoto poiché la transazione è ancora solo locale.  
  
## <a name="server-application"></a>Applicazione server  
 Il progetto server è simile, tuttavia, il flusso di lavoro viene ospitato in <xref:System.ServiceModel.Activities.WorkflowServiceHost> perché deve essere in attesa di un endpoint del messaggio dal client. Il flusso di lavoro si basa sull'oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> che riceve la transazione propagata dal client, stampa il messaggio che è stato inviato e l'ID della transazione distribuita e infine invia la risposta al client. L'ID della transazione distribuita è ora un GUID non vuoto e se un'attività in grado di riconoscere la transazione è stata aggiunta al corpo dell'oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope>, viene eseguita nella transazione propagata.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Aprire la soluzione TransactedReceiveScope.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Per compilare la soluzione, premere CTRL + MAIUSC + B o scegliere **Compila soluzione** dalle **compilazione** menu.  
  
3.  Una volta completata la compilazione, la soluzione e scegliere **Imposta progetti di avvio**. Nella finestra di dialogo, selezionare **progetti di avvio multipli** e assicurarsi che l'azione per entrambi i progetti sia **avviare**.  
  
4.  Premere F5 o selezionare **Avvia debug** dalle **Debug** menu. In alternativa, è possibile premere CTRL+F5 o selezionare **Avvia senza eseguire debug** dalle **Debug** menu per l'esecuzione senza debug.  
  
    > [!NOTE]
    >  Il server deve essere in esecuzione prima dell'avvio del client. L'output dalla finestra della console che ospita il servizio indica quando è stato avviato.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`
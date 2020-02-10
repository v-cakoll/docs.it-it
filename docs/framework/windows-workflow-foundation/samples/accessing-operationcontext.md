---
title: Accesso a OperationContext
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: 83f3a6cacd3ee86050f65a886d446ab8da7d3690
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094709"
---
# <a name="accessing-operationcontext"></a>Accesso a OperationContext
In questo esempio viene illustrato come è possibile utilizzare le attività di messaggistica (<xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.Send>) con un'attività di ambito personalizzata per accedere <xref:System.ServiceModel.OperationContext.Current%2A> e associare o recuperare un'intestazione di messaggio personalizzata all'interno di un messaggio in uscita o in ingresso.  
  
## <a name="demonstrates"></a>Dimostra  
 Attività di messaggistica, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene illustrato come usare punti di estensibilità (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) nelle attività di messaggistica per accedere a <xref:System.ServiceModel.OperationContext.Current%2A>. I callback vengono registrati all'interno dell'esecuzione del flusso di lavoro come un'implementazione di <xref:System.Activities.IExecutionProperty> raccolta dalle attività della messaggistica durante l'esecuzione. Qualsiasi attività di messaggistica nello stesso ambito di tale implementazione <xref:System.Activities.IExecutionProperty> risulta interessata. In particolare, questo esempio usa un'attività di ambiti personalizzata per applicare il comportamento di callback. <xref:System.ServiceModel.Activities.ISendMessageCallback> viene usato nel flusso di lavoro client per includere l'oggetto <xref:System.Activities.WorkflowApplication.Id%2A> del flusso di lavoro come <xref:System.ServiceModel.Channels.MessageHeader> in uscita. Questa intestazione viene quindi scelta nel servizio usando <xref:System.ServiceModel.Activities.IReceiveMessageCallback> e il valore dell'intestazione viene stampato nella console.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. In questo esempio viene esposto un servizio flusso di lavoro tramite endpoint HTTP. Per eseguire questo esempio, è necessario aggiungere gli ACL URL appropriati (per informazioni dettagliate, vedere [configurazione di http e HTTPS](../../wcf/feature-details/configuring-http-and-https.md) ), eseguendo Visual Studio come amministratore oppure eseguendo il comando seguente in un prompt con privilegi elevati per aggiungere gli ACL appropriati. Assicurarsi che vengono sostituiti il dominio e il nome utente.  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. Una volta aggiunti gli elenchi ACL URL, usare i passaggi seguenti.  
  
    1. Compilare la soluzione.  
  
    2. Impostare più progetti di avvio facendo clic con il pulsante destro del mouse sulla soluzione e selezionando **Imposta progetti di avvio**.  
  
    3. Aggiungere il **servizio** e il **client** (in questo ordine) come più progetti di avvio.  
  
    4. Eseguire l'applicazione. Nella console client viene visualizzato un flusso di lavoro che viene eseguito due volte e nella finestra Servizio è visualizzato l'ID istanza di tali flussi di lavoro.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`

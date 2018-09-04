---
title: OperationScope
ms.date: 03/30/2017
ms.assetid: 56206a21-1e63-422d-b92a-e5d8b713e707
ms.openlocfilehash: 562fd9c8ff964cb997012d49600bce73d4441465
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43554069"
---
# <a name="operationscope"></a>OperationScope
In questo esempio viene illustrato come è possibile usare le attività di messaggistica, <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply> per esporre un'attività personalizzata esistente come operazione in un servizio flusso di lavoro. Questo esempio include una nuova attività personalizzata chiamata `OperationScope`. È destinata a facilitare lo sviluppo di un servizio flusso di lavoro consentendo agli utenti di creare separatamente il corpo delle operazioni come attività personalizzate ed esponendole quindi facilmente come operazioni del servizio tramite l'attività `OperationScope`. Ad esempio, un'attività `Add` personalizzata che accetta due argomenti `in` e restituisce un argomento `out` potrebbe essere esposta come un'operazione `Add` nel servizio flusso di lavoro rilasciandolo in `OperationScope`.  
  
 Il funzionamento dell'ambito si basa sul controllo dell'attività fornita come corpo. Gli eventuali argomenti `in` non associati vengono considerati come input dal messaggio in arrivo. Tutti gli argomenti `out`, indipendentemente che siano associati, sono considerati come output nel messaggio di risposta successivo. Il nome dell'operazione esposto viene rilevato dal nome visualizzato dell'attività `OperationScope`. Come risultato finale viene eseguito il wrapping dell'attività del corpo in un oggetto <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply> con i parametri dei messaggi associati agli argomenti dell'attività.  
  
 In questo esempio viene esposto un servizio flusso di lavoro tramite endpoint HTTP. Per l'esecuzione, è necessario aggiungere ACL di URL appropriati. Per altre informazioni, vedere [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353). Eseguire il comando seguente in un prompt dei comandi con privilegi elevati consente di aggiungere gli ACL appropriati (assicurarsi che il nome utente e dominio vengono sostituiti con dominio %\\% UserName %).  
  
 **netsh http aggiungere url urlacl =http://+:8000/ utente = % % dominio\\% UserName %**  
  
### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Aprire la soluzione OperationScope.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Impostare più progetti di avvio facendo clic sulla soluzione in Esplora soluzioni e selezionando **Imposta progetti di avvio**. Aggiungere Scenario e Scenario_Client (in tale ordine) come più progetti di avvio.  
  
3.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
    > [!WARNING]
    >  Questo passaggio è necessario per visualizzare il flusso di lavoro BankService.xaml a causa dell'attività personalizzata `OperationScope`.  
  
4.  Premere CTRL+F5 per eseguire l'applicazione. La console Scenario_Client richiede l'input e l'output corrispondente viene visualizzato nella console di Scenario.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\OperationScope`
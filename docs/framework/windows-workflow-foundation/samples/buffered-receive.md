---
title: Ricezione memorizzata nel buffer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7a486d3fbfb520ffe3b32c392566e5147c5dfcc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="buffered-receive"></a>Ricezione memorizzata nel buffer
In questo esempio viene illustrato come impostare e configurare la funzionalità di ricezione memorizzata nel buffer in [!INCLUDE[wf](../../../../includes/wf-md.md)]. La ricezione memorizzata nel buffer consente a un autore di creare un flusso di lavoro senza dover preoccuparsi dell'ordine con cui vengono ricevuti i messaggi. La funzionalità di ricezione memorizzata nel buffer memorizza localmente nel buffer i messaggi e li recapita quando il flusso di lavoro è pronto per riceverli.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Elaborazione di messaggi non ordinata tramite la ricezione memorizzata nel buffer con attività di messaggistica.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a>Discussione  
 In questo esempio, un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] viene implementato usando [!INCLUDE[wf1](../../../../includes/wf1-md.md)] e dispone di una sequenza di attività <xref:System.ServiceModel.Activities.Receive>. Questo flusso di lavoro modella un semplice processo di approvazione di un prestito in cui il flusso di lavoro prevede l'approvazione di tre notifiche per un prestito. Un'applicazione client [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] invia tre notifiche correlate nell'ordine inverso rispetto a quello previsto dal servizio. Poiché la funzionalità di ricezione memorizzata nel buffer viene attivata in corrispondenza del servizio, ogni messaggio non ordinato viene memorizzato nel buffer in corrispondenza del servizio ed elaborato quando il flusso di lavoro diventa pronto per riceverlo.  
  
 La funzionalità di ricezione memorizzata nel buffer richiede che l'associazione supporti l'oggetto <xref:System.ServiceModel.Activities.ReceiveContent>, pertanto il servizio usa l'oggetto <xref:System.ServiceModel.NetMsmqBinding>. Non è richiesta alcuna configurazione particolare per l'associazione, pertanto vengono usate le impostazioni predefinite.  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 Il servizio espone inoltre i metadati per il servizio tramite l'oggetto <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
 Analogamente, l'endpoint client viene configurato usando l'oggetto <xref:System.ServiceModel.NetMsmqBinding>. Viene generato il codice client e la configurazione utilizzando il **Aggiungi riferimento al servizio** funzionalità di [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]. L'esempio seguente rappresenta l'endpoint client generato nel file App.config.  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 Per questo esempio è necessario aver abilitato i seguenti componenti di Windows:  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  Compatibilità di gestione, compatibilità metabase e compatibilità configurazione di [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
3.  Servizi World Wide Web, funzionalità di sviluppo di applicazioni e ASP.NET  
  
4.  Microsoft Message Queue (MSMQ) Server  
  
#### <a name="to-set-up-and-build-the-sample"></a>Per impostare e compilare l'esempio  
  
1.  In corrispondenza di un prompt dei comandi di [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], registrare ASP.NET digitando `aspnet_regiis –I` e premere INVIO.  
  
2.  Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] come amministratore.  
  
3.  Aprire LoanService.sln.  
  
4.  Quando viene richiesto se si desidera creare directory virtuali per il progetto LoanService, selezionare **Sì**.  
  
#### <a name="to-set-up-the-service-queues"></a>Per impostare le code del servizio  
  
1.  Premere F5 per eseguire l'applicazione LoanClient che crea le code e attiva il servizio definito in Service1.xamlx.  
  
2.  Aprire il **Gestione Computer** console eseguendo Compmgmt.msc da un prompt dei comandi.  
  
3.  Nel **Gestione Computer** espandere **servizio**, **applicazioni**, **Accodamento**, **code Private** .  
  
4.  La coda loanservice/service1.xamlx di mouse e scegliere **proprietà**.  
  
5.  Selezionare il **sicurezza** scheda e aggiungere **tutti ricevono messaggi**, **Visualizza il messaggio** e **Invia messaggio** autorizzazioni.  
  
6.  Aprire Gestione [!INCLUDE[iis60](../../../../includes/iis60-md.md)].  
  
7.  Passare a **Server**, **siti**, **sito Web predefinito**, **privata**, **LoanService** e selezionare  **Opzioni avanzate**  
  
8.  Modifica il **protocolli abilitati** da **http**, **NET. MSMQ**.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Passare a http://localhost/private/loanservice/service1.xamlx per assicurarsi che il servizio sia in esecuzione.  
  
2.  Premere F5 per eseguire l'applicazione LoanClient. Una volta completato il flusso di lavoro, è necessario salvare un file out.txt nella directory C:\Inbox in cui è contenuto il risultato dello scambio di messaggi.  
  
#### <a name="to-clean-up"></a>Per eseguire la pulizia  
  
1.  Aprire il **Gestione Computer** console eseguendo Compmgmt.msc da un prompt dei comandi.  
  
2.  Espandere **servizio** e **applicazioni**, **Accodamento**, **code Private**.  
  
3.  Eliminare la coda loanservice/service1.xamlx.  
  
4.  Rimuovere la directory C:\Inbox.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`

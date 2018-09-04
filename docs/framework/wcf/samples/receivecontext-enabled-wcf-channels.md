---
title: Canali WCF abilitati per ReceiveContext
ms.date: 03/30/2017
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
ms.openlocfilehash: d7f80d0874606129876fbf7dfa30c0327680b922
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515930"
---
# <a name="receivecontext-enabled-wcf-channels"></a>Canali WCF abilitati per ReceiveContext
In questo esempio viene illustrata l'utilità dei canali WCF abilitati per <xref:System.ServiceModel.Channels.ReceiveContext>. In questo esempio viene implementato un servizio per trovare il prodotto di due numeri usando un canale NetMSMQ.  
  
 La classe <xref:System.ServiceModel.Channels.ReceiveContext> consente a un'applicazione di scegliere se accedere al messaggio o lasciarlo nella coda per l'ulteriore elaborazione, anche dopo il controllo del contenuto del messaggio. In questo esempio un client invia integer casuali a una coda transazionale. Il servizio `ProductCalculator` riceve i messaggi e controlla il contenuto dei messaggi, costituito da integer, per determinare se è possibile calcolare il prodotto. Se l'operazione del servizio non determina il calcolo del prodotto, il messaggio viene inserito di nuovo nella coda e può essere ricevuto nuovamente dal servizio in ascolto sulla coda.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Verificare che Accodamento messaggi Microsoft (MSMQ) sia installato.  
  
    1.  Per installare MSMQ in [!INCLUDE[lserver](../../../../includes/lserver-md.md)]  
  
        1.  Nelle **Server Manager**, fare clic su **funzionalità**.  
  
        2.  Nel riquadro destro sotto **Riepilogo funzionalità**, fare clic su **Aggiungi funzionalità**.  
  
        3.  Nella finestra risulta, espandere **Accodamento messaggi**.  
  
        4.  Espandere **servizi di accodamento dei messaggi**.  
  
        5.  Fare clic su **integrazione servizi Directory** (per i computer aggiunti a un dominio), quindi fare clic su **supporto HTTP**.  
  
        6.  Fare clic su **successivo**, quindi fare clic su **installare**.  
  
    2.  Per installare MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)]  
  
        1.  Aprire il **Pannello di controllo**.  
  
        2.  Fare clic su **i programmi** e quindi selezionare **programmi e funzionalità**, fare clic su **Attiva funzionalità Windows attivare e disattivare**.  
  
        3.  Espandere **Microsoft Message Queue (MSMQ) Server**, espandere **Microsoft Message Queue (MSMQ) Server Core**e quindi selezionare le caselle di controllo per le seguenti funzionalità installare Accodamento messaggi:  
  
            -   Message Queuing Server  
  
            -   Integrazione dei Servizi di dominio Active Directory MSMQ (per i computer aggiunti a un dominio).  
  
            -   Supporto HTTP MSMQ  
  
        4.  Fare clic su **OK**.  
  
        5.  Se viene chiesto di riavviare il computer, fare clic su **OK** per completare l'installazione.  
  
2.  Verificare che [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] sia installato nel computer.  
  
3.  Usare [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] per aprire il file della soluzione ReceiveContextProductGenerator.sln.  
  
4.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
5.  Per eseguire la soluzione, premere CTRL+F5.

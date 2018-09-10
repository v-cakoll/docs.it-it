---
title: Gestione avanzata degli errori
ms.date: 03/30/2017
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
ms.openlocfilehash: 72fb9885408759f5781501b548f81625d258d13c
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084143"
---
# <a name="advanced-error-handling"></a>Gestione avanzata degli errori
Questo esempio viene illustrato il servizio di routing di Windows Communication Foundation (WCF). Il servizio di routing è un componente WCF che rende più semplice includere un router basato sul contenuto nell'applicazione. Nell'esempio viene illustrata la modalità di ripristino intelligente del servizio di routing in caso di errore mediante l'uso di transazioni e altri concetti di messaggistica più complessi, ad esempio il multicasting.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 In questo esempio il servizio di routing è configurato per leggere un messaggio da una coda MSMQ ed eseguirne il multicasting a due elenchi di code. Un elenco viene usato per le code dei servizi e un altro per le code di registrazione.  
  
 Poiché per impostazione predefinita l'associazione MSMQ per il cui uso è configurato il servizio di routing supporta l'uso di transazioni, il servizio di routing verifica che il messaggio sia transazionale e che sia stato ricevuto da almeno una coda in ogni elenco prima della segnalazione alla coda in ingresso (`InQ`) a cui il messaggio è stato indirizzato correttamente. Pertanto, nel caso in cui non siano disponibili entrambe le code dei servizi o entrambe le code di registrazione, il servizio di routing segnalerà l'impossibilità di indirizzare il messaggio e la coda in ingresso dovrà intraprendere un'azione. Questa azione consiste nello spostamento del messaggio alla coda di messaggi non recapitabili di sistema.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  > [!IMPORTANT]
    >  Installare MSMQ prima di eseguire questo esempio. Se MSMQ non è installato, nel momento in cui l'esempio viene eseguito verrà restituito un messaggio di eccezione. Vedere le istruzioni per l'installazione di MSMQ [installazione di Accodamento messaggi (MSMQ)](https://go.microsoft.com/fwlink/?LinkId=166437).  
  
     Aprire AdvancedErrorHandling.sln usando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Premere **F5** oppure **CTRL + MAIUSC + B** in Visual Studio.  
  
    1.  Se l'applicazione viene compilata con CTRL+MAIUSC+B, sarà necessario avviare l'applicazione in ./RoutingService/bin/debug/RoutingService.exe.  
  
3.  Nella finestra della console premere INVIO per avviare il client.  
  
4.  Il client restituirà statistiche diverse relativamente alle code per ogni caso.  
  
    1.  Di seguito è riportato l'output restituito per il caso 1 (nessun errore).  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  Di seguito è riportato l'output restituito per il caso 3 (coda dei servizi primaria e di registrazione con errori).  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  Di seguito è riportato l'output restituito per il caso 4 (coda dei servizi primaria e coda di registrazione primaria e di backup con errori).  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  Di seguito è riportato l'output restituito per il caso 2 (coda dei servizi primaria con errori).  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a>Configurabile tramite codice o App.config  
 L'esempio proposto è configurato per l'uso di un file App.config per la definizione del comportamento del router. È inoltre possibile modificare il nome del file RoutingService\App.config affinché non venga riconosciuto e modificare il valore del campo `configDriven` in RoutingService\Program.cs su `false` per usare la configurazione definita nel codice. Entrambi i metodi restituiscono lo stesso comportamento da parte del router.  
  
### <a name="scenario"></a>Scenario  
 In questo esempio viene illustrato come il servizio di routing sia in grado di gestire funzionalità di messaggistica avanzate, ad esempio transazioni e contesto di ricezione, e possa usare tali funzionalità come parte della gestione corretta di scenari di errore.  
  
### <a name="real-world-scenario"></a>Scenario reale  
 Contoso desidera usare ricezioni transazionali tramite il servizio di routing per garantire che tutti i servizi necessari ricevano le informazioni anche durante le condizioni di errore. Desidera inoltre che gli errori vengano gestiti correttamente e automaticamente e che i problemi vengano segnalati nel caso in cui un messaggio non sia recapitabile anche quando viene usata la logica di gestione degli errori. Per questo scopo, il servizio di routing viene configurato per il failover di endpoint specifici come previsto. Tale servizio gestisce inoltre le situazioni di errore, inclusi la creazione, il completamento, il rollback o l'interruzione di transazioni/contesti di ricezione in base alle necessità.  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting di AppFabric e salvataggio permanente](https://go.microsoft.com/fwlink/?LinkId=193961)

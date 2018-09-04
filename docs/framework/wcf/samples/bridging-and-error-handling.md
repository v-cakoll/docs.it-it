---
title: Bridging e gestione degli errori
ms.date: 03/30/2017
ms.assetid: 4ae87d1a-b615-4014-a494-a53f63ff0137
ms.openlocfilehash: 6afaddc75855b7e95ad708b2179cabb9aee35001
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514542"
---
# <a name="bridging-and-error-handling"></a>Bridging e gestione degli errori
Questo esempio viene illustrato come il servizio di routing di Windows Communication Foundation (WCF) viene usato per il collegamento delle comunicazioni tra un client e un servizio che impiegano associazioni diverse. L'esempio mostra inoltre come utilizzare un servizio di backup per scenari di failover. Il servizio di routing è un componente WCF che rende più semplice includere un router basato sul contenuto nell'applicazione. In questo esempio si adatta l'esempio di calcolatrice standard di WCF per comunicare con il servizio di routing.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\ErrorHandlingAndBridging`  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 In questo esempio, il client calcolatrice è configurato per inviare messaggi a un endpoint esposto dal router. Il servizio di routing è configurato per accettare tutti i messaggi ad esso inviati e per inoltrarli a un endpoint che corrisponde al servizio di calcolatrice. Nei punti seguenti viene descritta la configurazione del servizio di calcolatrice primario, del servizio di calcolatrice di backup e del client calcolatrice. Vengono inoltre fornite informazioni sulla modalità di comunicazione tra client e servizio mediante il servizio di routing:  
  
-   Il client calcolatrice è configurato per utilizzare BasicHttpBinding, mentre il servizio di calcolatrice è configurato per utilizzare NetTcpBinding. Il servizio di routing converte automaticamente i messaggi in modo appropriato prima di inviarli al servizio di calcolatrice e converte anche le risposte in modo che il client calcolatrice sia in grado di accedervi.  
  
-   Il servizio di routing è in grado di riconoscere la presenza di due servizi di calcolatrice: il servizio di calcolatrice primario e il servizio di calcolatrice di backup. Il servizio di routing tenta in primo luogo di comunicare con l'endpoint del servizio di calcolatrice primario. Se il tentativo non riesce a causa dell'inattività dell'endpoint, il servizio di routing tenta di comunicare con l'endpoint del servizio di calcolatrice di backup.  
  
 I messaggi inviati dal client vengono pertanto ricevuti dal router e reindirizzati al servizio di calcolatrice effettivo. Se l'endpoint del servizio di calcolatrice è inattivo, il servizio di routing instrada il messaggio all'endpoint del servizio di calcolatrice di backup. I messaggi provenienti dal servizio di calcolatrice di backup vengono inviati nuovamente al router del servizio, che a sua volta li inoltra al client calcolatrice.  
  
> [!NOTE]
>  In un elenco di backup possono essere definiti più endpoint. In questo caso, se l'endpoint del servizio di backup è inattivo, il servizio di routing tenta di connettersi all'endpoint di backup successivo nell'elenco fino a quando il tentativo di connessione non riesce.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], aprire RouterBridgingAndErrorHandling.sln.  
  
2.  Premere F5 o CTRL+MAIUSC+B in Visual Studio  
  
    1.  Se si desidera avviare automaticamente i progetti necessari quando si preme F5, fare doppio clic la soluzione, selezionare **proprietà**e il **progetto di avvio** nodo sotto **proprietà comuni**, selezionare **progetti di avvio multipli**e impostare tutti i progetti **Start**.  
  
    2.  Se si compila il progetto con CTRL+MAIUSC+B, avviare le applicazioni seguenti:  
  
        1.  Client calcolatrice (./CalculatorClient/bin/client.exe)  
  
        2.  Servizio di calcolatrice (./CalculatorService/bin/service.exe)  
  
        3.  Servizio di routing (./RoutingService/bin/RoutingService.exe)  
  
3.  Nel client calcolatrice, premere INVIO per avviare il client.  
  
     È necessario visualizzare il seguente output:  
  
    ```Output  
    Add(100,15.99) = 115.99  
    Subtract(145,76.54) = 68.46  
    Multiply(9,81.25) = 731.25  
    Divide(22,7) = 3.14285714285714  
    ```  
  
## <a name="configurable-via-code-or-appconfig"></a>Configurabile tramite codice o App.config  
 L'esempio proposto è configurato per l'uso di un file App.config per la definizione del comportamento del router. È inoltre possibile modificare il nome del file App.config affinché non venga riconosciuto e rimuovere i commenti dalla chiamata al metodo in `ConfigureRouterViaCode()`. Entrambi i metodi restituiscono lo stesso comportamento da parte del router.  
  
### <a name="scenario"></a>Scenario  
 L'esempio dimostra il funzionamento del router del servizio come bridge del protocollo e gestore errori. In questo scenario, non si verifica alcun routing basato sul contenuto; il servizio di routing viene utilizzato come nodo proxy trasparente configurato per inoltrare direttamente messaggi a un set preconfigurato di endpoint di destinazione. Il servizio di routing esegue inoltre i passaggi aggiuntivi di gestione trasparente degli errori che si verificano in caso di invio agli endpoint con i quali è prevista la comunicazione in base alla configurazione. Utilizzato come bridge del protocollo, il servizio di routing consente all'utente di definire un protocollo per le comunicazioni esterne e un altro per le comunicazioni interne.  
  
### <a name="real-world-scenario"></a>Scenario reale  
 Contoso desidera fornire un endpoint del servizio interoperativo a livello mondiale, ottimizzando al contempo le prestazioni interne. Propone pertanto i propri servizi a livello internazionale tramite un endpoint utilizzando BasicHttpBinding e ricorrendo internamente al servizio di routing che funge da bridge alla connessione all'endpoint utilizzando NetTcpBinding, impiegato dai propri servizi. Inoltre, poiché Contoso desidera che il servizio offerto tenga conto di possibili periodi di interruzione temporanei in uno dei servizi di produzione, virtualizza più endpoint associati al servizio del router utilizzando le funzionalità di gestione degli errori per il failover automatico nel caso in cui si renda necessario effettuare il backup degli endpoint.  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting di AppFabric e salvataggio permanente](https://go.microsoft.com/fwlink/?LinkId=193961)

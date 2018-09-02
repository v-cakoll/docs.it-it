---
title: Riconfigurazione dinamica
ms.date: 03/30/2017
ms.assetid: b20786ae-cce6-4f91-b6cb-9cae116faf8b
ms.openlocfilehash: a147a1d6cf61001832661376363ecc850ecad309
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43401340"
---
# <a name="dynamic-reconfiguration"></a>Riconfigurazione dinamica
Questo esempio viene illustrato il servizio di routing di Windows Communication Foundation (WCF). Il servizio di routing è un componente WCF che rende più semplice includere un router basato sul contenuto nell'applicazione. In questo esempio si adatta l'esempio di calcolatrice standard di WCF per comunicare con il servizio di routing. In questo esempio viene illustrato come è possibile riconfigurare il servizio di routing dinamicamente durante il runtime.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\DynamicReconfiguration`  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 Per riconfigurare dinamicamente il servizio di routing durante il runtime, questo esempio genera un timer ogni cinque secondi che determina la creazione e l'applicazione di un nuovo oggetto <xref:System.ServiceModel.Routing.RoutingConfiguration>. Questa configurazione fa riferimento al normale endpoint del servizio di calcolo o all'endpoint del servizio di calcolo che esegue l'arrotondamento. L'applicazione client calcolatrice riceve i messaggi da uno dei due servizi, a seconda del servizio di routing configurato per l'indirizzamento in quel momento specifico.  
  
 Vengono utilizzate le funzionalità del servizio di routing per la riconfigurazione dinamica tramite un comportamento personalizzato. In base a tale comportamento personalizzato viene allegata un'estensione del servizio contenente un semplice thread che genera il timer ogni cinque secondi, comportando un callback al metodo `UpdateRules`. Questo callback crea e applica la nuova configurazione del routing. In una distribuzione effettiva questo callback verrebbe probabilmente eseguito in risposta ad altri tipi di evento, ad esempio una notifica di evento SQL o un annuncio di individuazione WS.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire DynamicReconfiguration.sln utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Per aprire **Esplora soluzioni**, selezionare **Esplora soluzioni** dal **visualizzazione** menu.  
  
3.  Premere **F5** oppure **CTRL + MAIUSC + B** in Visual Studio.  
  
    1.  Se si desidera avviare automaticamente i progetti necessari quando si preme **F5**, la soluzione e scegliere **proprietà**. Selezionare il **progetto di avvio** nodo **proprietà comuni** nel riquadro sinistro. Selezionare il **progetti di avvio multipli** pulsante di opzione e impostare tutti i progetti affinché le **avviare** azione.  
  
    2.  Se si compila il progetto con **CTRL + MAIUSC + B**, è necessario avviare le applicazioni seguenti:  
  
        1.  Client calcolatrice (./CalculatorClient/bin/client.exe)  
  
        2.  Servizio di calcolatrice (./CalculatorService/bin/service.exe)  
  
        3.  Servizio di routing relativo alla calcolatrice (./RoundingCalcService/bin/service.exe)  
  
        4.  RoutingService (./RoutingService/bin/RoutingService.exe)  
  
4.  Nella finestra della console del client calcolatrice premere INVIO per avviare il client e per chiamare le operazioni del servizio di calcolatrice.  
  
     Il servizio di routing indirizza i messaggi in modo alternativo e dinamico al servizio di calcolo che esegue l'arrotondamento e al normale servizio di calcolatrice a mano a mano che la configurazione del routing viene modificata dinamicamente ogni cinque secondi. A seconda dell'endpoint configurato per l'invio dei messaggi da parte del servizio routing, nella finestra della console client verranno visualizzati risultati diversi.  
  
5.  Continuare a premere INVIO ripetutamente per più di cinque secondi e osservare le modifiche nei risultati generati dal servizio.  
  
    1.  Di seguito è riportato l'output restituito quando il servizio router è configurato per indirizzare messaggi al servizio di calcolo che esegue l'arrotondamento.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.2  
        Divide(22,7) = 3.1  
        ```  
  
    2.  Di seguito è riportato l'output restituito quando il servizio di routing è configurato per indirizzare messaggi al normale servizio di calcolatrice.  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
6.  Il servizio di calcolatrice e il servizio di calcolo che esegue l'arrotondamento stamperanno inoltre un log delle operazioni richiamate nelle rispettive finestre della console.  
  
7.  Nella finestra della console client, digitare "quit" e premere INVIO per uscire.  
  
8.  Premere INVIO nelle finestre della console dei servizi per terminare i servizi.  
  
## <a name="scenario"></a>Scenario  
 In questo esempio il router agisce come router basato sul contenuto consentendo a più tipi o implementazioni di servizi di essere esposti mediante un endpoint.  
  
### <a name="real-world-scenario"></a>Scenario reale  
 Contoso desidera virtualizzare i propri servizi per esporre pubblicamente solo un endpoint tramite il quale viene offerto l'accesso a più tipi diversi di servizi. In questo caso, le funzionalità di routing basate sul contenuto del servizio di routing vengono utilizzate per determinare dove devono essere inviate le richieste in entrata.  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting di AppFabric e salvataggio permanente](https://go.microsoft.com/fwlink/?LinkId=193961)

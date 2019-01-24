---
title: Hello World con il servizio di routing
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: d560a8e871846f608cc90ec2f4f298c0db710e2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691775"
---
# <a name="hello-world-with-the-routing-service"></a>Hello World con il servizio di routing
Questo esempio viene illustrato il servizio di Routing di Windows Communication Foundation (WCF). Il servizio di Routing è un componente WCF che rende più semplice includere un router basato sul contenuto nell'applicazione. In questo esempio si adatta l'esempio di calcolatrice standard di WCF per comunicare con il servizio di Routing. In questo esempio, il client calcolatrice è configurato per inviare messaggi a un endpoint esposto dal router. Il servizio di routing è configurato per accettare tutti i messaggi ad esso inviati e per inoltrarli a un endpoint che corrisponde al servizio di calcolatrice. I messaggi inviati dal client vengono pertanto ricevuti dal router e reindirizzati al servizio di calcolatrice effettivo. I messaggi provenienti dal servizio di calcolatrice di backup vengono inviati nuovamente al router del servizio, che a sua volta li inoltra al client calcolatrice.

### <a name="to-use-this-sample"></a>Per usare questo esempio

1.  Se si utilizza Visual Studio 2012, aprire Helloroutingservice.

2.  Premere F5 o CTRL+MAIUSC+B.

    > [!NOTE]
    >  Se si preme F5, il client calcolatrice viene avviato automaticamente. Se si preme CTRL+MAIUSC+B (compilazione), è necessario avviare le applicazioni seguenti.
    >
    > 1.  Client calcolatrice (./CalculatorClient/bin/client.exe
    > 2.  Servizio di calcolatrice (./CalculatorService/bin/service.exe)
    > 3.  Servizio di routing (./RoutingService/bin/RoutingService.exe)

3.  Premere INVIO per avviare il client.

     È necessario visualizzare il seguente output:

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a>Configurabile tramite codice o App.Config
 L'esempio proposto è configurato per l'uso di un file App.config per la definizione del comportamento del router. È inoltre possibile modificare il nome del file App.config affinché non venga riconosciuto e rimuovere i commenti dalla chiamata al metodo in ConfigureRouterViaCode(). Entrambi i metodi restituiscono lo stesso comportamento da parte del router.

### <a name="scenario"></a>Scenario
 Questo esempio descrive l'utilizzo del router come message pump di base. Il servizio di routing viene utilizzato come nodo proxy trasparente configurato per inoltrare direttamente messaggi a un set preconfigurato di endpoint di destinazione.

### <a name="real-world-scenario"></a>Scenario reale
 Contoso desidera incrementare la flessibilità relativa a denominazione, indirizzamento, configurazione e sicurezza dei propri servizi. A tale scopo, una message pump di base viene posizionata di fronte ai servizi per essere utilizzata come endpoint rivolto al pubblico. Ciò consente di posizionare sicurezza aggiuntiva davanti ai servizi effettivi e di semplificare l'implementazione di soluzioni di scalabilità o di controllo delle versioni del servizio in una data successiva.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a>Vedere anche
- [Hosting di AppFabric e salvataggio permanente](https://go.microsoft.com/fwlink/?LinkId=193961)

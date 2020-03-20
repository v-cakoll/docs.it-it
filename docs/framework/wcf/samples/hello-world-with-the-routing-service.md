---
title: Hello World con il servizio di routing
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 86a2981e8b861da9d5ccf0a34fe037f3ef419aab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183643"
---
# <a name="hello-world-with-the-routing-service"></a>Hello World con il servizio di routing
In questo esempio viene illustrato il servizio di routing di Windows Communication Foundation (WCF). Il servizio di routing è un componente WCF che semplifica l'inclusione di un router basato sul contenuto nell'applicazione. In questo esempio adatta l'esempio di calcolatrice WCF standard per comunicare utilizzando il servizio di routing. In questo esempio, il client calcolatrice è configurato per inviare messaggi a un endpoint esposto dal router. Il servizio di routing è configurato per accettare tutti i messaggi ad esso inviati e per inoltrarli a un endpoint che corrisponde al servizio di calcolatrice. I messaggi inviati dal client vengono pertanto ricevuti dal router e reindirizzati al servizio di calcolatrice effettivo. I messaggi provenienti dal servizio di calcolatrice di backup vengono inviati nuovamente al router del servizio, che a sua volta li inoltra al client calcolatrice.

### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Utilizzando Visual Studio 2012, aprire HelloRoutingService.sln.

2. Premere F5 o CTRL+MAIUSC+B.

    > [!NOTE]
    > Se si preme F5, il client calcolatrice viene avviato automaticamente. Se si preme CTRL+MAIUSC+B (compilazione), è necessario avviare le applicazioni seguenti.
    >
    > 1. Client calcolatrice (./CalculatorClient/bin/client.exe
    > 2. Servizio di calcolatrice (./CalculatorService/bin/service.exe)
    > 3. Servizio di routing (./RoutingService/bin/RoutingService.exe)

3. Premere INVIO per avviare il client.

     Dovrebbe venire visualizzato l'output seguente.

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
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a>Vedere anche

- [Hosting e salvataggio permanente](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))

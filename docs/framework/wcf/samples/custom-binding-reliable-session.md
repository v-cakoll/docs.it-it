---
title: Sessione affidabile di associazione personalizzata
ms.date: 03/30/2017
ms.assetid: c5fcd409-246f-4f3e-b3f1-629506ca4c04
ms.openlocfilehash: 76c701aaae368171bc7047784e1dc126937c84f0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463931"
---
# <a name="custom-binding-reliable-session"></a>Sessione affidabile di associazione personalizzata

Un'associazione personalizzata viene definita da un elenco ordinato di elementi di associazione discreti. In questo esempio viene illustrato come configurare un'associazione personalizzata con vari elementi di codifica di trasporto e messaggio, in particolare l'abilitazione di sessioni affidabili.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSession`

## <a name="sample-details"></a>Dettagli dell'esempio

Le sessioni affidabili forniscono funzionalità per la messaggistica affidabile e le sessioni. La messaggistica affidabile ritenta la comunicazione in caso di errore e consente di specificare assicurazioni del recapito quali l'arrivo nell'ordine di invio dei messaggi. Le sessioni gestiscono lo stato per i client tra le chiamate. L'esempio implementa le sessioni per mantenere lo stato del client e specifica assicurazioni di recapito nell'ordine. L'esempio è basato sulla [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md) che implementa un servizio di calcolatrice. Le funzionalità di sessioni affidabili vengono abilitate e configurate nei file di configurazione dell'applicazione per il client e il servizio.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

L'ordine degli elementi di associazione è importante nella definizione di un'associazione personalizzata, poiché ognuno rappresenta un livello nello stack di canali (vedere [Associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md)).

La configurazione del servizio per l'esempio è definita come illustrato nell'esempio di codice seguente.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc  -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                     requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous" bypassProxyOnLocal="false"
                        hostNameComparisonMode="StrongWildcard"
                        proxyAuthenticationScheme="Anonymous" realm=""
                        useDefaultWebProxy="true" />
        </binding>
      </customBinding>
    </bindings>

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>

</configuration>
```

Quando si esegue l'esempio tra più computer, è necessario modificare l'indirizzo endpoint del client per riflettere il nome host del servizio.

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Installare ASP.NET 4.0 utilizzando il seguente comando:

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).

4. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).

    > [!IMPORTANT]
    > Quando si esegue il client in una configurazione tra computer, assicurarsi di sostituire "localhost" sia nell'attributo `address` dell'endpoint `clientBaseAddress` [ \<>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento che nell'attributo del>[ \<compositeDuplex](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) con il nome del computer appropriato, come illustrato nell'esempio seguente.

    ```xml
    <endpoint name = ""
    address="http://service_machine_name/servicemodelsamples/service.svc" />
    <compositeDuplex clientBaseAddress="http://client_machine_name:8000/myClient/" />
    ```

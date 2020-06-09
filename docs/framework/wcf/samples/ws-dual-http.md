---
title: HTTP duale WS
ms.date: 03/30/2017
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
ms.openlocfilehash: 4acf2491c242099f6c8b6c9c01dc18e9c99c9934
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589734"
---
# <a name="ws-dual-http"></a>HTTP duale WS

Nell'esempio di HTTP duale viene illustrato come configurare l'associazione `WSDualHttpBinding`. Questo esempio è costituito da un programma di console client (.exe) e da una libreria di servizi (.dll) ospitati da Internet Information Services (IIS). Il servizio implementa un contratto duplex. Il contratto è definito dall'interfaccia `ICalculatorDuplex`, che espone operazioni matematiche (somma, sottrazione, moltiplicazione e divisione). In questo esempio, l'interfaccia `ICalculatorDuplex` consente al client di eseguire operazioni matematiche, calcolando un risultato nella sessione. Il servizio restituisce risultati sull'interfaccia `ICalculatorDuplexCallback` indipendentemente. Poiché occorre definire un contesto per correlare il set di messaggi scambiati fra il client e il servizio, un contratto duplex richiede una sessione. L'associazione `WSDualHttpBinding` supporta la comunicazione duplex.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`

Per configurare un endpoint del servizio con `WSDualHttpBinding`, specificare l'associazione nella configurazione dell'endpoint come illustrato.

```xml
<endpoint address=""
         binding="wsDualHttpBinding"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
```

Nel client, è necessario configurare un indirizzo usabile dal server per la connessione al client, come illustrato nella configurazione di esempio seguente.

```xml
<system.serviceModel>
  <client>
    <endpoint address=
         "http://localhost/servicemodelsamples/service.svc"
         binding="wsDualHttpBinding"
         bindingConfiguration="Binding1"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
  </client>

  <bindings>
    <!-- Configure a WSDualHttpBinding that supports duplex -->
    <!-- communication. -->
    <wsDualHttpBinding>
      <binding name="Binding1"
               clientBaseAddress="http://localhost:8000/myClient/"
               useDefaultWebProxy="true"
               bypassProxyOnLocal="false">
      </binding>
    </wsDualHttpBinding>
  </bindings>
</system.serviceModel>
```

Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Premere INVIO nella finestra del client per arrestare il client.

```console
Press <ENTER> to terminate client once the output is displayed.

Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

Quando si esegue l'esempio, vengono visualizzati i messaggi restituiti al client sull'interfaccia di callback inviata dal servizio. Una volta completate tutte le operazioni, vengono visualizzati tutti i risultati intermedi, seguiti dall'intera equazione. Premere INVIO per arrestare il client.

### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio

1. Installare ASP.NET 4,0 usando il comando seguente.

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

3. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).

4. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).

    > [!IMPORTANT]
    > Quando si esegue il client in una configurazione a più computer, assicurarsi di sostituire localhost sia nell'attributo dell'elemento `address` [ \<endpoint> \<client> dell'](../../configure-apps/file-schema/wcf/endpoint-of-client.md) elemento che nell' `clientBaseAddress` attributo dell'elemento [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) dell' [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) elemento con il nome del computer appropriato, come illustrato:

    ```xml
    <client>
        <endpoint name = ""
          address=
         "http://service_machine_name/servicemodelsamples/service.svc"
        />
    </client>
    ...
    <wsDualHttpBinding>
        <binding name="DuplexBinding" clientBaseAddress=
            "http://client_machine_name:8000/myClient/">
        </binding>
    </wsDualHttpBinding>
    ```

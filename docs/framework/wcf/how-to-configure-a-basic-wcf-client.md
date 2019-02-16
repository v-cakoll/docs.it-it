---
title: 'Procedura: Configurare un Client di base di Windows Communication Foundation'
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 18acec48b2af78877f99335da38ccb0ae8942824
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332319"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>Procedura: Configurare un Client di base di Windows Communication Foundation

Questa è la quinta delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF). Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).

Questo argomento viene illustrato il file di configurazione client generato tramite il **Aggiungi riferimento al servizio** funzionalità di Visual Studio o il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). La configurazione del client è costituita dalla specifica dell'endpoint usato dal client per accedere al servizio. Un endpoint ha un indirizzo, un'associazione e un contratto, e ognuno di questi deve essere specificato nel processo di configurazione del client.

## <a name="configure-a-windows-communication-foundation-client"></a>Configurare un client Windows Communication Foundation

Aprire il file di configurazione generato (App.config) dal progetto GettingStartedClient. L'esempio seguente è una visualizzazione del file di configurazione generato. Sotto il [ \<System. ServiceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sezione, trovare il [ \<endpoint >](../configure-apps/file-schema/wcf/endpoint-element.md) elemento.

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
          <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

In questo esempio viene configurato l'endpoint utilizzato dal client per accedere al servizio che si trova all'indirizzo seguente: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.

L'elemento endpoint specifica che il contratto di servizio `ServiceReference1.ICalculator` viene usato per la comunicazione tra il client e il servizio di WCF. Il canale WCF è configurato con l'oggetto <xref:System.ServiceModel.WSHttpBinding> fornito dal sistema. Il presente contratto è stato generato utilizzando **Aggiungi riferimento al servizio** in Visual Studio. Si tratta essenzialmente di una copia del contratto che è stato definito nel progetto GettingStartedLib. Con l'associazione <xref:System.ServiceModel.WSHttpBinding> vengono specificati HTTP come trasporto, la sicurezza interoperativa e altri dettagli di configurazione.

Per altre informazioni su come usare il client generato con questa configurazione, vedere [come: Usare un Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Procedura: Usare un client WCF](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

## <a name="see-also"></a>Vedere anche

- [Uso di associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Procedura: Creare un Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [Introduzione](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Servizio indipendente](../../../docs/framework/wcf/samples/self-host.md)
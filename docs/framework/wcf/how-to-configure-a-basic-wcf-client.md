---
title: 'Procedura: configurare un client Windows Communication Foundation di base'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: c03bf37c737a19b0a90f12e7ad5db78b75323f5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>Procedura: configurare un client Windows Communication Foundation di base
Questa è la quinta delle sei attività necessarie per creare un'applicazione di Windows Communication Foundation (WCF) di base. Per una panoramica di tutte e sei le attività, vedere il [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md) argomento.  
  
 Questo argomento viene illustrato il file di configurazione di client che è stato generato utilizzando la funzionalità Aggiungi riferimento al servizio del [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] o il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). La configurazione del client è costituita dalla specifica dell'endpoint usato dal client per accedere al servizio. Un endpoint ha un indirizzo, un'associazione e un contratto, e ognuno di questi elementi deve essere specificato nel processo di configurazione del client.  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a>Per configurare un client Windows Communication Foundation  
  
1.  Aprire il file di configurazione generato (App.config) dal progetto GettingStartedClient. L'esempio seguente è una visualizzazione del file di configurazione generato. Sotto il [ \<System. ServiceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sezione, trovare il [ \<endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) elemento.  
  
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
  
     Questo esempio mostra come configurare l'endpoint che il client utilizza per accedere al servizio che si trova all'indirizzo seguente: http://localhost:8000/ServiceModelSamples/Service/CalculatorService  
  
     L'elemento endpoint specifica che il contratto di servizio `ServiceReference1.ICalculator` viene usato per la comunicazione tra il client e il servizio di WCF. Il canale WCF è configurato con fornito dal sistema <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>. Questo contratto è stato generato usando Aggiungi riferimento al servizio in Visual Studio. Si tratta essenzialmente di una copia del contratto che è stato definito nel progetto GettingStartedLib. Il <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> associazione specifica HTTP come trasporto, sicurezza interoperativa e altri dettagli di configurazione.  
  
2.  Per ulteriori informazioni su come usare il client generato con questa configurazione, vedere [procedura: utilizzare un Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di associazioni per configurare servizi e client](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Procedura: Creare un client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Introduzione](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Servizio indipendente](../../../docs/framework/wcf/samples/self-host.md)

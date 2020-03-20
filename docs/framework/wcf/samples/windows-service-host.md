---
title: Host del servizio Windows
ms.date: 03/30/2017
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
ms.openlocfilehash: 83b40f467af933b5da69b859d990fbe4ba005928
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143525"
---
# <a name="windows-service-host"></a>Host del servizio Windows
In questo esempio viene illustrato un servizio Windows Communication Foundation (WCF) ospitato in un servizio Windows gestito. I servizi di Windows sono controllati tramite l'applet Servizi nel **Pannello di controllo** e possono essere configurati per l'avvio automatico dopo un riavvio del sistema. L'esempio è costituito da un programma client e da un programma di Servizio Windows. Il servizio viene implementato come programma con estensione exe e contiene il proprio codice di hosting. In altri ambienti host, quali ad esempio il servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service) o Internet Information Services (IIS), non è necessario scrivere codice di hosting.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 Dopo aver compilato questo servizio, è necessario installarlo con l'utilità Installutil.exe come qualsiasi altro servizio Windows. Se si apportano modifiche al servizio, è prima necessario arrestarlo con `installutil /u`. I file Setup.bat e Cleanup.bat inclusi in questo esempio sono i comandi per installare e avviare il servizio Windows e per arrestarlo e disinstallarlo. Il servizio WCF può rispondere ai client solo se il servizio Windows è in esecuzione. Se si arresta il servizio Windows utilizzando l'applet Servizi <xref:System.ServiceModel.EndpointNotFoundException> dal Pannello di **controllo** ed eseguire il client, si verifica un'eccezione quando un client tenta di accedere al servizio. Se si riavvia il servizio Windows e si esegue di nuovo il client, la comunicazione ha esito positivo.  
  
 Il codice del servizio include una classe di programma di installazione, una classe di implementazione del servizio WCF che implementa il contratto ICalculator e una classe di servizio Windows che funge da host di runtime. La classe Installer, che eredita da <xref:System.Configuration.Install.Installer>, consente di installare il programma come servizio NT mediante lo strumento Installutil.exe. La classe di `WcfCalculatorService`implementazione del servizio , , è un servizio WCF che implementa un contratto di servizio di base. Questo servizio WCF è ospitato all'interno di una classe del servizio Windows denominata `WindowsCalculatorService`. Per essere qualificata come un servizio Windows, la classe eredita da <xref:System.ServiceProcess.ServiceBase> e implementa i metodi <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> e <xref:System.ServiceProcess.ServiceBase.OnStop>. In <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, viene creato un oggetto <xref:System.ServiceModel.ServiceHost> per il tipo `WcfCalculatorService` e viene aperto. In <xref:System.ServiceProcess.ServiceBase.OnStop>, ServiceHost viene chiuso chiamando il metodo <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> dell'oggetto <xref:System.ServiceModel.ServiceHost>. L'indirizzo di base dell'host viene configurato utilizzando l'elemento [ \<add>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) , che è un elemento figlio di [ \<baseAddresses>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), che è un elemento figlio dell'elemento [ \<>host,](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) che è un elemento figlio del [ \<servizio>.](../../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
  
 L'endpoint definito utilizza l'indirizzo di base e un [ \<>wsHttpBinding ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Nell'esempio seguente viene mostrata la configurazione dell'indirizzo di base e l'endpoint che espone CalculatorService.  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.WcfCalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <host>  
      <baseAddresses>  
        <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
      </baseAddresses>  
    </host>  
    <!-- This endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service.  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
```  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nelle finestre della console client e del servizio. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Dopo aver compilato la soluzione, eseguire Setup.bat da un prompt dei comandi di Visual Studio 2012 con privilegi elevati per installare il servizio Windows utilizzando lo strumento Installutil.exe. Il servizio viene visualizzato in Servizi.  
  
4. Per eseguire l'esempio in una configurazione a singolo o tra computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vedere anche

- [Hosting e salvataggio permanente](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))

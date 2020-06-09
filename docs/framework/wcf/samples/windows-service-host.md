---
title: Host del servizio Windows
ms.date: 03/30/2017
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
ms.openlocfilehash: 9c041f6e9505d2ec5865dd512359b497a411cb40
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602284"
---
# <a name="windows-service-host"></a>Host del servizio Windows
In questo esempio viene illustrato un servizio Windows Communication Foundation (WCF) ospitato in un servizio Windows gestito. I servizi Windows sono controllati tramite l'applet servizi nel **Pannello di controllo** e possono essere configurati per l'avvio automatico dopo un riavvio del sistema. L'esempio è costituito da un programma client e da un programma di Servizio Windows. Il servizio viene implementato come programma con estensione exe e contiene il proprio codice di hosting. In altri ambienti host, quali ad esempio il servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service) o Internet Information Services (IIS), non è necessario scrivere codice di hosting.

> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 Dopo aver compilato questo servizio, è necessario installarlo con l'utilità Installutil.exe come qualsiasi altro servizio Windows. Se si apportano modifiche al servizio, è prima necessario arrestarlo con `installutil /u`. I file Setup.bat e Cleanup.bat inclusi in questo esempio sono i comandi per installare e avviare il servizio Windows e per arrestarlo e disinstallarlo. Il servizio WCF può rispondere ai client solo se il servizio Windows è in esecuzione. Se si arresta il servizio Windows utilizzando l'applet servizi del **Pannello di controllo** e si esegue il client, <xref:System.ServiceModel.EndpointNotFoundException> si verifica un'eccezione quando un client tenta di accedere al servizio. Se si riavvia il servizio Windows e si esegue di nuovo il client, la comunicazione ha esito positivo.  
  
 Il codice del servizio include una classe Installer, una classe di implementazione del servizio WCF che implementa il contratto ICalculator e una classe del servizio Windows che funge da host di Runtime. La classe Installer, che eredita da <xref:System.Configuration.Install.Installer>, consente di installare il programma come servizio NT mediante lo strumento Installutil.exe. La classe di implementazione del servizio, `WcfCalculatorService` , è un servizio WCF che implementa un contratto di servizio di base. Questo servizio WCF è ospitato all'interno di una classe del servizio Windows denominata `WindowsCalculatorService` . Per essere qualificata come un servizio Windows, la classe eredita da <xref:System.ServiceProcess.ServiceBase> e implementa i metodi <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> e <xref:System.ServiceProcess.ServiceBase.OnStop>. In <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, viene creato un oggetto <xref:System.ServiceModel.ServiceHost> per il tipo `WcfCalculatorService` e viene aperto. In <xref:System.ServiceProcess.ServiceBase.OnStop>, ServiceHost viene chiuso chiamando il metodo <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> dell'oggetto <xref:System.ServiceModel.ServiceHost>. L'indirizzo di base dell'host viene configurato utilizzando l' [\<add>](../../configure-apps/file-schema/wcf/add-of-baseaddresses.md) elemento, che è figlio di [\<baseAddresses>](../../configure-apps/file-schema/wcf/baseaddresses.md) , che è figlio dell' [\<host>](../../configure-apps/file-schema/wcf/host.md) elemento, che è figlio dell' [\<service>](../../configure-apps/file-schema/wcf/service.md) elemento.  
  
 L'endpoint definito utilizza l'indirizzo di base e un oggetto [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) . Nell'esempio seguente viene mostrata la configurazione dell'indirizzo di base e l'endpoint che espone CalculatorService.  
  
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
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Una volta compilata la soluzione, eseguire Setup. bat da un prompt dei comandi di Visual Studio 2012 con privilegi elevati per installare il servizio Windows mediante lo strumento installutil. exe. Il servizio viene visualizzato in Servizi.  
  
4. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md).  
  
## <a name="see-also"></a>Vedere anche

- [Hosting e salvataggio permanente](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))

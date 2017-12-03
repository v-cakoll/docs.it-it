---
title: Host del servizio Windows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3dd2b4880ea61f5c3236a3e15ba1c939dbc2952
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="windows-service-host"></a>Host del servizio Windows
In questo esempio viene illustrato un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ospitato in un servizio Windows gestito. Servizi di Windows vengono controllati mediante l'applet Servizi nel **Pannello di controllo** e può essere configurato per l'avvio automatico dopo un riavvio del sistema. L'esempio è costituito da un programma client e da un programma di Servizio Windows. Il servizio viene implementato come programma con estensione exe e contiene il proprio codice di hosting. In altri ambienti host, quali ad esempio il servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service) o Internet Information Services (IIS), non è necessario scrivere codice di hosting.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 Dopo aver compilato questo servizio, è necessario installarlo con l'utilità Installutil.exe come qualsiasi altro servizio Windows. Se si apportano modifiche al servizio, è prima necessario arrestarlo con `installutil /u`. I file Setup.bat e Cleanup.bat inclusi in questo esempio sono i comandi per installare e avviare il servizio Windows e per arrestarlo e disinstallarlo. Il servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] può rispondere ai client solo se il servizio Windows è in esecuzione. Se si arresta il servizio Windows tramite l'applet Servizi dal **Pannello di controllo** ed eseguire il client, un <xref:System.ServiceModel.EndpointNotFoundException> eccezione si verifica quando un client tenta di accedere al servizio. Se si riavvia il servizio Windows e si esegue di nuovo il client, la comunicazione ha esito positivo.  
  
 Il codice del servizio include una classe Installer, ovvero una classe di implementazione del servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che implementa il contratto ICalculator, e una classe del servizio Windows che funge da host di runtime. La classe Installer, che eredita da <xref:System.Configuration.Install.Installer>, consente di installare il programma come servizio NT mediante lo strumento Installutil.exe. La classe di implementazione del servizio, `WcfCalculatorService`, è un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che implementa un contratto di servizio di base. Questo servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è ospitato in una classe del servizio Windows denominata `WindowsCalculatorService`. Per essere qualificata come un servizio Windows, la classe eredita da <xref:System.ServiceProcess.ServiceBase> e implementa i metodi <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> e <xref:System.ServiceProcess.ServiceBase.OnStop>. In <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>, viene creato un oggetto <xref:System.ServiceModel.ServiceHost> per il tipo `WcfCalculatorService` e viene aperto. In <xref:System.ServiceProcess.ServiceBase.OnStop>, ServiceHost viene chiuso chiamando il metodo <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> dell'oggetto <xref:System.ServiceModel.ServiceHost>. Indirizzo di base dell'host è configurato utilizzando il [ \<aggiungere >](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) elemento che è un elemento figlio di [ \<baseAddresses >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), che è un figlio del [ \<host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md) elemento che è un elemento figlio del [ \<servizio >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) elemento.  
  
 L'endpoint definito utilizza l'indirizzo di base e un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Nell'esempio seguente viene mostrata la configurazione dell'indirizzo di base e l'endpoint che espone CalculatorService.  
  
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
  
1.  Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Dopo che la soluzione è stata compilata, eseguire Setup.bat da un prompt dei comandi di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegi elevati per installare il servizio Windows con lo strumento Installutil.exe. Il servizio viene visualizzato in Servizi.  
  
4.  Per eseguire l'esempio in una configurazione a una o più computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting di AppFabric ed esempi di persistenza](http://go.microsoft.com/fwlink/?LinkId=193961)

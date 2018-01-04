---
title: Configurazione del servizio di attivazione dei processi di Windows da usare con Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12df9e3760774b4dc8d4e8f73a09df5e79c2453e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a>Configurazione del servizio di attivazione dei processi di Windows da usare con Windows Communication Foundation
In questo argomento vengono illustrati i passaggi richiesti per impostare il servizio di attivazione dei processi di Windows (anche noto come WAS) in [!INCLUDE[wv](../../../../includes/wv-md.md)] per ospitare servizi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] che non comunicano su protocolli di rete HTTP. Nelle sezioni seguenti vengono spiegati i passaggi relativi a tale configurazione:  
  
-   Installare i componenti di attivazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] necessari, o controllarne l'installazione.  
  
-   Creare un sito WAS con le associazioni del protocollo di rete che si desidera utilizzare, o aggiungere una nuova associazione del protocollo a un sito esistente.  
  
-   Creare un'applicazione per ospitare i servizi e consentirle di utilizzare i protocolli di rete necessari.  
  
-   Generare un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che esponga un endpoint non HTTP.  
  
## <a name="configuring-a-site-with-non-http-bindings"></a>Configurazione di un sito con associazioni non HTTP  
 Per utilizzare un'associazione non HTTP con WAS, è necessario aggiungere l'associazione del sito alla configurazione WAS. L'archivio di configurazione per WAS è il file applicationHost.config, situato nella directory %windir%\system32\inetsrv\config. Questo archivio di configurazione è condiviso sia da WAS che da IIS 7.0.  
  
 applicationHost.config è un file di testo XML che può essere aperto con qualsiasi editor di testo standard, ad esempio Blocco note. Lo strumento di configurazione dalla riga di comando [!INCLUDE[iisver](../../../../includes/iisver-md.md)] (appcmd.exe) è tuttavia la modalità preferita per aggiungere associazioni di sito non HTTP.  
  
 Nel comando seguente viene aggiunta un'associazione di sito net.tcp al sito Web predefinito utilizzando appcmd.exe (questo comando viene immesso come riga singola).  
  
```  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 Il comando aggiunge la nuova associazione net.tcp al sito Web predefinito aggiungendo la riga indicata sotto al file applicationHost.config.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
        <bindings>  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            //The following line is added by the command.  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
        </bindings>  
    </site>  
</sites>  
```  
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a>Consentire a un'applicazione di utilizzare protocolli non HTTP  
 È possibile abilitare o disabilitare singoli rete protocolsat il livello di applicazione. Nel comando seguente viene illustrato come attivare entrambi i protocolli HTTP e net.tcp per un'applicazione in esecuzione nel `Default Web Site`.  
  
```  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 L'elenco dei protocolli abilitati possa essere impostata anche nella \<applicationDefaults > dell'elemento di configurazione XML del sito archiviata nel file ApplicationHost. config.  
  
 Nel codice XML seguente da applicationHost.config viene illustrato un sito associato sia a un protocollo HTTP che a uno non HTTP. La configurazione aggiuntiva necessaria per supportare protocolli non HTTP viene chiamata assieme ai commenti.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
    <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
    </application>  
       <bindings>  
            //The following two lines are added by the command.  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
       </bindings>  
    </site>  
    <siteDefaults>  
        <logFile   
        customLogPluginClsid="{FF160663-DE82-11CF-BC0A-00AA006111E0}"  
          directory="D:\inetpub\logs\LogFiles" />  
        <traceFailedRequestsLogging   
          directory="D:\inetpub\logs\FailedReqLogFiles" />  
    </siteDefaults>  
    <applicationDefaults   
      applicationPool="DefaultAppPool"   
      //The following line is inserted by the command.  
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 Se si tenta di attivare un servizio utilizzando WAS per l'attivazione non HTTP e non è stato installato e configurato WAS, è possibile che si verifichi l'errore seguente:  
  
```Output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 Se viene visualizzato questo errore, assicurarsi che WAS per l'attivazione non HTTP sia installato e configurato correttamente. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Procedura: installare e configurare i componenti di attivazione WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a>Compilazione di un servizio WCF che utilizza WAS per l'attivazione non HTTP  
 Dopo aver eseguito i passaggi per installare e configurare WAS (vedere [procedura: installare e configurare componenti di attivazione WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), configurazione di un servizio per l'utilizzo di WAS per l'attivazione è simile alla configurazione di un servizio ospitato in IIS.  
  
 Per istruzioni dettagliate sulla compilazione di attivazione WAS [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] del servizio, vedere [procedura: ospitare un servizio WCF in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Hosting nel servizio di attivazione dei processi di Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)  
 [Windows Server AppFabric con funzionalità di Hosting](http://go.microsoft.com/fwlink/?LinkId=201276)

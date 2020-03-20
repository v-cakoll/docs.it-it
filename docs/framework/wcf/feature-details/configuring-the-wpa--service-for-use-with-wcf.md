---
title: Configurazione del servizio di attivazione dei processi di Windows da usare con Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
ms.openlocfilehash: 2da2653f3d2bd3d998b0ebbe87ea33760315f7df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185296"
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a>Configurazione del servizio di attivazione dei processi di Windows da usare con Windows Communication Foundation
In questo argomento vengono descritti i passaggi necessari per configurare il servizio Attivazione processo Windows (noto anche come WAS) in Windows Vista per ospitare i servizi Windows Communication Foundation (WCF) che non comunicano tramite protocolli di rete HTTP. Nelle sezioni seguenti vengono spiegati i passaggi relativi a tale configurazione:  
  
- Installare (o confermare l'installazione di) i componenti di attivazione WCF necessari.  
  
- Creare un sito WAS con le associazioni del protocollo di rete che si desidera utilizzare, o aggiungere una nuova associazione del protocollo a un sito esistente.  
  
- Creare un'applicazione per ospitare i servizi e consentirle di utilizzare i protocolli di rete necessari.  
  
- Compilare un servizio WCF che espone un endpoint non HTTP.  
  
## <a name="configuring-a-site-with-non-http-bindings"></a>Configurazione di un sito con associazioni non HTTP  
 Per utilizzare un'associazione non HTTP con WAS, è necessario aggiungere l'associazione del sito alla configurazione WAS. L'archivio di configurazione per WAS è il file applicationHost.config, situato nella directory %windir%\system32\inetsrv\config. Questo archivio di configurazione è condiviso sia da WAS che da IIS 7.0.  
  
 applicationHost.config è un file di testo XML che può essere aperto con qualsiasi editor di testo standard, ad esempio Blocco note. Tuttavia, lo strumento di configurazione della riga di comando di IIS 7.0 (appcmd.exe) è il modo preferito per aggiungere associazioni di sito non HTTP.  
  
 Nel comando seguente viene aggiunta un'associazione di sito net.tcp al sito Web predefinito utilizzando appcmd.exe (questo comando viene immesso come riga singola).  
  
```console  
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
 È possibile abilitare o disabilitare singoli protocolli di rete a livello di applicazione. Nel comando seguente viene illustrato come attivare entrambi i protocolli HTTP e net.tcp per un'applicazione in esecuzione nel `Default Web Site`.  
  
```console  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 L'elenco dei protocolli abilitati può \<essere impostato anche nell'elemento applicationDefaults> della configurazione XML del sito archiviato in ApplicationHost.config.  
  
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
  
```output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 Se viene visualizzato questo errore, assicurarsi che WAS per l'attivazione non HTTP sia installato e configurato correttamente. Per ulteriori informazioni, vedere [procedura: installare e configurare i componenti](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)di attivazione WCF .  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a>Compilazione di un servizio WCF che utilizza WAS per l'attivazione non HTTP  
 Una volta eseguita la procedura di installazione e configurazione di WAS (vedere [Procedura: installare e configurare i componenti](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)di attivazione WCF ), la configurazione di un servizio per l'utilizzo di WAS per l'attivazione è simile alla configurazione di un servizio ospitato in IIS.  
  
 Per istruzioni dettagliate sulla creazione di un servizio WCF attivato da WAS, vedere [Procedura: ospitare un servizio WCF in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="see-also"></a>Vedere anche

- [Hosting nel servizio di attivazione dei processi di Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))

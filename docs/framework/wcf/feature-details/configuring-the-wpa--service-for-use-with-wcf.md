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
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a><span data-ttu-id="bb08c-102">Configurazione del servizio di attivazione dei processi di Windows da usare con Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="bb08c-102">Configuring the Windows Process Activation Service for Use with Windows Communication Foundation</span></span>
<span data-ttu-id="bb08c-103">In questo argomento vengono descritti i passaggi necessari per configurare il servizio Attivazione processo Windows (noto anche come WAS) in Windows Vista per ospitare i servizi Windows Communication Foundation (WCF) che non comunicano tramite protocolli di rete HTTP.</span><span class="sxs-lookup"><span data-stu-id="bb08c-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) in Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="bb08c-104">Nelle sezioni seguenti vengono spiegati i passaggi relativi a tale configurazione:</span><span class="sxs-lookup"><span data-stu-id="bb08c-104">The following sections outline the steps for this configuration:</span></span>  
  
- <span data-ttu-id="bb08c-105">Installare (o confermare l'installazione di) i componenti di attivazione WCF necessari.</span><span class="sxs-lookup"><span data-stu-id="bb08c-105">Install (or confirm the installation of) the WCF activation components required.</span></span>  
  
- <span data-ttu-id="bb08c-106">Creare un sito WAS con le associazioni del protocollo di rete che si desidera utilizzare, o aggiungere una nuova associazione del protocollo a un sito esistente.</span><span class="sxs-lookup"><span data-stu-id="bb08c-106">Create a WAS site with the network protocol bindings you wish to use, or add a new protocol binding to an existing site.</span></span>  
  
- <span data-ttu-id="bb08c-107">Creare un'applicazione per ospitare i servizi e consentirle di utilizzare i protocolli di rete necessari.</span><span class="sxs-lookup"><span data-stu-id="bb08c-107">Create an application to host your services and enable that application to use the required network protocols.</span></span>  
  
- <span data-ttu-id="bb08c-108">Compilare un servizio WCF che espone un endpoint non HTTP.</span><span class="sxs-lookup"><span data-stu-id="bb08c-108">Build a WCF service that exposes a non-HTTP endpoint.</span></span>  
  
## <a name="configuring-a-site-with-non-http-bindings"></a><span data-ttu-id="bb08c-109">Configurazione di un sito con associazioni non HTTP</span><span class="sxs-lookup"><span data-stu-id="bb08c-109">Configuring a Site with Non-HTTP bindings</span></span>  
 <span data-ttu-id="bb08c-110">Per utilizzare un'associazione non HTTP con WAS, è necessario aggiungere l'associazione del sito alla configurazione WAS.</span><span class="sxs-lookup"><span data-stu-id="bb08c-110">To use a non-HTTP binding with WAS, the site binding must be added to the WAS configuration.</span></span> <span data-ttu-id="bb08c-111">L'archivio di configurazione per WAS è il file applicationHost.config, situato nella directory %windir%\system32\inetsrv\config.</span><span class="sxs-lookup"><span data-stu-id="bb08c-111">The configuration store for WAS is the applicationHost.config file, located in the %windir%\system32\inetsrv\config directory.</span></span> <span data-ttu-id="bb08c-112">Questo archivio di configurazione è condiviso sia da WAS che da IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="bb08c-112">This configuration store is shared by both WAS and IIS 7.0.</span></span>  
  
 <span data-ttu-id="bb08c-113">applicationHost.config è un file di testo XML che può essere aperto con qualsiasi editor di testo standard, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="bb08c-113">applicationHost.config is an XML text file that can be opened with any standard text editor (such as Notepad).</span></span> <span data-ttu-id="bb08c-114">Tuttavia, lo strumento di configurazione della riga di comando di IIS 7.0 (appcmd.exe) è il modo preferito per aggiungere associazioni di sito non HTTP.</span><span class="sxs-lookup"><span data-stu-id="bb08c-114">However, the IIS 7.0 command-line configuration tool (appcmd.exe) is the preferred way to add non-HTTP site bindings.</span></span>  
  
 <span data-ttu-id="bb08c-115">Nel comando seguente viene aggiunta un'associazione di sito net.tcp al sito Web predefinito utilizzando appcmd.exe (questo comando viene immesso come riga singola).</span><span class="sxs-lookup"><span data-stu-id="bb08c-115">The following command adds a net.tcp site binding to the default Web site using appcmd.exe (this command is entered as a single line).</span></span>  
  
```console  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 <span data-ttu-id="bb08c-116">Il comando aggiunge la nuova associazione net.tcp al sito Web predefinito aggiungendo la riga indicata sotto al file applicationHost.config.</span><span class="sxs-lookup"><span data-stu-id="bb08c-116">This command adds the new net.tcp binding to the default Web site by adding the line indicated below to the applicationHost.config file.</span></span>  
  
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
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a><span data-ttu-id="bb08c-117">Consentire a un'applicazione di utilizzare protocolli non HTTP</span><span class="sxs-lookup"><span data-stu-id="bb08c-117">Enabling an Application to Use Non-HTTP Protocols</span></span>  
 <span data-ttu-id="bb08c-118">È possibile abilitare o disabilitare singoli protocolli di rete a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="bb08c-118">You can enable or disable individual network protocolsat the application level.</span></span> <span data-ttu-id="bb08c-119">Nel comando seguente viene illustrato come attivare entrambi i protocolli HTTP e net.tcp per un'applicazione in esecuzione nel `Default Web Site`.</span><span class="sxs-lookup"><span data-stu-id="bb08c-119">The following command illustrates how to enable both the HTTP and net.tcp protocols for an application that runs in the `Default Web Site`.</span></span>  
  
```console  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 <span data-ttu-id="bb08c-120">L'elenco dei protocolli abilitati può \<essere impostato anche nell'elemento applicationDefaults> della configurazione XML del sito archiviato in ApplicationHost.config.</span><span class="sxs-lookup"><span data-stu-id="bb08c-120">The list of enabled protocols can also be set in the \<applicationDefaults> element of the site’s XML configuration stored in ApplicationHost.config.</span></span>  
  
 <span data-ttu-id="bb08c-121">Nel codice XML seguente da applicationHost.config viene illustrato un sito associato sia a un protocollo HTTP che a uno non HTTP.</span><span class="sxs-lookup"><span data-stu-id="bb08c-121">The following XML code from applicationHost.config illustrates a site bound to both HTTP and non-HTTP protocols.</span></span> <span data-ttu-id="bb08c-122">La configurazione aggiuntiva necessaria per supportare protocolli non HTTP viene chiamata assieme ai commenti.</span><span class="sxs-lookup"><span data-stu-id="bb08c-122">The additional configuration required to support non-HTTP protocols is called out with comments.</span></span>  
  
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
  
 <span data-ttu-id="bb08c-123">Se si tenta di attivare un servizio utilizzando WAS per l'attivazione non HTTP e non è stato installato e configurato WAS, è possibile che si verifichi l'errore seguente:</span><span class="sxs-lookup"><span data-stu-id="bb08c-123">If you attempt to activate a service using WAS for Non-HTTP activation and you have not installed and configured WAS you may see the following error:</span></span>  
  
```output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 <span data-ttu-id="bb08c-124">Se viene visualizzato questo errore, assicurarsi che WAS per l'attivazione non HTTP sia installato e configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="bb08c-124">If you see this error ensure WAS for Non-HTTP Activation is installed and configured properly.</span></span> <span data-ttu-id="bb08c-125">Per ulteriori informazioni, vedere [procedura: installare e configurare i componenti](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)di attivazione WCF .</span><span class="sxs-lookup"><span data-stu-id="bb08c-125">For more information, see [How to: Install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).</span></span>  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a><span data-ttu-id="bb08c-126">Compilazione di un servizio WCF che utilizza WAS per l'attivazione non HTTP</span><span class="sxs-lookup"><span data-stu-id="bb08c-126">Building a WCF Service That Uses WAS for Non-HTTP activation</span></span>  
 <span data-ttu-id="bb08c-127">Una volta eseguita la procedura di installazione e configurazione di WAS (vedere [Procedura: installare e configurare i componenti](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)di attivazione WCF ), la configurazione di un servizio per l'utilizzo di WAS per l'attivazione è simile alla configurazione di un servizio ospitato in IIS.</span><span class="sxs-lookup"><span data-stu-id="bb08c-127">Once you perform the steps to install and configure WAS (see [How to: Install and Configure WCF Activation Components](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), configuring a service to use WAS for activation is similar to configuring a service that is hosted in IIS.</span></span>  
  
 <span data-ttu-id="bb08c-128">Per istruzioni dettagliate sulla creazione di un servizio WCF attivato da WAS, vedere [Procedura: ospitare un servizio WCF in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).</span><span class="sxs-lookup"><span data-stu-id="bb08c-128">For detailed instructions about building a WAS-activated WCF service, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb08c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb08c-129">See also</span></span>

- [<span data-ttu-id="bb08c-130">Hosting nel servizio di attivazione dei processi di Windows</span><span class="sxs-lookup"><span data-stu-id="bb08c-130">Hosting in Windows Process Activation Service</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)
- <span data-ttu-id="bb08c-131">[Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="bb08c-131">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>

---
title: Servizio AJAX senza configurazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13f74a69e05c419cc76cc8df8f58d3e3385ab35f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="dda2b-102">Servizio AJAX senza configurazione</span><span class="sxs-lookup"><span data-stu-id="dda2b-102">AJAX Service Without Configuration</span></span>
<span data-ttu-id="dda2b-103">Questo esempio illustra come usare [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] per creare un servizio AJAX (ASP.NET Asynchronous JavaScript and XML) di base, ovvero un servizio al quale è possibile accedere usando codice JavaScript da un client browser Web senza usare alcuna impostazione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="dda2b-103">This sample demonstrates how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="dda2b-104">Il servizio usa sintassi speciale nel file con estensione svc per abilitare automaticamente un endpoint AJAX.</span><span class="sxs-lookup"><span data-stu-id="dda2b-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>  
  
 <span data-ttu-id="dda2b-105">Il supporto AJAX in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] è ottimizzato per l'uso con ASP.NET AJAX tramite il controllo `ScriptManager`.</span><span class="sxs-lookup"><span data-stu-id="dda2b-105">AJAX support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="dda2b-106">Per un esempio di utilizzo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con ASP.NET AJAX, vedere il [esempi Ajax](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="dda2b-106">For an example of using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see the [Ajax Samples](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dda2b-107">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="dda2b-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="dda2b-108">Nell'esempio viene usato il servizio AJAX con il protocollo HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="dda2b-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="dda2b-109">Come descritto nel [servizio AJAX di base](../../../../docs/framework/wcf/samples/basic-ajax-service.md) esempio <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> viene utilizzato per ospitare il servizio.</span><span class="sxs-lookup"><span data-stu-id="dda2b-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>  
  
```  
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```  
  
 <span data-ttu-id="dda2b-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> aggiunge automaticamente un elemento <xref:System.ServiceModel.Description.WebScriptEndpoint> al servizio.</span><span class="sxs-lookup"><span data-stu-id="dda2b-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="dda2b-111">Se è necessario apportare all'endpoint, senza modifiche alla configurazione di \<sistema. ServiceModel > sezione può essere rimossa completamente dal file Web. config per il servizio.</span><span class="sxs-lookup"><span data-stu-id="dda2b-111">If no configuration changes need to be made to the endpoint, the \<system.ServiceModel> section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="dda2b-112">Il file Web.config contiene alcune impostazioni di ASP.NET che vengono usate da ConfigFreeClientPage.aspx.</span><span class="sxs-lookup"><span data-stu-id="dda2b-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="dda2b-113">Se la situazione è diversa, il file Web.config potrebbe essere totalmente rimosso.</span><span class="sxs-lookup"><span data-stu-id="dda2b-113">If that were not the case, the entire Web.config file could be removed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dda2b-114">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="dda2b-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dda2b-115">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="dda2b-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dda2b-116">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dda2b-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dda2b-117">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="dda2b-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dda2b-118">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="dda2b-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dda2b-119">Assicurarsi di eseguire le istruzioni di installazione in [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dda2b-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="dda2b-120">Compilare la soluzione ConfigFreeAjaxService.sln, come descritto in [compilazione degli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dda2b-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="dda2b-121">Spostarsi alla pagina http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (non aprire ConfigFreeClientPage.aspx nel browser all'interno della directory del progetto).</span><span class="sxs-lookup"><span data-stu-id="dda2b-121">Navigate to http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dda2b-122">Quando si esegue questo esempio, assicurarsi che Autenticazione anonima e Autenticazione Windows non siano abilitate simultaneamente per la cartella ServiceModelSamples in IIS.</span><span class="sxs-lookup"><span data-stu-id="dda2b-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="dda2b-123">Se così dovesse essere, disabilitare l'autenticazione Windows.</span><span class="sxs-lookup"><span data-stu-id="dda2b-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="dda2b-124">Dopo aver eseguito l'esempio, abilitare l'autenticazione Windows ed eseguire "iisreset".</span><span class="sxs-lookup"><span data-stu-id="dda2b-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dda2b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dda2b-125">See Also</span></span>  
 [<span data-ttu-id="dda2b-126">Servizio AJAX di base</span><span class="sxs-lookup"><span data-stu-id="dda2b-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)

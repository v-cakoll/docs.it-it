---
title: "Esempio Individuare un servizio con modalità Uri di ascolto univoco"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a6d35b2-0469-43c8-a0c9-63623e3d2733
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82f47fb0b789e41c332ebae2cfeaeb350ff0fddd
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="discover-a-service-with-unique-listen-uri-mode-sample"></a><span data-ttu-id="e392b-102">Esempio Individuare un servizio con modalità Uri di ascolto univoco</span><span class="sxs-lookup"><span data-stu-id="e392b-102">Discover a Service with Unique Listen Uri Mode Sample</span></span>
<span data-ttu-id="e392b-103">In questo esempio viene illustrato come individuare un servizio che dispone della proprietà <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> impostata su <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span><span class="sxs-lookup"><span data-stu-id="e392b-103">This sample demonstrates how to discover a service that has the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>.</span></span> <span data-ttu-id="e392b-104">L'impostazione della proprietà <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> su <xref:System.ServiceModel.Description.ListenUriMode.Unique> garantisce l'univocità di ListenUri attraverso l'impostazione della porta che deve essere univoca o del percorso che deve essere univoco mediante l'aggiunta di un GUID.</span><span class="sxs-lookup"><span data-stu-id="e392b-104">When the <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique>, the ListenUri is ensured to be unique by either setting the port to be unique or for the path to be unique by appending a GUID.</span></span>  
  
### <a name="features-on-the-service"></a><span data-ttu-id="e392b-105">Funzionalità nel servizio</span><span class="sxs-lookup"><span data-stu-id="e392b-105">Features on the Service</span></span>  
 <span data-ttu-id="e392b-106">La proprietà <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> viene impostata su <xref:System.ServiceModel.Description.ListenUriMode.Unique> per l'endpoint TCP.</span><span class="sxs-lookup"><span data-stu-id="e392b-106">The <xref:System.ServiceModel.Channels.BindingContext.ListenUriMode%2A> property is set to <xref:System.ServiceModel.Description.ListenUriMode.Unique> for the TCP endpoint.</span></span> <span data-ttu-id="e392b-107">Il servizio viene quindi reso individuabile su un endpoint <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="e392b-107">The service is then made discoverable over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> endpoint.</span></span>  
  
### <a name="features-on-the-client"></a><span data-ttu-id="e392b-108">Funzionalità nel client</span><span class="sxs-lookup"><span data-stu-id="e392b-108">Features on the Client</span></span>  
 <span data-ttu-id="e392b-109">Questo client si connette al servizio utilizzando il `Via.Uri` corretto tramite il metodo <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>.</span><span class="sxs-lookup"><span data-stu-id="e392b-109">This client connects to the service using the correct `Via.Uri` by using the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method.</span></span> <span data-ttu-id="e392b-110">Sull'oggetto <xref:System.ServiceModel.Discovery.FindResponse> restituito dal metodo viene quindi eseguita una query per determinare se contiene una proprietà <xref:System.ServiceModel.Endpoint.ListenUri%2A> valida e se è diverso da `Address.Uri`.</span><span class="sxs-lookup"><span data-stu-id="e392b-110">The <xref:System.ServiceModel.Discovery.FindResponse> that is returned from the method is then queried for whether it contains a valid <xref:System.ServiceModel.Endpoint.ListenUri%2A> and whether it is different than `Address.Uri`.</span></span> <span data-ttu-id="e392b-111">Le informazioni appropriate vengono quindi passate al metodo `InvokeCalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="e392b-111">The appropriate information is then passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="e392b-112">Nel metodo `InvokeCalculatorService` la proprietà <xref:System.ServiceModel.Endpoint.ListenUri%2A> viene passata dal chiamante, quindi un oggetto `ClientViaBehavior` con il `Via.Uri` corretto viene aggiunto all'endpoint del client.</span><span class="sxs-lookup"><span data-stu-id="e392b-112">In the `InvokeCalculatorService` method, the <xref:System.ServiceModel.Endpoint.ListenUri%2A> was passed in by the caller, then a `ClientViaBehavior` with the correct `Via.Uri` is added to the client’s endpoint.</span></span>  
  
##### <a name="to-use-this-sample"></a><span data-ttu-id="e392b-113">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="e392b-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="e392b-114">Aprire UniqueListenUriMode.sln utilizzando [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e392b-114">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open UniqueListenUriMode.sln.</span></span>  
  
2.  <span data-ttu-id="e392b-115">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="e392b-115">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="e392b-116">Eseguire l'applicazione del servizio, generata nella cartella [directory soluzione di base]\service\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="e392b-116">Run the service application, which is generated in the [solution base directory]\service\bin\debug folder.</span></span>  
  
4.  <span data-ttu-id="e392b-117">Eseguire l'applicazione client, generata nella cartella [directory soluzione di base]\Client\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="e392b-117">Run the client application, which is generated in the [solution base directory]\Client\bin\debug folder.</span></span>  
  
     <span data-ttu-id="e392b-118">Il client individua il servizio in esecuzione e scrive nella console i metadati pubblicati dall'endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="e392b-118">The client locates the running service and writes to the console the metadata published by the service’s endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e392b-119">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="e392b-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e392b-120">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="e392b-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e392b-121">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e392b-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e392b-122">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="e392b-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\UniqueListenUriMode`  
  
## <a name="see-also"></a><span data-ttu-id="e392b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e392b-123">See Also</span></span>

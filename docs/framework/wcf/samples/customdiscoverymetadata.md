---
title: CustomDiscoveryMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2e13fde338075d9ef16c205efcfcb452235f0af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="customdiscoverymetadata"></a><span data-ttu-id="58da7-102">CustomDiscoveryMetadata</span><span class="sxs-lookup"><span data-stu-id="58da7-102">CustomDiscoveryMetadata</span></span>
<span data-ttu-id="58da7-103">In questo esempio viene illustrato come inserire metadati XML personalizzati nei metadati di individuazione per un endpoint individuabile esposto da un servizio.</span><span class="sxs-lookup"><span data-stu-id="58da7-103">This sample shows how to insert custom XML metadata into the discovery metadata for a discoverable endpoint exposed by a service.</span></span> <span data-ttu-id="58da7-104">Nell'esempio viene quindi illustrato come un client può eseguire la ricerca del servizio ed estrarre questi dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="58da7-104">The sample then shows how a client can search for the service and extract this custom data.</span></span> <span data-ttu-id="58da7-105">Questo esempio è costituito da due progetti, ovvero il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="58da7-105">This sample consists of two projects, service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="58da7-106">Servizio</span><span class="sxs-lookup"><span data-stu-id="58da7-106">Service</span></span>  
 <span data-ttu-id="58da7-107">Nel metodo `main` dell'esempio un oggetto di tipo <xref:System.Xml.Linq.XElement> viene popolato con i campi desiderati e aggiunto a <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="58da7-107">In the `main` method, the sample shows that an object of type <xref:System.Xml.Linq.XElement> is populated with the desired fields and is added to the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span></span> <span data-ttu-id="58da7-108">Questo <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> viene aggiunto a un particolare endpoint.</span><span class="sxs-lookup"><span data-stu-id="58da7-108">This <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> is added to a particular endpoint.</span></span> <span data-ttu-id="58da7-109">Nel momento in cui viene individuato quel particolare endpoint, i metadati di individuazione contengono i dati personalizzati aggiunti.</span><span class="sxs-lookup"><span data-stu-id="58da7-109">When that particular endpoint is discovered, the discovery metadata contains the custom data that was added here.</span></span>  
  
## <a name="client"></a><span data-ttu-id="58da7-110">Client</span><span class="sxs-lookup"><span data-stu-id="58da7-110">Client</span></span>  
 <span data-ttu-id="58da7-111">Nell'esempio viene illustrato il metodo <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> chiamato su un oggetto <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span><span class="sxs-lookup"><span data-stu-id="58da7-111">The sample shows the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method being called on a <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span></span> <span data-ttu-id="58da7-112">Sull'oggetto <xref:System.ServiceModel.Discovery.FindResponse> risultante viene eseguita una query per individuare gli elementi XML appropriati e previsti.</span><span class="sxs-lookup"><span data-stu-id="58da7-112">The resulting <xref:System.ServiceModel.Discovery.FindResponse> is then queried for the appropriate and expected XML elements.</span></span> <span data-ttu-id="58da7-113">Questi elementi vengono quindi stampati sulla console.</span><span class="sxs-lookup"><span data-stu-id="58da7-113">These elements are then printed to the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="58da7-114">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="58da7-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="58da7-115">Caricare la soluzione del progetto in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] e compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="58da7-115">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="58da7-116">Eseguire innanzitutto l'applicazione del servizio, generata in [directory soluzione di base]\service\bin\debug, quindi eseguire l'applicazione client, generata in [directory soluzione di base]\Client\bin\debug</span><span class="sxs-lookup"><span data-stu-id="58da7-116">First run the Service application, generated in [solution base directory]\service\bin\debug, and then run the Client application, generated in [solution base directory]\Client\bin\debug</span></span>  
  
3.  <span data-ttu-id="58da7-117">Si noti che il servizio viene portato online, il client individua il servizio e stampa i metadati pubblicati nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="58da7-117">Note that the service comes online, the client locates the service and prints the metadata published in the endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58da7-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="58da7-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="58da7-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="58da7-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="58da7-120">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58da7-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="58da7-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="58da7-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a><span data-ttu-id="58da7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58da7-122">See Also</span></span>

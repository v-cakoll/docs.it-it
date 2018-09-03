---
title: CustomDiscoveryMetadata
ms.date: 03/30/2017
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
ms.openlocfilehash: 181910db3f1dd6da892f6ae2ddcbf7bd5859ff17
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43465577"
---
# <a name="customdiscoverymetadata"></a><span data-ttu-id="b31fe-102">CustomDiscoveryMetadata</span><span class="sxs-lookup"><span data-stu-id="b31fe-102">CustomDiscoveryMetadata</span></span>
<span data-ttu-id="b31fe-103">In questo esempio viene illustrato come inserire metadati XML personalizzati nei metadati di individuazione per un endpoint individuabile esposto da un servizio.</span><span class="sxs-lookup"><span data-stu-id="b31fe-103">This sample shows how to insert custom XML metadata into the discovery metadata for a discoverable endpoint exposed by a service.</span></span> <span data-ttu-id="b31fe-104">Nell'esempio viene quindi illustrato come un client può eseguire la ricerca del servizio ed estrarre questi dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b31fe-104">The sample then shows how a client can search for the service and extract this custom data.</span></span> <span data-ttu-id="b31fe-105">Questo esempio è costituito da due progetti, ovvero il servizio e il client.</span><span class="sxs-lookup"><span data-stu-id="b31fe-105">This sample consists of two projects, service and client.</span></span>  
  
## <a name="service"></a><span data-ttu-id="b31fe-106">Servizio</span><span class="sxs-lookup"><span data-stu-id="b31fe-106">Service</span></span>  
 <span data-ttu-id="b31fe-107">Nel metodo `main` dell'esempio un oggetto di tipo <xref:System.Xml.Linq.XElement> viene popolato con i campi desiderati e aggiunto a <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="b31fe-107">In the `main` method, the sample shows that an object of type <xref:System.Xml.Linq.XElement> is populated with the desired fields and is added to the <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>.</span></span> <span data-ttu-id="b31fe-108">Questo <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> viene aggiunto a un particolare endpoint.</span><span class="sxs-lookup"><span data-stu-id="b31fe-108">This <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> is added to a particular endpoint.</span></span> <span data-ttu-id="b31fe-109">Nel momento in cui viene individuato quel particolare endpoint, i metadati di individuazione contengono i dati personalizzati aggiunti.</span><span class="sxs-lookup"><span data-stu-id="b31fe-109">When that particular endpoint is discovered, the discovery metadata contains the custom data that was added here.</span></span>  
  
## <a name="client"></a><span data-ttu-id="b31fe-110">Client</span><span class="sxs-lookup"><span data-stu-id="b31fe-110">Client</span></span>  
 <span data-ttu-id="b31fe-111">Nell'esempio viene illustrato il metodo <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> chiamato su un oggetto <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span><span class="sxs-lookup"><span data-stu-id="b31fe-111">The sample shows the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method being called on a <xref:System.ServiceModel.Discovery.DiscoveryClient>.</span></span> <span data-ttu-id="b31fe-112">Sull'oggetto <xref:System.ServiceModel.Discovery.FindResponse> risultante viene eseguita una query per individuare gli elementi XML appropriati e previsti.</span><span class="sxs-lookup"><span data-stu-id="b31fe-112">The resulting <xref:System.ServiceModel.Discovery.FindResponse> is then queried for the appropriate and expected XML elements.</span></span> <span data-ttu-id="b31fe-113">Questi elementi vengono quindi stampati sulla console.</span><span class="sxs-lookup"><span data-stu-id="b31fe-113">These elements are then printed to the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b31fe-114">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="b31fe-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="b31fe-115">Caricare la soluzione del progetto in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] e compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="b31fe-115">Load the project solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="b31fe-116">Eseguire innanzitutto l'applicazione del servizio, generata in [directory soluzione di base]\service\bin\debug, quindi eseguire l'applicazione client, generata in [directory soluzione di base]\Client\bin\debug</span><span class="sxs-lookup"><span data-stu-id="b31fe-116">First run the Service application, generated in [solution base directory]\service\bin\debug, and then run the Client application, generated in [solution base directory]\Client\bin\debug</span></span>  
  
3.  <span data-ttu-id="b31fe-117">Si noti che il servizio viene portato online, il client individua il servizio e stampa i metadati pubblicati nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="b31fe-117">Note that the service comes online, the client locates the service and prints the metadata published in the endpoint.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b31fe-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b31fe-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b31fe-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b31fe-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b31fe-120">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b31fe-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b31fe-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b31fe-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a><span data-ttu-id="b31fe-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b31fe-122">See Also</span></span>

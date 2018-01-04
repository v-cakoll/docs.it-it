---
title: Servizio router di individuazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ec96a4c318b7f9994f04bf2e4dfc6209cadda29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="discovery-router-service"></a><span data-ttu-id="2311b-102">Servizio router di individuazione</span><span class="sxs-lookup"><span data-stu-id="2311b-102">Discovery Router Service</span></span>
<span data-ttu-id="2311b-103">In questo esempio viene descritto come inoltrare messaggi di individuazione a un altro endpoint.</span><span class="sxs-lookup"><span data-stu-id="2311b-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2311b-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="2311b-104">Demonstrates</span></span>  
 <span data-ttu-id="2311b-105">Routing di individuazione</span><span class="sxs-lookup"><span data-stu-id="2311b-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2311b-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="2311b-106">Discussion</span></span>  
 <span data-ttu-id="2311b-107">Il routing di individuazione è utile in uno scenario nel quale un client effettua la ricerca di un servizio utilizzando un proxy e il proxy non riconosce tale servizio, ma riconosce un altro proxy.</span><span class="sxs-lookup"><span data-stu-id="2311b-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="2311b-108">Questo proxy può inoltrare il pacchetto di individuazione dal client al secondo proxy.</span><span class="sxs-lookup"><span data-stu-id="2311b-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="2311b-109">Il secondo proxy può ricercare il servizio e restituire le risposte al client originale.</span><span class="sxs-lookup"><span data-stu-id="2311b-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="2311b-110">In questo esempio, un client invia un messaggio a un componente del routing di individuazione.</span><span class="sxs-lookup"><span data-stu-id="2311b-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="2311b-111">Il messaggio viene inviato a un endpoint specifico nel router di individuazione.</span><span class="sxs-lookup"><span data-stu-id="2311b-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="2311b-112">Il router inoltra quindi il messaggio a un endpoint multicast UDP.</span><span class="sxs-lookup"><span data-stu-id="2311b-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="2311b-113">Il messaggio del probe raggiunge l'endpoint multicast e un servizio in ascolto su un indirizzo multicast UDP risponde al router di individuazione.</span><span class="sxs-lookup"><span data-stu-id="2311b-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="2311b-114">Il router di individuazione raccoglie le risposte e le restituisce al client.</span><span class="sxs-lookup"><span data-stu-id="2311b-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2311b-115">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="2311b-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2311b-116">Compilare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="2311b-116">Build the sample.</span></span>  
  
2.  <span data-ttu-id="2311b-117">Eseguire il file eseguibile DiscoveryRouter.</span><span class="sxs-lookup"><span data-stu-id="2311b-117">Run the DiscoveryRouter executable.</span></span>  
  
3.  <span data-ttu-id="2311b-118">Eseguire il servizio eseguibile dalla directory di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2311b-118">Run the service executable from the build directory.</span></span>  
  
4.  <span data-ttu-id="2311b-119">Eseguire il file eseguibile del client.</span><span class="sxs-lookup"><span data-stu-id="2311b-119">Run the client executable.</span></span> <span data-ttu-id="2311b-120">Il client individua il servizio.</span><span class="sxs-lookup"><span data-stu-id="2311b-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2311b-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2311b-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2311b-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2311b-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2311b-123">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2311b-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2311b-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2311b-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`

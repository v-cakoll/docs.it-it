---
title: Servizio router di individuazione
ms.date: 03/30/2017
ms.assetid: 3d30af47-b24f-40e5-833a-24d77125c9e6
ms.openlocfilehash: 166f6b9d1055e36f987e6b9a81fe69dc8bd548b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773035"
---
# <a name="discovery-router-service"></a><span data-ttu-id="9aeaa-102">Servizio router di individuazione</span><span class="sxs-lookup"><span data-stu-id="9aeaa-102">Discovery Router Service</span></span>
<span data-ttu-id="9aeaa-103">In questo esempio viene descritto come inoltrare messaggi di individuazione a un altro endpoint.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-103">This sample demonstrates how to forward discovery messages to another endpoint.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="9aeaa-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="9aeaa-104">Demonstrates</span></span>  
 <span data-ttu-id="9aeaa-105">Routing di individuazione</span><span class="sxs-lookup"><span data-stu-id="9aeaa-105">Discovery Routing</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="9aeaa-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="9aeaa-106">Discussion</span></span>  
 <span data-ttu-id="9aeaa-107">Il routing di individuazione è utile in uno scenario nel quale un client effettua la ricerca di un servizio utilizzando un proxy e il proxy non riconosce tale servizio, ma riconosce un altro proxy.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-107">Discovery routing is useful in a scenario in which a client is looking for a service using a proxy and the proxy is unaware of such a service, but knows of another proxy.</span></span> <span data-ttu-id="9aeaa-108">Questo proxy può inoltrare il pacchetto di individuazione dal client al secondo proxy.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-108">This proxy can forward the discovery packet from this client to the second proxy.</span></span> <span data-ttu-id="9aeaa-109">Il secondo proxy può ricercare il servizio e restituire le risposte al client originale.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-109">The second proxy can look for the service and return the responses to the original client.</span></span>  
  
 <span data-ttu-id="9aeaa-110">In questo esempio, un client invia un messaggio a un componente del routing di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-110">In this sample, a client sends a message to a discovery routing component.</span></span> <span data-ttu-id="9aeaa-111">Il messaggio viene inviato a un endpoint specifico nel router di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-111">This message is sent to a specific endpoint on the discovery router.</span></span> <span data-ttu-id="9aeaa-112">Il router inoltra quindi il messaggio a un endpoint multicast UDP.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-112">The router then forwards the message to a UDP multicast endpoint.</span></span> <span data-ttu-id="9aeaa-113">Il messaggio del probe raggiunge l'endpoint multicast e un servizio in ascolto su un indirizzo multicast UDP risponde al router di individuazione.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-113">The probe message goes out to the multicast endpoint and a service listening on a UDP multicast address responds to that discovery router.</span></span> <span data-ttu-id="9aeaa-114">Il router di individuazione raccoglie le risposte e le restituisce al client.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-114">The discovery router collects the responses and sends them back to the client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9aeaa-115">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="9aeaa-115">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="9aeaa-116">Compilare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-116">Build the sample.</span></span>  
  
2. <span data-ttu-id="9aeaa-117">Eseguire il file eseguibile DiscoveryRouter.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-117">Run the DiscoveryRouter executable.</span></span>  
  
3. <span data-ttu-id="9aeaa-118">Eseguire il servizio eseguibile dalla directory di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-118">Run the service executable from the build directory.</span></span>  
  
4. <span data-ttu-id="9aeaa-119">Eseguire il file eseguibile del client.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-119">Run the client executable.</span></span> <span data-ttu-id="9aeaa-120">Il client individua il servizio.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-120">Note that the client locates the service.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9aeaa-121">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9aeaa-122">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9aeaa-123">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9aeaa-124">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="9aeaa-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryRouter`

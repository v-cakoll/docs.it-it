---
title: Esempio di individuazione del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: 82cc43f1-3c8f-4771-ac19-a75ac936e2c3
ms.openlocfilehash: 1c6210472b594aec02bdf47f472a1a8b1823230c
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202066"
---
# <a name="workflow-discovery-sample"></a><span data-ttu-id="b2a2b-102">Esempio di individuazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b2a2b-102">Workflow Discovery Sample</span></span>
<span data-ttu-id="b2a2b-103">In questo esempio viene descritto come rendere individuabile un servizio flusso di lavoro e come creare un'attività di codice personalizzata in grado di effettuare la ricerca di un servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-103">This sample demonstrates how to make a workflow service discoverable and how to author a custom code activity that searches for a particular service.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b2a2b-104">Dimostra</span><span class="sxs-lookup"><span data-stu-id="b2a2b-104">Demonstrates</span></span>  
 <span data-ttu-id="b2a2b-105">Attività di ricerca di individuazione e utilizzo dei flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="b2a2b-105">Discovery Find Activity and Workflow Usage</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b2a2b-106">Discussione</span><span class="sxs-lookup"><span data-stu-id="b2a2b-106">Discussion</span></span>  
 <span data-ttu-id="b2a2b-107">Nella prima parte dell'esempio, un servizio flusso di lavoro viene reso individuabile mediante la configurazione.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-107">In the first part of the sample, a workflow service is made discoverable using configuration.</span></span> <span data-ttu-id="b2a2b-108">La configurazione può inoltre essere utilizzata per applicare il servizio in modo appropriato con metadati personalizzati (quali gli ambiti).</span><span class="sxs-lookup"><span data-stu-id="b2a2b-108">Configuration can also be used to apply the service appropriately with custom metadata (such as scopes).</span></span> <span data-ttu-id="b2a2b-109">Nel client, l'esempio impiega un'attività di codice personalizzata che utilizza l'individuazione per ricercare un servizio che corrisponda a un contratto specifico.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-109">On the client, the sample uses a custom code activity, which uses Discovery to search for a service matching a particular contract.</span></span> <span data-ttu-id="b2a2b-110">L'attività di codice restituisce un URI, che viene in seguito utilizzato da un'attività di invio.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-110">The code activity outputs a URI, which is later used by a send activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b2a2b-111">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="b2a2b-111">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b2a2b-112">Questo esempio Usa endpoint HTTP, che devono avere gli ACL URL appropriati da eseguire. per informazioni dettagliate, vedere [configurazione di http e HTTPS](../feature-details/configuring-http-and-https.md) .</span><span class="sxs-lookup"><span data-stu-id="b2a2b-112">This sample uses HTTP endpoints, which must have proper URL ACLs to run (see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md) for details).</span></span> <span data-ttu-id="b2a2b-113">L'esecuzione del comando seguente con un prompt dei comandi con privilegi elevati consente di aggiungere gli ACL appropriati.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-113">Executing the following command at an elevated command prompt should add the appropriate ACLs.</span></span> <span data-ttu-id="b2a2b-114">Se la shell non riconosce il formato della variabile, sostituire il dominio e il nome utente per gli argomenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-114">If your shell does not understand the variable format, substitute your Domain and Username for the following arguments.</span></span>  
  
    `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`
  
> [!IMPORTANT]
> <span data-ttu-id="b2a2b-115">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b2a2b-116">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-116">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b2a2b-117">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b2a2b-118">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="b2a2b-118">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\WorkflowDiscovery`

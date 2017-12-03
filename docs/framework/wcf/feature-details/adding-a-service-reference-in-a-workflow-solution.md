---
title: Aggiunta di un riferimento al servizio in una soluzione del flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a80362f8cb7dce2853472b7f03c3586e33b8578
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="adding-a-service-reference-in-a-workflow-solution"></a><span data-ttu-id="e27d5-102">Aggiunta di un riferimento al servizio in una soluzione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e27d5-102">Adding a Service Reference in a Workflow Solution</span></span>
<span data-ttu-id="e27d5-103">L'aggiunta di un riferimento al servizio in un'applicazione flusso di lavoro è leggermente differente da quella in un'applicazione WCF normale.</span><span class="sxs-lookup"><span data-stu-id="e27d5-103">Adding a service reference in a workflow application works a little differently than a regular WCF application.</span></span> <span data-ttu-id="e27d5-104">Quando si seleziona Aggiungi riferimento al servizio e si specifica l'URL del servizio, i metadati vengono scaricati e le attività personalizzate vengono generate per consentire la chiamata al servizio WCF o al servizio del flusso di lavoro WCF a cui è stato aggiunto un riferimento.</span><span class="sxs-lookup"><span data-stu-id="e27d5-104">When you select Add Service Reference and specify the URL to the service the metadata is downloaded and custom activities are generated that allow you to call the WCF service or WCF workflow service you added a reference to.</span></span> <span data-ttu-id="e27d5-105">Dopo avere aggiunto un riferimento al servizio, ricompilare la soluzione per compilare le attività generate</span><span class="sxs-lookup"><span data-stu-id="e27d5-105">After adding a service reference, rebuild the solution so the generated activities are built.</span></span> <span data-ttu-id="e27d5-106">che verranno visualizzate nella casella degli strumenti di Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e27d5-106">They will then appear in the workflow designer toolbox.</span></span> <span data-ttu-id="e27d5-107">Notare tuttavia che l'operazione viene eseguita solo se si aggiunge un riferimento al servizio all'interno di una soluzione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e27d5-107">Note however, that this will only work if you are adding a service reference within a workflow solution.</span></span> <span data-ttu-id="e27d5-108">Il cast di web riportato di seguito viene illustrato come aggiungere un riferimento al servizio in altri tipi di progetti: [chiama un servizio WCF da un flusso di lavoro in un progetto Web](http://go.microsoft.com/fwlink/?LinkId=207725).</span><span class="sxs-lookup"><span data-stu-id="e27d5-108">The following web cast shows how to add a service reference in other types of projects: [Calling a WCF Service from a Workflow in a Web Project](http://go.microsoft.com/fwlink/?LinkId=207725).</span></span>  
  
 <span data-ttu-id="e27d5-109">L'aggiunta di due o più riferimenti ai servizi contenenti lo stesso nome di operazione causa un problema.</span><span class="sxs-lookup"><span data-stu-id="e27d5-109">Adding two or more service references to services that contain the same operation name will cause a problem.</span></span> <span data-ttu-id="e27d5-110">Le attività generate chiameranno solo la prima operazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="e27d5-110">The generated activities will call only the first service operation.</span></span> <span data-ttu-id="e27d5-111">Per ovviare a questo problema rinominare le operazioni del servizio in modo da renderle diverse o modificano il nome di configurazione dell'endpoint all'interno di ogni attività generata.</span><span class="sxs-lookup"><span data-stu-id="e27d5-111">To work around this issue rename the service operations so they are different or change the endpoint configuration name within each generated activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e27d5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e27d5-112">See Also</span></span>  
 [<span data-ttu-id="e27d5-113">Servizi flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e27d5-113">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="e27d5-114">Procedura: creare un servizio flusso di lavoro che chiama il servizio di un altro flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="e27d5-114">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-that-calls-another-workflow-service.md)  
 [<span data-ttu-id="e27d5-115">Chiamata di un servizio WCF da un flusso di lavoro in un progetto Web</span><span class="sxs-lookup"><span data-stu-id="e27d5-115">Calling a WCF Service from a Workflow in a Web Project</span></span>](http://go.microsoft.com/fwlink/?LinkId=207725)

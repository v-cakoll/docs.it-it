---
title: 'Procedura: distribuire un''applicazione di integrazione COM+'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aca9df2be74dba308d3c4e4eb1c61b3e1afaa580
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="9b39e-102">Procedura: distribuire un'applicazione di integrazione COM+</span><span class="sxs-lookup"><span data-stu-id="9b39e-102">How to: Deploy a COM+ Integration Application</span></span>
<span data-ttu-id="9b39e-103">Dopo aver scritto un'applicazione di integrazione COM+, è possibile distribuirla ad altri computer.</span><span class="sxs-lookup"><span data-stu-id="9b39e-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="9b39e-104">In questo argomento viene illustrato come trasferire un'applicazione di integrazione COM+ da un computer a un altro.</span><span class="sxs-lookup"><span data-stu-id="9b39e-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="9b39e-105">Trasferimento di un'applicazione di integrazione COM+ ospitata</span><span class="sxs-lookup"><span data-stu-id="9b39e-105">Moving a COM+ hosted Integration App</span></span>  
  
1.  <span data-ttu-id="9b39e-106">Assicurarsi che [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sia installato su entrambi i computer.</span><span class="sxs-lookup"><span data-stu-id="9b39e-106">Ensure that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="9b39e-107">Esportare l'applicazione dal computer A.</span><span class="sxs-lookup"><span data-stu-id="9b39e-107">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="9b39e-108">Importare l'applicazione nel computer B.</span><span class="sxs-lookup"><span data-stu-id="9b39e-108">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="9b39e-109">Impostare la directory principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9b39e-109">Set the Application Root Directory.</span></span> <span data-ttu-id="9b39e-110">Per convenzione, è %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span><span class="sxs-lookup"><span data-stu-id="9b39e-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5.  <span data-ttu-id="9b39e-111">Copiare i file Application.config e Application.manifest dalla directory principale dell'applicazione del computer A nella directory principale dell'applicazione del computer B.</span><span class="sxs-lookup"><span data-stu-id="9b39e-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6.  <span data-ttu-id="9b39e-112">Modificare gli indirizzi endpoint del servizio nel file Application.config nel computer B per identificare il computer appropriato.</span><span class="sxs-lookup"><span data-stu-id="9b39e-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="9b39e-113">Cambiare, ad esempio, http://machineA/MyService in http://machineB/MyService.</span><span class="sxs-lookup"><span data-stu-id="9b39e-113">For example, change http://machineA/MyService to http://machineB/MyService.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="9b39e-114">Trasferimento di un'applicazione di integrazione ospitata da Web</span><span class="sxs-lookup"><span data-stu-id="9b39e-114">Moving a Web-hosted integration application</span></span>  
  
1.  <span data-ttu-id="9b39e-115">Assicurarsi che [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sia installato su entrambi i computer.</span><span class="sxs-lookup"><span data-stu-id="9b39e-115">Ensure that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is installed on both machines.</span></span>  
  
2.  <span data-ttu-id="9b39e-116">Esportare l'applicazione dal computer A.</span><span class="sxs-lookup"><span data-stu-id="9b39e-116">Export the application from machine A.</span></span>  
  
3.  <span data-ttu-id="9b39e-117">Importare l'applicazione nel computer B.</span><span class="sxs-lookup"><span data-stu-id="9b39e-117">Import the application on machine B.</span></span>  
  
4.  <span data-ttu-id="9b39e-118">Creare una radice virtuale di IIS nel computer B.</span><span class="sxs-lookup"><span data-stu-id="9b39e-118">Create an IIS vroot on machine B.</span></span>  
  
5.  <span data-ttu-id="9b39e-119">Copiare il file con estensione svc (componentName.svc) e il file Web.config dalla radice virtuale nel computer A nella radice virtuale appena creata nel computer B.</span><span class="sxs-lookup"><span data-stu-id="9b39e-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b39e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b39e-120">See Also</span></span>  
 [<span data-ttu-id="9b39e-121">Panoramica dell'integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="9b39e-121">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)  
 [<span data-ttu-id="9b39e-122">Procedura: Configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="9b39e-122">How to: Configure COM+ Service Settings</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)  
 [<span data-ttu-id="9b39e-123">Procedura: Usare lo strumento di configurazione del modello di servizi COM+</span><span class="sxs-lookup"><span data-stu-id="9b39e-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-com-service-model-configuration-tool.md)

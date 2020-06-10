---
title: "Procedura: distribuire un'applicazione di integrazione COM+"
ms.date: 03/30/2017
ms.assetid: 2e5a0510-db3c-4988-a09c-696285836650
ms.openlocfilehash: b4ae7f730296d54debc1cf2971b61e5700503430
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595427"
---
# <a name="how-to-deploy-a-com-integration-application"></a><span data-ttu-id="191df-102">Procedura: distribuire un'applicazione di integrazione COM+</span><span class="sxs-lookup"><span data-stu-id="191df-102">How to: Deploy a COM+ Integration Application</span></span>
<span data-ttu-id="191df-103">Dopo aver scritto un'applicazione di integrazione COM+, è possibile distribuirla ad altri computer.</span><span class="sxs-lookup"><span data-stu-id="191df-103">Once you have written a COM+ integration application, you may want to deploy it on another machine.</span></span> <span data-ttu-id="191df-104">In questo argomento viene illustrato come trasferire un'applicazione di integrazione COM+ da un computer a un altro.</span><span class="sxs-lookup"><span data-stu-id="191df-104">This topic describes how to move a COM+ integration application from one machine to another.</span></span>  
  
### <a name="moving-a-com-hosted-integration-app"></a><span data-ttu-id="191df-105">Trasferimento di un'applicazione di integrazione COM+ ospitata</span><span class="sxs-lookup"><span data-stu-id="191df-105">Moving a COM+ hosted Integration App</span></span>  
  
1. <span data-ttu-id="191df-106">Assicurarsi che WCF sia installato in entrambi i computer.</span><span class="sxs-lookup"><span data-stu-id="191df-106">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="191df-107">Esportare l'applicazione dal computer A.</span><span class="sxs-lookup"><span data-stu-id="191df-107">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="191df-108">Importare l'applicazione nel computer B.</span><span class="sxs-lookup"><span data-stu-id="191df-108">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="191df-109">Impostare la directory principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="191df-109">Set the Application Root Directory.</span></span> <span data-ttu-id="191df-110">Per convenzione, è %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span><span class="sxs-lookup"><span data-stu-id="191df-110">By convention, this is %PROGRAMFILES%/ComPlus Applications/{AppGUID}.</span></span>  
  
5. <span data-ttu-id="191df-111">Copiare i file Application.config e Application.manifest dalla directory principale dell'applicazione del computer A nella directory principale dell'applicazione del computer B.</span><span class="sxs-lookup"><span data-stu-id="191df-111">Copy the Application.config and Application.manifest files from the application root directory on machine A to the application root directory on machine B.</span></span>  
  
6. <span data-ttu-id="191df-112">Modificare gli indirizzi endpoint del servizio nel file Application.config nel computer B per identificare il computer appropriato.</span><span class="sxs-lookup"><span data-stu-id="191df-112">Edit the service endpoint addresses in the Application.config file on machine B to identify the appropriate machine.</span></span> <span data-ttu-id="191df-113">Ad esempio, sostituire `http://machineA/MyService` con `http://machineB/MyService`.</span><span class="sxs-lookup"><span data-stu-id="191df-113">For example, change `http://machineA/MyService` to `http://machineB/MyService`.</span></span>  
  
### <a name="moving-a-web-hosted-integration-application"></a><span data-ttu-id="191df-114">Trasferimento di un'applicazione di integrazione ospitata da Web</span><span class="sxs-lookup"><span data-stu-id="191df-114">Moving a Web-hosted integration application</span></span>  
  
1. <span data-ttu-id="191df-115">Assicurarsi che WCF sia installato in entrambi i computer.</span><span class="sxs-lookup"><span data-stu-id="191df-115">Ensure that WCF is installed on both machines.</span></span>  
  
2. <span data-ttu-id="191df-116">Esportare l'applicazione dal computer A.</span><span class="sxs-lookup"><span data-stu-id="191df-116">Export the application from machine A.</span></span>  
  
3. <span data-ttu-id="191df-117">Importare l'applicazione nel computer B.</span><span class="sxs-lookup"><span data-stu-id="191df-117">Import the application on machine B.</span></span>  
  
4. <span data-ttu-id="191df-118">Creare una radice virtuale di IIS nel computer B.</span><span class="sxs-lookup"><span data-stu-id="191df-118">Create an IIS vroot on machine B.</span></span>  
  
5. <span data-ttu-id="191df-119">Copiare il file con estensione svc (componentName.svc) e il file Web.config dalla radice virtuale nel computer A nella radice virtuale appena creata nel computer B.</span><span class="sxs-lookup"><span data-stu-id="191df-119">Copy the .svc file (componentName.svc) and the Web.config file from the vroot on machine A to the newly created vroot on machine B.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="191df-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="191df-120">See also</span></span>

- [<span data-ttu-id="191df-121">Panoramica sull'integrazione con applicazioni COM+</span><span class="sxs-lookup"><span data-stu-id="191df-121">Integrating with COM+ Applications Overview</span></span>](integrating-with-com-plus-applications-overview.md)
- [<span data-ttu-id="191df-122">Procedura: configurare le impostazioni del servizio COM+</span><span class="sxs-lookup"><span data-stu-id="191df-122">How to: Configure COM+ Service Settings</span></span>](how-to-configure-com-service-settings.md)
- [<span data-ttu-id="191df-123">Procedura: usare lo strumento di configurazione del modello di servizi di COM+</span><span class="sxs-lookup"><span data-stu-id="191df-123">How to: Use the COM+ Service Model Configuration Tool</span></span>](how-to-use-the-com-service-model-configuration-tool.md)

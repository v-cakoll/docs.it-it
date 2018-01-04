---
title: Controllo dell'avvio automatico di Host servizio WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65daceac9b865f3e8224c709d672344606905d9f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="69c68-102">Controllo dell'avvio automatico di Host servizio WCF</span><span class="sxs-lookup"><span data-stu-id="69c68-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="69c68-103">È possibile controllare le funzionalità di avvio automatico dell'host del servizio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] (WcfSvcHost.exe) per un progetto Libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] quando si esegue il debug di un altro progetto nella stessa soluzione [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] contenente più progetti.</span><span class="sxs-lookup"><span data-stu-id="69c68-103">You can control the auto-launching capability of [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Service Host (WcfSvcHost.exe) for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library project, when you debug another project in the same [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="69c68-104">A tale scopo, fare doppio clic su di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] progetto di servizio in **Esplora**, scegliere **proprietà**, fare clic su **opzioni WCF** scheda. Il **avvia Host servizio WCF durante il debug di un altro progetto nella stessa soluzione** casella di controllo è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="69c68-104">To do so, right-click the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="69c68-105">È possibile deselezionare la casella in modo che l'host del servizio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] per questo progetto specifico non venga avviato durante il debug di un altro progetto nella stessa soluzione.</span><span class="sxs-lookup"><span data-stu-id="69c68-105">You can clear the box so that [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="69c68-106">Questo comportamento non influisce sulle funzionalità di debug con F5 o con l'opzione Aggiungi riferimento al servizio per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="69c68-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="69c68-107">Questa opzione è disponibile per i progetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="69c68-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="69c68-108">Progetto Libreria di servizi [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69c68-108">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Library Project.</span></span>  
  
-   <span data-ttu-id="69c68-109">Progetto Libreria di servizi del flusso di lavoro sequenziale.</span><span class="sxs-lookup"><span data-stu-id="69c68-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="69c68-110">Progetto Libreria di servizi del flusso di lavoro di una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="69c68-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="69c68-111">Progetto Libreria di servizi di diffusione.</span><span class="sxs-lookup"><span data-stu-id="69c68-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c68-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69c68-112">See Also</span></span>  
 [<span data-ttu-id="69c68-113">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="69c68-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)

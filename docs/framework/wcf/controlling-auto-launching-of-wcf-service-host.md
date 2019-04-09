---
title: Controllo dell'avvio automatico di Host servizio WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 2fa060e567fba9bb5e6344b2c8fc67fb639ad0f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228497"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="35a8a-102">Controllo dell'avvio automatico di Host servizio WCF</span><span class="sxs-lookup"><span data-stu-id="35a8a-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="35a8a-103">È possibile controllare la funzionalità avvio automatico dell'Host del servizio Windows Communication Foundation (WCF) (WcfSvcHost.exe) per un progetto libreria di servizi WCF, quando si esegue il debug di un altro progetto nella stessa soluzione di Visual Studio che contiene più progetti.</span><span class="sxs-lookup"><span data-stu-id="35a8a-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="35a8a-104">A tale scopo, fare doppio clic il progetto di servizio WCF in **Esplora soluzioni**, scegliere **delle proprietà**, fare clic su **opzioni WCF** scheda. Il **avvia Host del servizio WCF durante il debug di un altro progetto nella stessa soluzione** casella di controllo è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="35a8a-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="35a8a-105">È possibile deselezionare la casella in modo che l'Host del servizio WCF per questo progetto specifico non viene avviata quando viene eseguito il debug di un altro progetto nella stessa soluzione.</span><span class="sxs-lookup"><span data-stu-id="35a8a-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="35a8a-106">Questo comportamento non influisce sulle funzionalità di debug con F5 o con l'opzione Aggiungi riferimento al servizio per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="35a8a-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="35a8a-107">Questa opzione è disponibile per i progetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="35a8a-107">This option is available to the following projects:</span></span>  
  
-   <span data-ttu-id="35a8a-108">Progetto libreria di servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="35a8a-108">WCF Service Library Project.</span></span>  
  
-   <span data-ttu-id="35a8a-109">Progetto Libreria di servizi del flusso di lavoro sequenziale.</span><span class="sxs-lookup"><span data-stu-id="35a8a-109">Sequential Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="35a8a-110">Progetto Libreria di servizi del flusso di lavoro di una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="35a8a-110">State Machine Workflow Service Library Project.</span></span>  
  
-   <span data-ttu-id="35a8a-111">Progetto Libreria di servizi di diffusione.</span><span class="sxs-lookup"><span data-stu-id="35a8a-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a8a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35a8a-112">See also</span></span>

- [<span data-ttu-id="35a8a-113">Host servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="35a8a-113">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)

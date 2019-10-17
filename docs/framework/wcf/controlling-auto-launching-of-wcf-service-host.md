---
title: Controllo dell'avvio automatico di Host servizio WCF
ms.date: 03/30/2017
f1_keywords:
- WcfOptions
ms.assetid: 6abe5d34-519b-4cef-8f02-3c0a7f125585
ms.openlocfilehash: 7f21cd7ea600277461146387b962a89ea0a8472b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320631"
---
# <a name="controlling-auto-launching-of-wcf-service-host"></a><span data-ttu-id="1112a-102">Controllo dell'avvio automatico di Host servizio WCF</span><span class="sxs-lookup"><span data-stu-id="1112a-102">Controlling Auto-launching of WCF Service Host</span></span>
<span data-ttu-id="1112a-103">È possibile controllare la funzionalità di avvio automatico dell'host del servizio Windows Communication Foundation (WCF) (WcfSvcHost. exe) per un progetto libreria di servizi WCF, quando si esegue il debug di un altro progetto nella stessa soluzione di Visual Studio che contiene più progetti.</span><span class="sxs-lookup"><span data-stu-id="1112a-103">You can control the auto-launching capability of Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) for a WCF Service Library project, when you debug another project in the same Visual Studio solution containing multiple projects.</span></span>  
  
 <span data-ttu-id="1112a-104">A tale scopo, fare clic con il pulsante destro del mouse sul progetto servizio WCF in **Esplora soluzioni**, scegliere **Proprietà**, quindi fare clic sulla scheda **opzioni WCF** . La casella di controllo **Avvia host del servizio WCF durante il debug di un altro progetto nella stessa soluzione** è abilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="1112a-104">To do so, right-click the WCF Service Project in **Solution Explorer**, choose **Properties**, and click **WCF Options** tab. The **Start WCF Service Host when debugging another project in the same solution** check box is enabled by default.</span></span> <span data-ttu-id="1112a-105">È possibile deselezionare la casella in modo che l'host del servizio WCF per questo progetto specifico non venga avviato quando viene eseguito il debug di un altro progetto nella stessa soluzione.</span><span class="sxs-lookup"><span data-stu-id="1112a-105">You can clear the box so that WCF Service Host for this specific project is not launched when another project is debugged in the same solution.</span></span>  
  
 <span data-ttu-id="1112a-106">Questo comportamento non influisce sulle funzionalità di debug con F5 o con l'opzione Aggiungi riferimento al servizio per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="1112a-106">This behavior does not affect the F5 debugging, or Add Service Reference functionalities for this project.</span></span>  
  
 <span data-ttu-id="1112a-107">Questa opzione è disponibile per i progetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1112a-107">This option is available to the following projects:</span></span>  
  
- <span data-ttu-id="1112a-108">Progetto libreria di servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="1112a-108">WCF Service Library Project.</span></span>  
  
- <span data-ttu-id="1112a-109">Progetto Libreria di servizi del flusso di lavoro sequenziale.</span><span class="sxs-lookup"><span data-stu-id="1112a-109">Sequential Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="1112a-110">Progetto Libreria di servizi del flusso di lavoro di una macchina a stati.</span><span class="sxs-lookup"><span data-stu-id="1112a-110">State Machine Workflow Service Library Project.</span></span>  
  
- <span data-ttu-id="1112a-111">Progetto Libreria di servizi di diffusione.</span><span class="sxs-lookup"><span data-stu-id="1112a-111">Syndication Service Library Project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1112a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1112a-112">See also</span></span>

- [<span data-ttu-id="1112a-113">Host del servizio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="1112a-113">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)

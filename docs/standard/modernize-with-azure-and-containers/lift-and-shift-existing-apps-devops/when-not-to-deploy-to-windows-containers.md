---
title: Quando non distribuire ai contenitori di Windows
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Quando non distribuire ai contenitori di Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c74b71f9c80ab51cabe0e3c4abf32f292da30763
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="4f67d-103">Quando non distribuire ai contenitori di Windows</span><span class="sxs-lookup"><span data-stu-id="4f67d-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="4f67d-104">Alcune tecnologie di Windows non sono supportati dai contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="4f67d-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="4f67d-105">In questi casi, è necessario eseguire la migrazione a macchine virtuali standard, in genere con solo Windows e IIS.</span><span class="sxs-lookup"><span data-stu-id="4f67d-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="4f67d-106">Case non è supportate nei contenitori di Windows, a partire da mid 2017:</span><span class="sxs-lookup"><span data-stu-id="4f67d-106">Cases not supported in Windows Containers, as of mid-2017:</span></span>

-   <span data-ttu-id="4f67d-107">Microsoft Message Queuing (MSMQ) non è attualmente supportato nei contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="4f67d-107">Microsoft Message Queuing (MSMQ) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="4f67d-108">Forum di richiesta di UserVoice</span><span class="sxs-lookup"><span data-stu-id="4f67d-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="4f67d-109">Forum di discussione</span><span class="sxs-lookup"><span data-stu-id="4f67d-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="4f67d-110">Microsoft Distributed Transaction Coordinator (MSDTC) attualmente non è supportata nei contenitori di Windows</span><span class="sxs-lookup"><span data-stu-id="4f67d-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers</span></span>

    -   [<span data-ttu-id="4f67d-111">Problema di GitHub</span><span class="sxs-lookup"><span data-stu-id="4f67d-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="4f67d-112">Microsoft Office non supporta attualmente i contenitori</span><span class="sxs-lookup"><span data-stu-id="4f67d-112">Microsoft Office currently does not support containers</span></span>

    -   [<span data-ttu-id="4f67d-113">Forum di richiesta di UserVoice</span><span class="sxs-lookup"><span data-stu-id="4f67d-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

<span data-ttu-id="4f67d-114">Per altri scenari non supportati e le richieste dalla community, vedere il forum di UserVoice per i contenitori di Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="4f67d-114">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4f67d-115">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4f67d-115">Additional resources</span></span>

-   <span data-ttu-id="4f67d-116">**Macchine virtuali e contenitori in Azure**</span><span class="sxs-lookup"><span data-stu-id="4f67d-116">**Virtual machines and containers in Azure**</span></span>

    [<span data-ttu-id="4f67d-117">https://docs.microsoft.com/azure/virtual-machines/windows/containers</span><span class="sxs-lookup"><span data-stu-id="4f67d-117">https://docs.microsoft.com/azure/virtual-machines/windows/containers</span></span>](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="4f67d-118">[Precedente](deploy-existing-net-apps-as-windows-containers.md)
[Successivo](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="4f67d-118">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>

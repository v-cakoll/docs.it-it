---
title: Casi in cui non eseguire la distribuzione in contenitori Windows
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Quando non eseguire la distribuzione ai contenitori Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: e06793065d1fd55bbef855576174b07dc9ace4c8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64751394"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="918c7-103">Casi in cui non eseguire la distribuzione in contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="918c7-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="918c7-104">Alcune tecnologie di Windows non sono supportati da contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="918c7-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="918c7-105">In questi casi, è comunque necessario eseguire la migrazione alle macchine virtuali standard, in genere con solo Windows e IIS.</span><span class="sxs-lookup"><span data-stu-id="918c7-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="918c7-106">Case non è supportate nei contenitori di Windows, a partire da maggio 2018:</span><span class="sxs-lookup"><span data-stu-id="918c7-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="918c7-107">Microsoft Message Queuing (MSMQ) attualmente è disponibile solo in contenitori di Windows basata su Windows Server v1803 versione, ma non in qualsiasi altro versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="918c7-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="918c7-108">Forum di richiesta di UserVoice</span><span class="sxs-lookup"><span data-stu-id="918c7-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="918c7-109">Forum di discussione</span><span class="sxs-lookup"><span data-stu-id="918c7-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="918c7-110">Microsoft Distributed Transaction Coordinator (MSDTC) non è attualmente supportato nei contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="918c7-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="918c7-111">Problema di GitHub</span><span class="sxs-lookup"><span data-stu-id="918c7-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="918c7-112">Microsoft Office non supporta attualmente i contenitori.</span><span class="sxs-lookup"><span data-stu-id="918c7-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="918c7-113">Forum di richiesta di UserVoice</span><span class="sxs-lookup"><span data-stu-id="918c7-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="918c7-114">Interfaccia utente (app client con un'interfaccia utente visiva) non sono supportati gli scenari.</span><span class="sxs-lookup"><span data-stu-id="918c7-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="918c7-115">I ruoli di Windows dell'infrastruttura (DNS, DHCP, controller di dominio, NTP, stampa, File server, di pagine IAM e così via) non sono supportati gli scenari.</span><span class="sxs-lookup"><span data-stu-id="918c7-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="918c7-116">Per altri scenari non supportate e il desiderio della community, vedere il forum di UserVoice per i contenitori di Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="918c7-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="918c7-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="918c7-117">Additional resources</span></span>

- <span data-ttu-id="918c7-118">**Le macchine virtuali e contenitori in Azure**</span><span class="sxs-lookup"><span data-stu-id="918c7-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="918c7-119">[Precedente](deploy-existing-net-apps-as-windows-containers.md)
> [Successivo](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="918c7-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>

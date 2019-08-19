---
title: Casi in cui non eseguire la distribuzione in contenitori Windows
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Quando non eseguire la distribuzione nei contenitori di Windows
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577954"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="0611d-103">Casi in cui non eseguire la distribuzione in contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="0611d-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="0611d-104">Alcune tecnologie Windows non sono supportate dai contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="0611d-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="0611d-105">In questi casi, è ancora necessario eseguire la migrazione alle macchine virtuali standard, in genere con solo Windows e IIS.</span><span class="sxs-lookup"><span data-stu-id="0611d-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="0611d-106">Casi non supportati nei contenitori di Windows, a partire dal 2018 maggio:</span><span class="sxs-lookup"><span data-stu-id="0611d-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="0611d-107">Microsoft Message Queuing (MSMQ) è attualmente disponibile solo nei contenitori di Windows basati su Windows Server v1803 release, ma non in altre versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="0611d-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="0611d-108">Forum della richiesta UserVoice</span><span class="sxs-lookup"><span data-stu-id="0611d-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="0611d-109">Forum di discussione</span><span class="sxs-lookup"><span data-stu-id="0611d-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="0611d-110">Microsoft Distributed Transaction Coordinator (MSDTC) attualmente non è supportato nei contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="0611d-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="0611d-111">Problema di GitHub</span><span class="sxs-lookup"><span data-stu-id="0611d-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="0611d-112">Microsoft Office attualmente non supporta i contenitori.</span><span class="sxs-lookup"><span data-stu-id="0611d-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="0611d-113">Forum della richiesta UserVoice</span><span class="sxs-lookup"><span data-stu-id="0611d-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="0611d-114">Le app dell'interfaccia utente (app client con interfaccia utente visiva) non sono scenari supportati.</span><span class="sxs-lookup"><span data-stu-id="0611d-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="0611d-115">I ruoli di infrastruttura Windows (DNS, DHCP, DC, NTP, PRINT, file server, IAM e così via) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0611d-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="0611d-116">Per altri scenari non supportati e richieste dalla community, vedere il forum di UserVoice per i contenitori di Windows <https://windowsserver.uservoice.com/forums/304624-containers>:.</span><span class="sxs-lookup"><span data-stu-id="0611d-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0611d-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0611d-117">Additional resources</span></span>

- <span data-ttu-id="0611d-118">**Macchine virtuali e contenitori in Azure**</span><span class="sxs-lookup"><span data-stu-id="0611d-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="0611d-119">[Precedente](deploy-existing-net-apps-as-windows-containers.md)
> [Successivo](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="0611d-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>

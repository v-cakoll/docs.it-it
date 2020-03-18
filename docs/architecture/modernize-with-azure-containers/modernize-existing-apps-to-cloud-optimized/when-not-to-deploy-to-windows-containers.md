---
title: Casi in cui non eseguire la distribuzione in contenitori Windows
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Quando non si esegue la distribuzione in contenitori WindowsWhen not to deploy to Windows Containers
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69577954"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="3e876-103">Casi in cui non eseguire la distribuzione in contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="3e876-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="3e876-104">Alcune tecnologie Windows non sono supportate dai contenitori di Windows.Some Windows technologies are not supported by Windows Containers.</span><span class="sxs-lookup"><span data-stu-id="3e876-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="3e876-105">In questi casi, è comunque necessario eseguire la migrazione a macchine virtuali standard, in genere solo con Windows e IIS.</span><span class="sxs-lookup"><span data-stu-id="3e876-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="3e876-106">Casi non supportati nei contenitori di Windows, a partire da maggio 2018:</span><span class="sxs-lookup"><span data-stu-id="3e876-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="3e876-107">Microsoft Message Queuing (MSMQ) è attualmente disponibile solo nei contenitori di Windows basati sulla versione windows Server v1803, ma non in altre versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="3e876-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="3e876-108">Forum di richiesta userVoice</span><span class="sxs-lookup"><span data-stu-id="3e876-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="3e876-109">Forum di discussione</span><span class="sxs-lookup"><span data-stu-id="3e876-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="3e876-110">Microsoft Distributed Transaction Coordinator (MSDTC) attualmente non è supportato nei contenitori di Windows.</span><span class="sxs-lookup"><span data-stu-id="3e876-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="3e876-111">Problema di GitHub</span><span class="sxs-lookup"><span data-stu-id="3e876-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="3e876-112">Microsoft Office attualmente non supporta i contenitori.</span><span class="sxs-lookup"><span data-stu-id="3e876-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="3e876-113">Forum di richiesta userVoice</span><span class="sxs-lookup"><span data-stu-id="3e876-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="3e876-114">Le app dell'interfaccia utente (app client con un'interfaccia utente visiva) non sono scenari supportati.</span><span class="sxs-lookup"><span data-stu-id="3e876-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="3e876-115">I ruoli dell'infrastruttura Windows (DNS, DHCP, DC, NTP, PRINT, File server, IAM e così via) non sono scenari supportati.</span><span class="sxs-lookup"><span data-stu-id="3e876-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="3e876-116">Per ulteriori scenari e richieste non supportati dalla community, vedere <https://windowsserver.uservoice.com/forums/304624-containers>il forum UserVoice per i contenitori di Windows: .</span><span class="sxs-lookup"><span data-stu-id="3e876-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3e876-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3e876-117">Additional resources</span></span>

- <span data-ttu-id="3e876-118">**Macchine virtuali e contenitori in Azure**</span><span class="sxs-lookup"><span data-stu-id="3e876-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="3e876-119">[Successivo](deploy-existing-net-apps-as-windows-containers.md)
> [precedente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="3e876-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>

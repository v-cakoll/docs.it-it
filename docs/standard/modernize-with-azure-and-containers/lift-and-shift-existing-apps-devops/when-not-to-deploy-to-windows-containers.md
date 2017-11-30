---
title: Quando non distribuire ai contenitori di Windows
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Quando non distribuire ai contenitori di Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 538cb518cd169f42b3e8b7324ca108a1d366137a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Quando non distribuire ai contenitori di Windows

Alcune tecnologie di Windows non sono supportati dai contenitori di Windows. In questi casi, è necessario eseguire la migrazione a macchine virtuali standard, in genere con solo Windows e IIS.

Case non è supportate nei contenitori di Windows, a partire da mid 2017:

-   Microsoft Message Queuing (MSMQ) non è attualmente supportato nei contenitori di Windows.

    -   [Forum di richiesta di UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [Forum di discussione](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Microsoft Distributed Transaction Coordinator (MSDTC) attualmente non è supportata nei contenitori di Windows

    -   [Problema di GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office non supporta attualmente i contenitori

    -   [Forum di richiesta di UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

Per altri scenari non supportati e le richieste dalla community, vedere il forum di UserVoice per i contenitori di Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Macchine virtuali e contenitori in Azure**

    [https://docs.microsoft.com/Azure/Virtual-Machines/Windows/Containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[Precedente](deploy-existing-net-apps-as-windows-containers.md)
[Successivo](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)

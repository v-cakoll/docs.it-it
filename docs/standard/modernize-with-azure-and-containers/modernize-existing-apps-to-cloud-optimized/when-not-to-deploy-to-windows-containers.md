---
title: Casi in cui non eseguire la distribuzione in contenitori Windows
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Quando non eseguire la distribuzione ai contenitori Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: c5d8f50c7b9967eba0ec01c9e864a02b6a3b201a
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611939"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Casi in cui non eseguire la distribuzione in contenitori Windows

Alcune tecnologie di Windows non sono supportati da contenitori di Windows. In questi casi, è comunque necessario eseguire la migrazione alle macchine virtuali standard, in genere con solo Windows e IIS.

Case non è supportate nei contenitori di Windows, a partire da maggio 2018: 

-   Microsoft Message Queuing (MSMQ) attualmente è disponibile solo in contenitori di Windows basata su Windows Server v1803 versione, ma non in qualsiasi altro versioni precedenti. 

    -   [Forum di richiesta di UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [Forum di discussione](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Microsoft Distributed Transaction Coordinator (MSDTC) non è attualmente supportato nei contenitori di Windows.

    -   [Problema di GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office non supporta attualmente i contenitori.

    -   [Forum di richiesta di UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   Interfaccia utente (app client con un'interfaccia utente visiva) non sono supportati gli scenari.

-   I ruoli di Windows dell'infrastruttura (DNS, DHCP, controller di dominio, NTP, stampa, File server, di pagine IAM e così via) non sono supportati gli scenari.

Per altri scenari non supportate e il desiderio della community, vedere il forum di UserVoice per i contenitori di Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Le macchine virtuali e contenitori in Azure**

    <https://azure.microsoft.com/overview/containers/>

>[!div class="step-by-step"]
>[Precedente](deploy-existing-net-apps-as-windows-containers.md)
>[Successivo](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)

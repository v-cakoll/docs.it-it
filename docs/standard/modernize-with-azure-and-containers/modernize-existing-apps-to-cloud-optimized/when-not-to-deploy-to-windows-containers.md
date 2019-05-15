---
title: Casi in cui non eseguire la distribuzione in contenitori Windows
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Quando non eseguire la distribuzione ai contenitori Windows
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638904"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Casi in cui non eseguire la distribuzione in contenitori Windows

Alcune tecnologie di Windows non sono supportati da contenitori di Windows. In questi casi, è comunque necessario eseguire la migrazione alle macchine virtuali standard, in genere con solo Windows e IIS.

Case non è supportate nei contenitori di Windows, a partire da maggio 2018:

- Microsoft Message Queuing (MSMQ) attualmente è disponibile solo in contenitori di Windows basata su Windows Server v1803 versione, ma non in qualsiasi altro versioni precedenti.

  - [Forum di richiesta di UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Forum di discussione](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Microsoft Distributed Transaction Coordinator (MSDTC) non è attualmente supportato nei contenitori di Windows.

  - [Problema di GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Microsoft Office non supporta attualmente i contenitori.

  - [Forum di richiesta di UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- Interfaccia utente (app client con un'interfaccia utente visiva) non sono supportati gli scenari.

- I ruoli di Windows dell'infrastruttura (DNS, DHCP, controller di dominio, NTP, stampa, File server, di pagine IAM e così via) non sono supportati gli scenari.

Per altri scenari non supportate e il desiderio della community, vedere il forum di UserVoice per i contenitori di Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Le macchine virtuali e contenitori in Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Precedente](deploy-existing-net-apps-as-windows-containers.md)
> [Successivo](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)

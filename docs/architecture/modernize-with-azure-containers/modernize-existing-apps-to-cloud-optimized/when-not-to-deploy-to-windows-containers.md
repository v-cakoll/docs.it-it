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
# <a name="when-not-to-deploy-to-windows-containers"></a>Casi in cui non eseguire la distribuzione in contenitori Windows

Alcune tecnologie Windows non sono supportate dai contenitori di Windows. In questi casi, è ancora necessario eseguire la migrazione alle macchine virtuali standard, in genere con solo Windows e IIS.

Casi non supportati nei contenitori di Windows, a partire dal 2018 maggio:

- Microsoft Message Queuing (MSMQ) è attualmente disponibile solo nei contenitori di Windows basati su Windows Server v1803 release, ma non in altre versioni precedenti.

  - [Forum della richiesta UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Forum di discussione](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Microsoft Distributed Transaction Coordinator (MSDTC) attualmente non è supportato nei contenitori di Windows.

  - [Problema di GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Microsoft Office attualmente non supporta i contenitori.

  - [Forum della richiesta UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- Le app dell'interfaccia utente (app client con interfaccia utente visiva) non sono scenari supportati.

- I ruoli di infrastruttura Windows (DNS, DHCP, DC, NTP, PRINT, file server, IAM e così via) non sono supportati.

Per altri scenari non supportati e richieste dalla community, vedere il forum di UserVoice per i contenitori di Windows <https://windowsserver.uservoice.com/forums/304624-containers>:.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Macchine virtuali e contenitori in Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Precedente](deploy-existing-net-apps-as-windows-containers.md)
> [Successivo](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)

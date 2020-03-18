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
# <a name="when-not-to-deploy-to-windows-containers"></a>Casi in cui non eseguire la distribuzione in contenitori Windows

Alcune tecnologie Windows non sono supportate dai contenitori di Windows.Some Windows technologies are not supported by Windows Containers. In questi casi, è comunque necessario eseguire la migrazione a macchine virtuali standard, in genere solo con Windows e IIS.

Casi non supportati nei contenitori di Windows, a partire da maggio 2018:

- Microsoft Message Queuing (MSMQ) è attualmente disponibile solo nei contenitori di Windows basati sulla versione windows Server v1803, ma non in altre versioni precedenti.

  - [Forum di richiesta userVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Forum di discussione](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Microsoft Distributed Transaction Coordinator (MSDTC) attualmente non è supportato nei contenitori di Windows.

  - [Problema di GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Microsoft Office attualmente non supporta i contenitori.

  - [Forum di richiesta userVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- Le app dell'interfaccia utente (app client con un'interfaccia utente visiva) non sono scenari supportati.

- I ruoli dell'infrastruttura Windows (DNS, DHCP, DC, NTP, PRINT, File server, IAM e così via) non sono scenari supportati.

Per ulteriori scenari e richieste non supportati dalla community, vedere <https://windowsserver.uservoice.com/forums/304624-containers>il forum UserVoice per i contenitori di Windows: .

### <a name="additional-resources"></a>Risorse aggiuntive

- **Macchine virtuali e contenitori in Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Successivo](deploy-existing-net-apps-as-windows-containers.md)
> [precedente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)

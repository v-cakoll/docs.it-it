---
title: Utilizzando i comandi di Windows PowerShell in un DockerFile per impostare i contenitori di Windows (Docker standard in base)
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3c9a4bec4f48d988ecf8c75ff340300b83a1faef
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Utilizzando i comandi di Windows PowerShell in un DockerFile per impostare i contenitori di Windows (Docker standard in base)

Con [contenitori di Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), è possibile convertire le applicazioni di Windows esistenti per le immagini Docker e distribuirle con gli stessi strumenti come il resto dell'ecosistema di Docker.

Per usare i contenitori di Windows, è sufficiente scrivere i comandi di Windows PowerShell in DockerFile, come illustrato nell'esempio seguente:

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

Viene usata in questo caso, Windows PowerShell per installare un'immagine di base di Windows Server Core, nonché a IIS.

In modo analogo, è anche possibile utilizzare i comandi di Windows PowerShell per impostare i componenti aggiuntivi quali tradizionale ASP.NET 4. x e .NET 4.6 o qualsiasi altro software Windows, come illustrato di seguito:

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
[Precedente] (visual-studio-strumenti-per-docker.md) [Avanti] (... /docker-devops-workflow/index.MD)

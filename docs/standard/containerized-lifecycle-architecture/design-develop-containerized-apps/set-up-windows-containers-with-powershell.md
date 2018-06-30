---
title: Uso di comandi di Windows PowerShell in un DockerFile per impostare i contenitori di Windows (Docker standard in base)
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: d68378a12a16dd4072b381f00241e781b40c3e16
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105550"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Uso di comandi di Windows PowerShell in un DockerFile per impostare i contenitori di Windows (Docker standard in base)

Con [i contenitori di Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), è possibile convertire le applicazioni di Windows esistenti per le immagini Docker e distribuirle con gli stessi strumenti come il resto nell'ecosistema Docker.

Per usare i contenitori di Windows, è sufficiente scrivere comandi di Windows PowerShell in DockerFile, come illustrato nell'esempio seguente:

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

In questo caso, si usa Windows PowerShell per installare un'immagine di base di Windows Server Core, nonché a IIS.

In modo analogo, è inoltre possibile utilizzare i comandi di Windows PowerShell per configurare i componenti aggiuntivi, ad esempio ASP.NET tradizionale 4.x e .NET 4.6 o qualsiasi altro software Windows, come illustrato di seguito:

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
[Precedente](visual-studio-tools-for-docker.md)
[Successivo](../docker-devops-workflow/index.md)

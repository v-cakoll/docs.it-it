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
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="14e6c-104">Utilizzando i comandi di Windows PowerShell in un DockerFile per impostare i contenitori di Windows (Docker standard in base)</span><span class="sxs-lookup"><span data-stu-id="14e6c-104">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="14e6c-105">Con [contenitori di Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), è possibile convertire le applicazioni di Windows esistenti per le immagini Docker e distribuirle con gli stessi strumenti come il resto dell'ecosistema di Docker.</span><span class="sxs-lookup"><span data-stu-id="14e6c-105">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="14e6c-106">Per usare i contenitori di Windows, è sufficiente scrivere i comandi di Windows PowerShell in DockerFile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="14e6c-106">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="14e6c-107">Viene usata in questo caso, Windows PowerShell per installare un'immagine di base di Windows Server Core, nonché a IIS.</span><span class="sxs-lookup"><span data-stu-id="14e6c-107">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="14e6c-108">In modo analogo, è anche possibile utilizzare i comandi di Windows PowerShell per impostare i componenti aggiuntivi quali tradizionale ASP.NET 4. x e .NET 4.6 o qualsiasi altro software Windows, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="14e6c-108">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="14e6c-109">[Precedente] (visual-studio-strumenti-per-docker.md) [Avanti] (... /docker-devops-workflow/index.MD)</span><span class="sxs-lookup"><span data-stu-id="14e6c-109">[Previous] (visual-studio-tools-for-docker.md) [Next] (../docker-devops-workflow/index.md)</span></span>

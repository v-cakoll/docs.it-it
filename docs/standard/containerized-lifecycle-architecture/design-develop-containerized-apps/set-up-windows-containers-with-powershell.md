---
title: Utilizzando i comandi di Windows PowerShell in un DockerFile per impostare i contenitori di Windows (Docker standard in base)
description: Ciclo di vita dell'applicazione nei contenitori Docker con strumenti e piattaforma Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: f7e92b0f1c749e2c00e3afc4ffcfc2fc88d7628f
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2017
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="532c9-104">Utilizzando i comandi di Windows PowerShell in un DockerFile per impostare i contenitori di Windows (Docker standard in base)</span><span class="sxs-lookup"><span data-stu-id="532c9-104">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="532c9-105">Con [contenitori di Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), è possibile convertire le applicazioni di Windows esistenti per le immagini Docker e distribuirle con gli stessi strumenti come il resto dell'ecosistema di Docker.</span><span class="sxs-lookup"><span data-stu-id="532c9-105">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="532c9-106">Per usare i contenitori di Windows, è sufficiente scrivere i comandi di Windows PowerShell in DockerFile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="532c9-106">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="532c9-107">Viene usata in questo caso, Windows PowerShell per installare un'immagine di base di Windows Server Core, nonché a IIS.</span><span class="sxs-lookup"><span data-stu-id="532c9-107">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="532c9-108">In modo analogo, è anche possibile utilizzare i comandi di Windows PowerShell per impostare i componenti aggiuntivi quali tradizionale ASP.NET 4. x e .NET 4.6 o qualsiasi altro software Windows, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="532c9-108">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="532c9-109">[Precedente] (visual-studio-strumenti-per-docker.md) [Avanti] (... /docker-devops-workflow/index.MD)</span><span class="sxs-lookup"><span data-stu-id="532c9-109">[Previous] (visual-studio-tools-for-docker.md) [Next] (../docker-devops-workflow/index.md)</span></span>

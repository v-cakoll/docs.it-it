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
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="4dc6a-103">Uso di comandi di Windows PowerShell in un DockerFile per impostare i contenitori di Windows (Docker standard in base)</span><span class="sxs-lookup"><span data-stu-id="4dc6a-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="4dc6a-104">Con [i contenitori di Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), è possibile convertire le applicazioni di Windows esistenti per le immagini Docker e distribuirle con gli stessi strumenti come il resto nell'ecosistema Docker.</span><span class="sxs-lookup"><span data-stu-id="4dc6a-104">With [Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="4dc6a-105">Per usare i contenitori di Windows, è sufficiente scrivere comandi di Windows PowerShell in DockerFile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4dc6a-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="4dc6a-106">In questo caso, si usa Windows PowerShell per installare un'immagine di base di Windows Server Core, nonché a IIS.</span><span class="sxs-lookup"><span data-stu-id="4dc6a-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="4dc6a-107">In modo analogo, è inoltre possibile utilizzare i comandi di Windows PowerShell per configurare i componenti aggiuntivi, ad esempio ASP.NET tradizionale 4.x e .NET 4.6 o qualsiasi altro software Windows, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4dc6a-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
<span data-ttu-id="4dc6a-108">[Precedente](visual-studio-tools-for-docker.md)
[Successivo](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="4dc6a-108">[Previous](visual-studio-tools-for-docker.md)
[Next](../docker-devops-workflow/index.md)</span></span>

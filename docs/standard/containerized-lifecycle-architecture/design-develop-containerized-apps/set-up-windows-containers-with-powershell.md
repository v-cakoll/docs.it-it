---
title: Usa i comandi di Windows PowerShell in un DockerFile per configurare i contenitori di Windows (Docker basato su standard)
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 5e85beea0efbee6a2b6594e3a49d705505a36e1c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149393"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="ea7d0-103">Usa i comandi di Windows PowerShell in un DockerFile per configurare i contenitori di Windows (Docker basato su standard)</span><span class="sxs-lookup"><span data-stu-id="ea7d0-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="ea7d0-104">Con [i contenitori Windows](/virtualization/windowscontainers/about/index), è possibile convertire le applicazioni Windows esistenti alle immagini Docker e distribuirle con gli stessi strumenti come il resto dell'ecosistema Docker.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="ea7d0-105">Per usare i contenitori di Windows, è sufficiente scrivere i comandi di Windows PowerShell in DockerFile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="ea7d0-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="ea7d0-106">In questo caso, utilizziamo Windows PowerShell per installare un'immagine di base di Windows Server Core, oltre a IIS.</span><span class="sxs-lookup"><span data-stu-id="ea7d0-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="ea7d0-107">In modo analogo, è anche possibile usare i comandi di Windows PowerShell per configurare i componenti aggiuntivi, ad esempio il tradizionale di ASP.NET 4.x e .NET 4.6 o altri software di Windows, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ea7d0-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="ea7d0-108">[Precedente](visual-studio-tools-for-docker.md)
>[Successivo](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="ea7d0-108">[Previous](visual-studio-tools-for-docker.md)
[Next](../docker-devops-workflow/index.md)</span></span>

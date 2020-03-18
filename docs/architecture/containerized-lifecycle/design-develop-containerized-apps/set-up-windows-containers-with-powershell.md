---
title: Uso dei comandi di Windows PowerShell in un oggetto DockerFile per configurare i contenitori di Windows (basati su standard Docker)
description: Informazioni su come usare PowerShell quando si lavora con Docker nei contenitori di Windows
ms.date: 02/15/2019
ms.openlocfilehash: e91d278aef1365a111e8d67ff04092dfc6a44185
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673578"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a><span data-ttu-id="9d101-103">Uso dei comandi di Windows PowerShell in un oggetto DockerFile per configurare i contenitori di Windows (basati su standard Docker)</span><span class="sxs-lookup"><span data-stu-id="9d101-103">Using Windows PowerShell commands in a DockerFile to set up Windows Containers (Docker standard based)</span></span>

<span data-ttu-id="9d101-104">I [contenitori Windows](/virtualization/windowscontainers/about/index) consentono di convertire applicazioni Windows esistenti in immagini Docker e di distribuirle con gli stessi strumenti che si usano con il resto dell'ecosistema Docker.</span><span class="sxs-lookup"><span data-stu-id="9d101-104">With [Windows Containers](/virtualization/windowscontainers/about/index), you can convert your existing Windows applications to Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span>

<span data-ttu-id="9d101-105">Per usare i contenitori Windows è sufficiente scrivere comandi di Windows PowerShell nel DockerFile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="9d101-105">To use Windows Containers, you just need to write Windows PowerShell commands in the DockerFile, as demonstrated in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="9d101-106">In questo caso si usa Windows PowerShell per installare un'immagine di base di Windows Server Core, oltre a IIS.</span><span class="sxs-lookup"><span data-stu-id="9d101-106">In this case, we're using Windows PowerShell to install a Windows Server Core base image as well as IIS.</span></span>

<span data-ttu-id="9d101-107">In modo analogo è possibile usare i comandi di Windows PowerShell anche per configurare componenti aggiuntivi come i classici ASP.NET 4.x, .NET 4.6 o qualsiasi altro software Windows, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="9d101-107">In a similar way, you also could use Windows PowerShell commands to set up additional components like the traditional ASP.NET 4.x and .NET 4.6 or any other Windows software, as shown here:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
><span data-ttu-id="9d101-108">[Successivo](visual-studio-tools-for-docker.md)
>[precedente](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="9d101-108">[Previous](visual-studio-tools-for-docker.md)
[Next](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)</span></span>

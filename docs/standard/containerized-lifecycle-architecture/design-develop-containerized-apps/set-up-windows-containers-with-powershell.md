---
title: Usa i comandi di Windows PowerShell in un DockerFile per configurare i contenitori di Windows (Docker basato su standard)
description: Informazioni su come usare PowerShell quando si lavora con Docker in contenitori Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: d9c0bc28f62d44eb7471b99c63055ef43da12a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644645"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Usa i comandi di Windows PowerShell in un DockerFile per configurare i contenitori di Windows (Docker basato su standard)

Con [i contenitori Windows](/virtualization/windowscontainers/about/index), è possibile convertire le applicazioni Windows esistenti alle immagini Docker e distribuirle con gli stessi strumenti come il resto dell'ecosistema Docker.

Per usare i contenitori di Windows, è sufficiente scrivere i comandi di Windows PowerShell in DockerFile, come illustrato nell'esempio seguente:

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

In questo caso, utilizziamo Windows PowerShell per installare un'immagine di base di Windows Server Core, oltre a IIS.

In modo analogo, è anche possibile usare i comandi di Windows PowerShell per configurare i componenti aggiuntivi, ad esempio il tradizionale di ASP.NET 4.x e .NET 4.6 o altri software di Windows, come illustrato di seguito:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Precedente](visual-studio-tools-for-docker.md)
>[Successivo](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)

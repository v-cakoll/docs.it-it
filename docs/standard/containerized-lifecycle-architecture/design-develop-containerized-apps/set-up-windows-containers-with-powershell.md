---
title: Usa i comandi di Windows PowerShell in un DockerFile per configurare i contenitori di Windows (Docker basato su standard)
description: Informazioni su come usare PowerShell quando si lavora con Docker in contenitori Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: df9e98e3f963b6492e1008455251b61a8cb6e771
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219971"
---
# <a name="using-windows-powershell-commands-in-a-dockerfile-to-set-up-windows-containers-docker-standard-based"></a>Usa i comandi di Windows PowerShell in un DockerFile per configurare i contenitori di Windows (Docker basato su standard)

Con [i contenitori Windows](/virtualization/windowscontainers/about/index), è possibile convertire le applicazioni Windows esistenti alle immagini Docker e distribuirle con gli stessi strumenti come il resto dell'ecosistema Docker.

Per usare i contenitori di Windows, è sufficiente scrivere i comandi di Windows PowerShell in DockerFile, come illustrato nell'esempio seguente:

```
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

In questo caso, utilizziamo Windows PowerShell per installare un'immagine di base di Windows Server Core, oltre a IIS.

In modo analogo, è anche possibile usare i comandi di Windows PowerShell per configurare i componenti aggiuntivi, ad esempio il tradizionale di ASP.NET 4.x e .NET 4.6 o altri software di Windows, come illustrato di seguito:

```
RUN powershell add-windowsfeature web-asp-net45
```

>[!div class="step-by-step"]
>[Precedente](visual-studio-tools-for-docker.md)
>[Successivo](build-aspnet-core-applications-linux-containers-aks-kubernetes.md)

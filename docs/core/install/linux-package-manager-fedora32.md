---
title: Installare .NET Core in Fedora 32-Package Manager-.NET Core
description: Usare uno Gestione pacchetti per installare .NET Core SDK e Runtime in Fedora 32.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624966"
---
# <a name="fedora-32-package-manager---install-net-core"></a>Gestione pacchetti Fedora 32-installare .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

Questo articolo descrive come usare un gestore di pacchetti per installare .NET Core in Fedora 32.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

A partire da Fedora 32, .NET Core 3,1 è disponibile nei repository dei pacchetti predefiniti in Fedora.

## <a name="install-the-net-core-sdk"></a>Installare il .NET Core SDK

Installare .NET Core SDK. Nel terminale eseguire il comando seguente.

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Installare il runtime di ASP.NET Core

Installare il runtime di ASP.NET. Nel terminale eseguire il comando seguente.

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Installare il runtime di .NET Core

Installare il runtime di .NET Core. Nel terminale eseguire il comando seguente.

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

Per installare altre versioni di .NET Core, installare manualmente [il .NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) o [il runtime di .NET Core](runtime.md?pivots=os-linux#download-and-manually-install).

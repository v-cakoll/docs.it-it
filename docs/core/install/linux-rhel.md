---
title: Installare .NET Core in RHEL-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in RHEL.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 4a406fe1834c16bab9a5548b69206b51270b33fa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324715"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-rhel"></a>Installare .NET Core SDK o runtime di .NET Core in RHEL

.NET Core è supportato in RHEL. Questo articolo descrive come installare .NET Core in RHEL.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Registrare la sottoscrizione di Red Hat

Per installare .NET Core da Red Hat in RHEL, è prima necessario registrarsi usando Red Hat Subscription Manager. Se questa operazione non è stata eseguita nel sistema o se non si è certi, vedere la [documentazione del prodotto Red Hat per .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="supported-distributions"></a>Distribuzioni supportate

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate in RHEL 7 e RHEL 8. Queste versioni rimangono supportate fino a quando la versione di [.NET Core non raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di RHEL non è più supportata.

- Un ✔️ indica che la versione di RHEL o .NET Core è ancora supportata.
- ❌Indica che la versione di RHEL o .NET Core non è supportata nella versione RHEL.
- Quando una versione di RHEL e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| RHEL                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview (solo installazione manuale) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#rhel-8-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ [7](#rhel-7-) | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |

Le versioni seguenti di .NET Core non sono più supportate. I download per questi ancora rimangono pubblicati:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Come installare altre versioni

Per informazioni sui passaggi necessari per installare altre versioni di .NET Core, vedere la [documentazione di Red Hat relativa a .NET Core](https://access.redhat.com/documentation/net_core/) .

## <a name="rhel-8-"></a>✔️ RHEL 8

.NET Core è incluso nei repository FlussoApp per RHEL 8.

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="rhel-7-"></a>✔️ RHEL 7

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

Il comando seguente consente di installare il `scl-utils` pacchetto:

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a>Installare l'SDK

.NET Core SDK consente di sviluppare app con .NET Core. Se si installa .NET Core SDK, non è necessario installare il runtime corrispondente. Per installare .NET Core SDK, eseguire i comandi seguenti:

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

Red Hat non consiglia l'abilitazione in modo permanente `rh-dotnet31` perché potrebbe influire su altri programmi. Ad esempio, `rh-dotnet31` include una versione di `libcurl` che differisce dalla versione RHEL di base. Questo può causare problemi nei programmi che non prevedono una versione diversa di `libcurl` . Se si vuole abilitare in `rh-dotnet` modo permanente, aggiungere la riga seguente al file _~/.bashrc_ .

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a>Installare il runtime

Il runtime di .NET Core consente di eseguire app eseguite con .NET Core che non includevano il Runtime. I comandi seguenti consentono di installare il runtime di ASP.NET Core, che è il runtime più compatibile per .NET Core. Nel terminale eseguire i comandi seguenti.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31-aspnetcore-runtime-3.1 bash
```

Red Hat non consiglia l'abilitazione in modo permanente `rh-dotnet31-aspnetcore-runtime-3.1` perché potrebbe influire su altri programmi. Ad esempio, `rh-dotnet31-aspnetcore-runtime-3.1` include una versione di `libcurl` che differisce dalla versione RHEL di base. Questo può causare problemi nei programmi che non prevedono una versione diversa di `libcurl` . Se si vuole abilitare in `rh-dotnet31-aspnetcore-runtime-3.1` modo permanente, aggiungere la riga seguente al file _~/.bashrc_ .

```bash
source scl_source enable rh-dotnet31-aspnetcore-runtime-3.1
```

In alternativa al runtime di ASP.NET Core, è possibile installare il runtime di .NET Core che non include ASP.NET Core supporto: sostituire `rh-dotnet31-aspnetcore-runtime-3.1` nei comandi precedenti con `rh-dotnet31-dotnet-runtime-3.1` .

## <a name="snap"></a>Snap

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Dependencies

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a>Installazione tramite script

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Installazione manuale

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Passaggi successivi

- [Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code](../tutorials/with-visual-studio-code.md)

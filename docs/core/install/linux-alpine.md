---
title: Installare .NET Core su Alpine-.NET Core
description: Vengono illustrati i vari modi per installare .NET Core SDK e il runtime di .NET Core in Alpine.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: bbaf4ee9020dcd33c894b5376bf04ad65db8d378
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84771503"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-alpine"></a>Installare .NET Core SDK o runtime di .NET Core in Alpine

Questo articolo descrive come installare .NET Core su Alpine. Quando una versione alpina non è più supportata, .NET Core non è più supportato con tale versione. Tuttavia, queste istruzioni possono essere utili per l'esecuzione di .NET Core in tali versioni, anche se non sono supportate.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

Non sono disponibili programmi di installazione per Alpine. È necessario utilizzare lo [script di installazione](#scripted-install) o seguire le istruzioni di [installazione manuale](#manual-install) .

## <a name="supported-distributions"></a>Distribuzioni supportate

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni Alpine su cui sono supportate. Queste versioni rimangono supportate fino a quando la versione di [.NET Core raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Alpine raggiunge la fine del ciclo di vita](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- Un ✔️ indica che la versione di Alpine o .NET Core è ancora supportata.
- ❌Indica che la versione di Alpine o .NET Core non è supportata nella versione alpina.
- Quando una versione di Alpine e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| Alpine                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview |
|--------------------------|---------------|---------------|----------------|
| ✔️ 3,12  | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ 3,11  | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ 3,10  | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ 3,9   | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ❌3,8   | ✔️ 2,1        | ❌3,1        | ❌Anteprima 5,0 |

Le versioni seguenti di .NET Core non sono più supportate. I download per questi ancora rimangono pubblicati:

- 3.0
- 2.2
- 2.0

## <a name="dependencies"></a>Dependencies

.NET Core su Alpine Linux richiede l'installazione delle seguenti dipendenze:

- le librerie ICU
- krb5-libs
- libintl
- libssl 1.1 (Alpine v 3.9 o versione successiva)
- libssl 1.0 (Alpine v 3.8)
- libstdc++
- lttng-ust
- numactl (facoltativo)
- zlib

## <a name="scripted-install"></a>Installazione tramite script

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Installazione manuale

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Passaggi successivi

- [Esercitazione: creare un'applicazione console con .NET Core SDK usando Visual Studio Code](../tutorials/with-visual-studio-code.md)

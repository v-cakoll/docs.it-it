---
ms.openlocfilehash: fb78e1439a680a8dbb9fc0eb8afdeee3efef7ead
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768397"
---

Gli [script DotNet-install](../../tools/dotnet-install-script.md) vengono usati per le installazioni di automazione e non amministratore di **SDK** e **Runtime**. È possibile scaricare lo script da <https://dot.net/v1/dotnet-install.sh>.

Per impostazione predefinita, lo script installa la versione più recente di SDK a [lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. Per installare la versione corrente, che non può essere una versione (LTS), usare il `-c Current` parametro.

```bash
./dotnet-install.sh -c Current
```

Per installare Runtime di .NET Core anziché SDK, usare il `--runtime` parametro.

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

È possibile installare una versione specifica modificando il `-c` parametro per indicare la versione specifica. Il comando seguente installa .NET Core SDK 3,1.

```bash
./dotnet-install.sh -c 3.1
```

Per ulteriori informazioni, vedere Guida di [riferimento agli script DotNet-install](../../tools/dotnet-install-script.md).

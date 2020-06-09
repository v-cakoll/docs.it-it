---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602950"
---

Gli [script DotNet-install](../../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell' **SDK**. È possibile scaricare lo script da <https://dot.net/v1/dotnet-install.sh>.

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. Per installare la versione corrente, che non può essere una versione (LTS), usare il `-c Current` parametro.

```bash
./dotnet-install.sh -c Current
```

Per installare Runtime di .NET Core anziché SDK, usare il `--runtime` parametro.

```bash
./dotnet-install.sh -c Current --runtime
```

È possibile installare una versione specifica modificando il `-c` parametro per indicare la versione specifica. Il comando seguente installa .NET Core SDK 3,1.

```bash
./dotnet-install.sh -c 3.1
```

Per ulteriori informazioni, vedere Guida di [riferimento agli script DotNet-install](../../tools/dotnet-install-script.md).

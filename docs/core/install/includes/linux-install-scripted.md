---
ms.openlocfilehash: 0d29407896145bc3b2ed8284c839ae8f2f0521b2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602950"
---

<span data-ttu-id="6f6a0-101">Gli [script DotNet-install](../../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell' **SDK**.</span><span class="sxs-lookup"><span data-stu-id="6f6a0-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK**.</span></span> <span data-ttu-id="6f6a0-102">È possibile scaricare lo script da <https://dot.net/v1/dotnet-install.sh>.</span><span class="sxs-lookup"><span data-stu-id="6f6a0-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="6f6a0-103">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="6f6a0-103">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="6f6a0-104">Per installare la versione corrente, che non può essere una versione (LTS), usare il `-c Current` parametro.</span><span class="sxs-lookup"><span data-stu-id="6f6a0-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="6f6a0-105">Per installare Runtime di .NET Core anziché SDK, usare il `--runtime` parametro.</span><span class="sxs-lookup"><span data-stu-id="6f6a0-105">To install .NET Core Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime
```

<span data-ttu-id="6f6a0-106">È possibile installare una versione specifica modificando il `-c` parametro per indicare la versione specifica.</span><span class="sxs-lookup"><span data-stu-id="6f6a0-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="6f6a0-107">Il comando seguente installa .NET Core SDK 3,1.</span><span class="sxs-lookup"><span data-stu-id="6f6a0-107">The following command installs .NET Core SDK 3.1.</span></span>

```bash
./dotnet-install.sh -c 3.1
```

<span data-ttu-id="6f6a0-108">Per ulteriori informazioni, vedere Guida di [riferimento agli script DotNet-install](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="6f6a0-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>

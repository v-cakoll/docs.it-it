---
ms.openlocfilehash: fb78e1439a680a8dbb9fc0eb8afdeee3efef7ead
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768397"
---

<span data-ttu-id="ae329-101">Gli [script DotNet-install](../../tools/dotnet-install-script.md) vengono usati per le installazioni di automazione e non amministratore di **SDK** e **Runtime**.</span><span class="sxs-lookup"><span data-stu-id="ae329-101">The [dotnet-install scripts](../../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="ae329-102">È possibile scaricare lo script da <https://dot.net/v1/dotnet-install.sh>.</span><span class="sxs-lookup"><span data-stu-id="ae329-102">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="ae329-103">Per impostazione predefinita, lo script installa la versione più recente di SDK a [lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="ae329-103">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="ae329-104">Per installare la versione corrente, che non può essere una versione (LTS), usare il `-c Current` parametro.</span><span class="sxs-lookup"><span data-stu-id="ae329-104">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="ae329-105">Per installare Runtime di .NET Core anziché SDK, usare il `--runtime` parametro.</span><span class="sxs-lookup"><span data-stu-id="ae329-105">To install .NET Core Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="ae329-106">È possibile installare una versione specifica modificando il `-c` parametro per indicare la versione specifica.</span><span class="sxs-lookup"><span data-stu-id="ae329-106">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="ae329-107">Il comando seguente installa .NET Core SDK 3,1.</span><span class="sxs-lookup"><span data-stu-id="ae329-107">The following command installs .NET Core SDK 3.1.</span></span>

```bash
./dotnet-install.sh -c 3.1
```

<span data-ttu-id="ae329-108">Per ulteriori informazioni, vedere Guida di [riferimento agli script DotNet-install](../../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="ae329-108">For more information, see [dotnet-install scripts reference](../../tools/dotnet-install-script.md).</span></span>

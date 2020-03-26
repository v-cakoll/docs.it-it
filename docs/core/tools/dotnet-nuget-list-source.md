---
title: comando dotnet nuget list source command
description: Il comando dotnet nuget list source elenca tutte le origini esistenti dai file di configurazione NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 4d7bc3dbd3ab5eb14c1ebf592044b685d28355cd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148575"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="cafb1-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="cafb1-103">dotnet nuget list source</span></span>

<span data-ttu-id="cafb1-104">**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="cafb1-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cafb1-105">Nome</span><span class="sxs-lookup"><span data-stu-id="cafb1-105">Name</span></span>

<span data-ttu-id="cafb1-106">`dotnet nuget list source`- Elenca tutte le origini NuGet configurate.</span><span class="sxs-lookup"><span data-stu-id="cafb1-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cafb1-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cafb1-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format] [--configfile]
dotnet nuget list source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="cafb1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cafb1-108">Description</span></span>

<span data-ttu-id="cafb1-109">Il `dotnet nuget list source` comando elenca tutte le origini esistenti dai file di configurazione NuGet.The command lists all existing sources from your NuGet configuration files.</span><span class="sxs-lookup"><span data-stu-id="cafb1-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="cafb1-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cafb1-110">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="cafb1-111">Il file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="cafb1-111">The NuGet configuration file.</span></span> <span data-ttu-id="cafb1-112">Se specificato, verranno utilizzate solo le impostazioni di questo file.</span><span class="sxs-lookup"><span data-stu-id="cafb1-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="cafb1-113">Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cafb1-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="cafb1-114">Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="cafb1-114">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format`**

  <span data-ttu-id="cafb1-115">Il formato dell'output `Detailed` del comando elenco: (impostazione predefinita) e `Short`.</span><span class="sxs-lookup"><span data-stu-id="cafb1-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="cafb1-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="cafb1-116">Examples</span></span>

- <span data-ttu-id="cafb1-117">Elencare le origini configurate dalla directory corrente:</span><span class="sxs-lookup"><span data-stu-id="cafb1-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="cafb1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cafb1-118">See also</span></span>

- [<span data-ttu-id="cafb1-119">Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files</span><span class="sxs-lookup"><span data-stu-id="cafb1-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="cafb1-120">comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="cafb1-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)

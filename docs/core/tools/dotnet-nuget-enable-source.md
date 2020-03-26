---
title: dotnet nuget abilita il comando source
description: Il comando dotnet nuget enable source abilita un'origine esistente nei file di configurazione NuGet.The dotnet nuget enable source command enables an existing source in your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: 1f18e7db6a6c8631bb432676dd97dabfad5b0ab8
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148561"
---
# <a name="dotnet-nuget-enable-source"></a><span data-ttu-id="1b7f0-103">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="1b7f0-103">dotnet nuget enable source</span></span>

<span data-ttu-id="1b7f0-104">**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="1b7f0-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="1b7f0-105">Nome</span><span class="sxs-lookup"><span data-stu-id="1b7f0-105">Name</span></span>

<span data-ttu-id="1b7f0-106">`dotnet nuget enable source`- Abilitare un'origine NuGet.- Enable a NuGet source.</span><span class="sxs-lookup"><span data-stu-id="1b7f0-106">`dotnet nuget enable source` - Enable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1b7f0-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1b7f0-107">Synopsis</span></span>

```dotnetcli
dotnet nuget enable source <NAME> [--configfile]
dotnet nuget enable source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="1b7f0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b7f0-108">Description</span></span>

<span data-ttu-id="1b7f0-109">Il `dotnet nuget enable source` comando abilita un'origine esistente nei file di configurazione NuGet.The command enables an existing source in your NuGet configuration files.</span><span class="sxs-lookup"><span data-stu-id="1b7f0-109">The `dotnet nuget enable source` command enables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="1b7f0-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1b7f0-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="1b7f0-111">Nome dell'origine.</span><span class="sxs-lookup"><span data-stu-id="1b7f0-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="1b7f0-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1b7f0-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="1b7f0-113">Il file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="1b7f0-113">The NuGet configuration file.</span></span> <span data-ttu-id="1b7f0-114">Se specificato, verranno utilizzate solo le impostazioni di questo file.</span><span class="sxs-lookup"><span data-stu-id="1b7f0-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="1b7f0-115">Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1b7f0-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="1b7f0-116">Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="1b7f0-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="1b7f0-117">Esempi</span><span class="sxs-lookup"><span data-stu-id="1b7f0-117">Examples</span></span>

- <span data-ttu-id="1b7f0-118">Abilitare un'origine `mySource`con nome di :</span><span class="sxs-lookup"><span data-stu-id="1b7f0-118">Enable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="1b7f0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b7f0-119">See also</span></span>

- [<span data-ttu-id="1b7f0-120">Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files</span><span class="sxs-lookup"><span data-stu-id="1b7f0-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="1b7f0-121">comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="1b7f0-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)

---
title: dotnet nuget rimuovere il comando di origine
description: Il comando dotnet nuget remove source rimuove un'origine esistente dai file di configurazione NuGet.The dotnet nuget remove source command removes an existing source from your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: b259873e1885644b272136fa31414410bdfd9f27
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463496"
---
# <a name="dotnet-nuget-remove-source"></a><span data-ttu-id="167a6-103">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="167a6-103">dotnet nuget remove source</span></span>

<span data-ttu-id="167a6-104">**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="167a6-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="167a6-105">Nome</span><span class="sxs-lookup"><span data-stu-id="167a6-105">Name</span></span>

<span data-ttu-id="167a6-106">`dotnet nuget remove source`- Rimuovere un'origine NuGet.- Remove a NuGet source.</span><span class="sxs-lookup"><span data-stu-id="167a6-106">`dotnet nuget remove source` - Remove a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="167a6-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="167a6-107">Synopsis</span></span>

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a><span data-ttu-id="167a6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="167a6-108">Description</span></span>

<span data-ttu-id="167a6-109">Il `dotnet nuget remove source` comando rimuove un'origine esistente dai file di configurazione NuGet.The command removes an existing source from your NuGet configuration files.</span><span class="sxs-lookup"><span data-stu-id="167a6-109">The `dotnet nuget remove source` command removes an existing source from your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="167a6-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="167a6-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="167a6-111">Nome dell'origine.</span><span class="sxs-lookup"><span data-stu-id="167a6-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="167a6-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="167a6-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="167a6-113">Il file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="167a6-113">The NuGet configuration file.</span></span> <span data-ttu-id="167a6-114">Se specificato, verranno utilizzate solo le impostazioni di questo file.</span><span class="sxs-lookup"><span data-stu-id="167a6-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="167a6-115">Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="167a6-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="167a6-116">Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="167a6-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="167a6-117">Esempi</span><span class="sxs-lookup"><span data-stu-id="167a6-117">Examples</span></span>

- <span data-ttu-id="167a6-118">Rimuovere un'origine `mySource`con il nome di :</span><span class="sxs-lookup"><span data-stu-id="167a6-118">Remove a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="167a6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="167a6-119">See also</span></span>

- [<span data-ttu-id="167a6-120">Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files</span><span class="sxs-lookup"><span data-stu-id="167a6-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="167a6-121">comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="167a6-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)

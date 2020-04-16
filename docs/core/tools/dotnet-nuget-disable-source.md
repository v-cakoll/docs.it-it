---
title: dotnet nuget disable source comando
description: Il comando dotnet nuget disable source disabilita un'origine esistente nei file di configurazione NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 54acb40b1944eaff347107e8f3439578ec8e0f3c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463577"
---
# <a name="dotnet-nuget-disable-source"></a><span data-ttu-id="65374-103">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="65374-103">dotnet nuget disable source</span></span>

<span data-ttu-id="65374-104">**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="65374-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="65374-105">Nome</span><span class="sxs-lookup"><span data-stu-id="65374-105">Name</span></span>

<span data-ttu-id="65374-106">`dotnet nuget disable source`- Disabilitare un'origine NuGet.- Disable a NuGet source.</span><span class="sxs-lookup"><span data-stu-id="65374-106">`dotnet nuget disable source` - Disable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="65374-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="65374-107">Synopsis</span></span>

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a><span data-ttu-id="65374-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65374-108">Description</span></span>

<span data-ttu-id="65374-109">Il `dotnet nuget disable source` comando disabilita un'origine esistente nei file di configurazione NuGet.The command disables an existing source in your NuGet configuration files.</span><span class="sxs-lookup"><span data-stu-id="65374-109">The `dotnet nuget disable source` command disables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="65374-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="65374-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="65374-111">Nome dell'origine.</span><span class="sxs-lookup"><span data-stu-id="65374-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="65374-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="65374-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="65374-113">Il file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="65374-113">The NuGet configuration file.</span></span> <span data-ttu-id="65374-114">Se specificato, verranno utilizzate solo le impostazioni di questo file.</span><span class="sxs-lookup"><span data-stu-id="65374-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="65374-115">Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="65374-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="65374-116">Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="65374-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="65374-117">Esempi</span><span class="sxs-lookup"><span data-stu-id="65374-117">Examples</span></span>

- <span data-ttu-id="65374-118">Disabilitare un'origine `mySource`con il nome di :</span><span class="sxs-lookup"><span data-stu-id="65374-118">Disable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="65374-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65374-119">See also</span></span>

- [<span data-ttu-id="65374-120">Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files</span><span class="sxs-lookup"><span data-stu-id="65374-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="65374-121">comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="65374-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)

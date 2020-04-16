---
title: comando dotnet nuget list source command
description: Il comando dotnet nuget list source elenca tutte le origini esistenti dai file di configurazione NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 8b14413949bd60ddeed977d19eec9bb99982da70
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463546"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="80b8b-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="80b8b-103">dotnet nuget list source</span></span>

<span data-ttu-id="80b8b-104">**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="80b8b-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="80b8b-105">Nome</span><span class="sxs-lookup"><span data-stu-id="80b8b-105">Name</span></span>

<span data-ttu-id="80b8b-106">`dotnet nuget list source`- Elenca tutte le origini NuGet configurate.</span><span class="sxs-lookup"><span data-stu-id="80b8b-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="80b8b-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="80b8b-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format [Detailed|Short]] [--configfile <FILE>]

dotnet nuget list source -h|--help
```

## <a name="description"></a><span data-ttu-id="80b8b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="80b8b-108">Description</span></span>

<span data-ttu-id="80b8b-109">Il `dotnet nuget list source` comando elenca tutte le origini esistenti dai file di configurazione NuGet.The command lists all existing sources from your NuGet configuration files.</span><span class="sxs-lookup"><span data-stu-id="80b8b-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="80b8b-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="80b8b-110">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="80b8b-111">Il file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="80b8b-111">The NuGet configuration file.</span></span> <span data-ttu-id="80b8b-112">Se specificato, verranno utilizzate solo le impostazioni di questo file.</span><span class="sxs-lookup"><span data-stu-id="80b8b-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="80b8b-113">Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="80b8b-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="80b8b-114">Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="80b8b-114">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format [Detailed|Short]`**

  <span data-ttu-id="80b8b-115">Il formato dell'output `Detailed` del comando elenco: (impostazione predefinita) e `Short`.</span><span class="sxs-lookup"><span data-stu-id="80b8b-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="80b8b-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="80b8b-116">Examples</span></span>

- <span data-ttu-id="80b8b-117">Elencare le origini configurate dalla directory corrente:</span><span class="sxs-lookup"><span data-stu-id="80b8b-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="80b8b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80b8b-118">See also</span></span>

- [<span data-ttu-id="80b8b-119">Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files</span><span class="sxs-lookup"><span data-stu-id="80b8b-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="80b8b-120">comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="80b8b-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)

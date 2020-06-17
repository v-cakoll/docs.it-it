---
title: Comando dotnet msbuild
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
ms.date: 02/14/2020
ms.openlocfilehash: 9739fe782e17db3955db087ca1781ad4280cd491
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803167"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="60fb8-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="60fb8-103">dotnet msbuild</span></span>

<span data-ttu-id="60fb8-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="60fb8-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="60fb8-105">Nome</span><span class="sxs-lookup"><span data-stu-id="60fb8-105">Name</span></span>

<span data-ttu-id="60fb8-106">`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="60fb8-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span> <span data-ttu-id="60fb8-107">Nota: potrebbe essere necessario specificare un file di soluzione o di progetto se sono presenti più file.</span><span class="sxs-lookup"><span data-stu-id="60fb8-107">Note: A solution or project file may need to be specified if there are multiple.</span></span>

## <a name="synopsis"></a><span data-ttu-id="60fb8-108">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="60fb8-108">Synopsis</span></span>

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a><span data-ttu-id="60fb8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="60fb8-109">Description</span></span>

<span data-ttu-id="60fb8-110">Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="60fb8-110">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="60fb8-111">Il comando ha esattamente le stesse funzionalità del client della riga di comando MSBuild esistente solo per i progetti in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="60fb8-111">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="60fb8-112">Le opzioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="60fb8-112">The options are all the same.</span></span> <span data-ttu-id="60fb8-113">Per ulteriori informazioni sulle opzioni disponibili, vedere la Guida di [riferimento alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="60fb8-113">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="60fb8-114">Il comando [dotnet build](dotnet-build.md) equivale a `dotnet msbuild -restore`.</span><span class="sxs-lookup"><span data-stu-id="60fb8-114">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore`.</span></span> <span data-ttu-id="60fb8-115">Quando non si vuole compilare il progetto e si dispone di una destinazione specifica che si vuole eseguire, usare `dotnet build` o `dotnet msbuild` e specificare la destinazione.</span><span class="sxs-lookup"><span data-stu-id="60fb8-115">When you don't want to build the project and you have a specific target you want to run, use `dotnet build` or `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="60fb8-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="60fb8-116">Examples</span></span>

- <span data-ttu-id="60fb8-117">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="60fb8-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="60fb8-118">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="60fb8-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="60fb8-119">Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="60fb8-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="60fb8-120">Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:</span><span class="sxs-lookup"><span data-stu-id="60fb8-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  dotnet msbuild -preprocess:<fileName>.xml
  ```

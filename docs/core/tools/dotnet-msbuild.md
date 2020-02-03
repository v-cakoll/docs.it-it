---
title: Comando dotnet msbuild
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: dae1e9f0ca355166d41c11fbafb80c7c9fb29748
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733192"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="db9ed-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="db9ed-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="db9ed-104">Name</span><span class="sxs-lookup"><span data-stu-id="db9ed-104">Name</span></span>

<span data-ttu-id="db9ed-105">`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="db9ed-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="db9ed-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="db9ed-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="db9ed-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db9ed-107">Description</span></span>

<span data-ttu-id="db9ed-108">Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="db9ed-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="db9ed-109">Il comando ha esattamente le stesse funzionalità del client della riga di comando MSBuild esistente solo per i progetti in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="db9ed-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="db9ed-110">Le opzioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="db9ed-110">The options are all the same.</span></span> <span data-ttu-id="db9ed-111">Per ulteriori informazioni sulle opzioni disponibili, vedere la Guida di [riferimento alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="db9ed-111">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="db9ed-112">Il comando [dotnet build](dotnet-build.md) equivale a `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="db9ed-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="db9ed-113">la [compilazione DotNet](dotnet-build.md) è più comunemente utilizzata per la compilazione di progetti, ma poiché viene sempre eseguita la destinazione di compilazione, è possibile utilizzare `dotnet msbuild` quando non si desidera compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="db9ed-113">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="db9ed-114">Se, ad esempio, si dispone di una destinazione specifica che si desidera eseguire senza compilare il progetto, utilizzare `dotnet msbuild` e specificare la destinazione.</span><span class="sxs-lookup"><span data-stu-id="db9ed-114">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="db9ed-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="db9ed-115">Examples</span></span>

* <span data-ttu-id="db9ed-116">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="db9ed-116">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

* <span data-ttu-id="db9ed-117">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="db9ed-117">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

* <span data-ttu-id="db9ed-118">Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="db9ed-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="db9ed-119">Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:</span><span class="sxs-lookup"><span data-stu-id="db9ed-119">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```

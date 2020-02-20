---
title: Comando dotnet msbuild
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
ms.date: 02/14/2020
ms.openlocfilehash: 28a32a460d644d3e22f16b5dd9416222ae466e2e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503673"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="cfc6d-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="cfc6d-103">dotnet msbuild</span></span>

<span data-ttu-id="cfc6d-104">**Questo articolo si applica a:** ✔️ .NET Core 2. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="cfc6d-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="cfc6d-105">Nome</span><span class="sxs-lookup"><span data-stu-id="cfc6d-105">Name</span></span>

<span data-ttu-id="cfc6d-106">`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="cfc6d-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cfc6d-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cfc6d-107">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="cfc6d-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cfc6d-108">Description</span></span>

<span data-ttu-id="cfc6d-109">Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="cfc6d-109">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="cfc6d-110">Il comando ha esattamente le stesse funzionalità del client della riga di comando MSBuild esistente solo per i progetti in stile SDK.</span><span class="sxs-lookup"><span data-stu-id="cfc6d-110">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="cfc6d-111">Le opzioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="cfc6d-111">The options are all the same.</span></span> <span data-ttu-id="cfc6d-112">Per ulteriori informazioni sulle opzioni disponibili, vedere la Guida di [riferimento alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="cfc6d-112">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="cfc6d-113">Il comando [dotnet build](dotnet-build.md) equivale a `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="cfc6d-113">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="cfc6d-114">la [compilazione DotNet](dotnet-build.md) è più comunemente utilizzata per la compilazione di progetti, ma poiché viene sempre eseguita la destinazione di compilazione, è possibile utilizzare `dotnet msbuild` quando non si desidera compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="cfc6d-114">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="cfc6d-115">Se, ad esempio, si dispone di una destinazione specifica che si desidera eseguire senza compilare il progetto, utilizzare `dotnet msbuild` e specificare la destinazione.</span><span class="sxs-lookup"><span data-stu-id="cfc6d-115">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="cfc6d-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="cfc6d-116">Examples</span></span>

- <span data-ttu-id="cfc6d-117">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="cfc6d-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="cfc6d-118">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="cfc6d-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="cfc6d-119">Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="cfc6d-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="cfc6d-120">Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:</span><span class="sxs-lookup"><span data-stu-id="cfc6d-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```

---
title: Comando dotnet msbuild - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: 93471ded9614502ab89d5afb19dd9992f068ef80
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128047"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="feb55-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="feb55-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="feb55-104">nome</span><span class="sxs-lookup"><span data-stu-id="feb55-104">Name</span></span>

<span data-ttu-id="feb55-105">`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="feb55-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="feb55-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="feb55-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="feb55-107">Description</span><span class="sxs-lookup"><span data-stu-id="feb55-107">Description</span></span>

<span data-ttu-id="feb55-108">Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="feb55-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="feb55-109">Il comando ha le stesse funzionalità del client della riga di comando di MSBuild esistente solo per il progetto di tipo SDK.</span><span class="sxs-lookup"><span data-stu-id="feb55-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style project only.</span></span> <span data-ttu-id="feb55-110">Le opzioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="feb55-110">The options are all the same.</span></span> <span data-ttu-id="feb55-111">Per altre informazioni sulle opzioni disponibili, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="feb55-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="feb55-112">Il comando [dotnet build](dotnet-build.md) equivale a `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="feb55-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="feb55-113">`dotnet build` è più usato per compilare i progetti, ma `dotnet msbuild` consente maggiore controllo.</span><span class="sxs-lookup"><span data-stu-id="feb55-113">`dotnet build` is more commonly used for building projects, but `dotnet msbuild` gives you more control.</span></span> <span data-ttu-id="feb55-114">Se ad esempio si vuole eseguire una destinazione specifica (senza eseguire la destinazione di compilazione), probabilmente è preferibile usare `dotnet msbuild`.</span><span class="sxs-lookup"><span data-stu-id="feb55-114">For example, if you have a specific target you want to run (without running the build target), you probably want to use `dotnet msbuild`.</span></span>

## <a name="examples"></a><span data-ttu-id="feb55-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="feb55-115">Examples</span></span>

* <span data-ttu-id="feb55-116">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="feb55-116">Build a project and its dependencies:</span></span>

  ```console
  dotnet msbuild
  ```

* <span data-ttu-id="feb55-117">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="feb55-117">Build a project and its dependencies using Release configuration:</span></span>

  ```console
  dotnet msbuild -p:Configuration=Release
  ```

* <span data-ttu-id="feb55-118">Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="feb55-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```console
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="feb55-119">Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:</span><span class="sxs-lookup"><span data-stu-id="feb55-119">See the whole project with all targets included by the SDK:</span></span>

  ```console
  dotnet msbuild -pp
  ```
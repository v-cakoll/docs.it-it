---
title: Comando dotnet msbuild - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 76165590478b0e76d19d546c87e012da4716b6db
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2018
ms.locfileid: "46578896"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="4f854-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="4f854-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4f854-104">nome</span><span class="sxs-lookup"><span data-stu-id="4f854-104">Name</span></span>

<span data-ttu-id="4f854-105">`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="4f854-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4f854-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4f854-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="4f854-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f854-107">Description</span></span>

<span data-ttu-id="4f854-108">Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="4f854-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="4f854-109">Il comando ha le stesse funzionalità del client della riga di comando di MSBuild esistente.</span><span class="sxs-lookup"><span data-stu-id="4f854-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="4f854-110">Le opzioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="4f854-110">The options are all the same.</span></span> <span data-ttu-id="4f854-111">Per altre informazioni sulle opzioni disponibili, vedere [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="4f854-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="examples"></a><span data-ttu-id="4f854-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="4f854-112">Examples</span></span>

<span data-ttu-id="4f854-113">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="4f854-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="4f854-114">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="4f854-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild -p:Configuration=Release`

<span data-ttu-id="4f854-115">Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="4f854-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="4f854-116">Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:</span><span class="sxs-lookup"><span data-stu-id="4f854-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild -pp`

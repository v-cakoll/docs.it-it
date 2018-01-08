---
title: Comando dotnet msbuild - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 682b49d44c0fb8242eeb3cb8bf4d158f73b4b9a5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="ae20d-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="ae20d-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ae20d-104">nome</span><span class="sxs-lookup"><span data-stu-id="ae20d-104">Name</span></span>

<span data-ttu-id="ae20d-105">`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="ae20d-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ae20d-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="ae20d-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="ae20d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae20d-107">Description</span></span>

<span data-ttu-id="ae20d-108">Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="ae20d-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="ae20d-109">Il comando ha le stesse funzionalità del client della riga di comando di MSBuild esistente.</span><span class="sxs-lookup"><span data-stu-id="ae20d-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="ae20d-110">Le opzioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="ae20d-110">The options are all the same.</span></span> <span data-ttu-id="ae20d-111">Usare [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) per ottenere informazioni sulle opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="ae20d-111">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="ae20d-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="ae20d-112">Examples</span></span>

<span data-ttu-id="ae20d-113">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="ae20d-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="ae20d-114">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="ae20d-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="ae20d-115">Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="ae20d-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="ae20d-116">Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:</span><span class="sxs-lookup"><span data-stu-id="ae20d-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`

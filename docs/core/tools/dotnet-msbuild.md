---
title: Comando dotnet msbuild - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet msbuild consente di accedere alla riga di comando di MSBuild.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 9e6f8b3063b4cd2a3a36cae8839d6f83e0466e03
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="223c5-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="223c5-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="223c5-104">nome</span><span class="sxs-lookup"><span data-stu-id="223c5-104">Name</span></span>

<span data-ttu-id="223c5-105">`dotnet msbuild`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="223c5-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="223c5-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="223c5-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="223c5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="223c5-107">Description</span></span>

<span data-ttu-id="223c5-108">Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="223c5-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="223c5-109">Il comando ha le stesse funzionalità del client della riga di comando di MSBuild esistente.</span><span class="sxs-lookup"><span data-stu-id="223c5-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="223c5-110">Le opzioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="223c5-110">The options are all the same.</span></span> <span data-ttu-id="223c5-111">Usare [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) per ottenere informazioni sulle opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="223c5-111">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="223c5-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="223c5-112">Examples</span></span>

<span data-ttu-id="223c5-113">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="223c5-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="223c5-114">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="223c5-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="223c5-115">Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="223c5-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="223c5-116">Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:</span><span class="sxs-lookup"><span data-stu-id="223c5-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`

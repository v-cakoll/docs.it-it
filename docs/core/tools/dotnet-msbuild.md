---
title: Comando dotnet-msbuild - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-msbuild consente di accedere alla riga di comando di MSBuild.
keywords: dotnet-msmsbuild, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1f02dcd779b9ed249ebd2fedb973383b1dcd8963
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-msbuild"></a><span data-ttu-id="f79a8-104">dotnet-msbuild</span><span class="sxs-lookup"><span data-stu-id="f79a8-104">dotnet-msbuild</span></span>

## <a name="name"></a><span data-ttu-id="f79a8-105">Nome</span><span class="sxs-lookup"><span data-stu-id="f79a8-105">Name</span></span>

<span data-ttu-id="f79a8-106">`dotnet-msbuild`: consente di compilare un progetto e tutte le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="f79a8-106">`dotnet-msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f79a8-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f79a8-107">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="f79a8-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f79a8-108">Description</span></span>

<span data-ttu-id="f79a8-109">Il comando `dotnet msbuild` consente di accedere a un'istanza completamente funzionante di MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f79a8-109">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="f79a8-110">Il comando ha le stesse funzionalità del client della riga di comando di MSBuild esistente.</span><span class="sxs-lookup"><span data-stu-id="f79a8-110">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="f79a8-111">Le opzioni sono uguali.</span><span class="sxs-lookup"><span data-stu-id="f79a8-111">The options are all the same.</span></span> <span data-ttu-id="f79a8-112">Usare [Riferimenti alla riga di comando di MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) per ottenere informazioni sulle opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="f79a8-112">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="f79a8-113">Esempi</span><span class="sxs-lookup"><span data-stu-id="f79a8-113">Examples</span></span>

<span data-ttu-id="f79a8-114">Compilare un progetto e le relative dipendenze:</span><span class="sxs-lookup"><span data-stu-id="f79a8-114">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="f79a8-115">Compilare un progetto e le relative dipendenze usando la configurazione per il rilascio:</span><span class="sxs-lookup"><span data-stu-id="f79a8-115">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="f79a8-116">Eseguire la destinazione di pubblicazione e pubblicare per il RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="f79a8-116">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="f79a8-117">Vedere l'intero progetto con tutte le destinazioni incluse dall'SDK:</span><span class="sxs-lookup"><span data-stu-id="f79a8-117">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`


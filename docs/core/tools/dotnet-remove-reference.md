---
title: Comando dotnet remove reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet remove reference offre un'opzione utile per rimuovere riferimenti da progetto a progetto.
keywords: dotnet-remove, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 691fd77c7605b6476adc764f20e59b51abd7d914
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="0b6a1-104">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="0b6a1-104">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0b6a1-105">nome</span><span class="sxs-lookup"><span data-stu-id="0b6a1-105">Name</span></span>

<span data-ttu-id="0b6a1-106">`dotnet remove reference`: rimuove i riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="0b6a1-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0b6a1-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="0b6a1-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="0b6a1-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b6a1-108">Description</span></span>

<span data-ttu-id="0b6a1-109">Il comando `dotnet remove reference` offre un'opzione utile per rimuovere i riferimenti al progetto da un progetto.</span><span class="sxs-lookup"><span data-stu-id="0b6a1-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="0b6a1-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0b6a1-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="0b6a1-111">File di progetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0b6a1-111">Target project file.</span></span> <span data-ttu-id="0b6a1-112">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="0b6a1-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="0b6a1-113">Riferimenti da progetto a progetto da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="0b6a1-113">Project to project (P2P references to remove.</span></span> <span data-ttu-id="0b6a1-114">È possibile specificare uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="0b6a1-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="0b6a1-115">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="0b6a1-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="0b6a1-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0b6a1-116">Options</span></span>

`-h|--help`

<span data-ttu-id="0b6a1-117">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="0b6a1-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="0b6a1-118">Rimuove il riferimento solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="0b6a1-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="0b6a1-119">Esempi</span><span class="sxs-lookup"><span data-stu-id="0b6a1-119">Examples</span></span>

<span data-ttu-id="0b6a1-120">Rimuovere un riferimento al progetto dal progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="0b6a1-120">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="0b6a1-121">Rimuovere più riferimenti al progetto dal progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="0b6a1-121">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="0b6a1-122">Rimuovere più riferimenti al progetto usando un criterio GLOB in Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="0b6a1-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`

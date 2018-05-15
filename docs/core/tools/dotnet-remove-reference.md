---
title: Comando dotnet remove reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet remove reference offre un'opzione utile per rimuovere riferimenti da progetto a progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 209f1ad62221e8a80efa161354a2c074d74b7c5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="710a2-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="710a2-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="710a2-104">nome</span><span class="sxs-lookup"><span data-stu-id="710a2-104">Name</span></span>

<span data-ttu-id="710a2-105">`dotnet remove reference`: rimuove i riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="710a2-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="710a2-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="710a2-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="710a2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="710a2-107">Description</span></span>

<span data-ttu-id="710a2-108">Il comando `dotnet remove reference` offre un'opzione utile per rimuovere i riferimenti al progetto da un progetto.</span><span class="sxs-lookup"><span data-stu-id="710a2-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="710a2-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="710a2-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="710a2-110">File di progetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="710a2-110">Target project file.</span></span> <span data-ttu-id="710a2-111">Se non specificato, il comando ne cerca uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="710a2-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="710a2-112">Riferimenti da progetto a progetto da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="710a2-112">Project to project (P2P references to remove.</span></span> <span data-ttu-id="710a2-113">È possibile specificare uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="710a2-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="710a2-114">I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="710a2-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="710a2-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="710a2-115">Options</span></span>

`-h|--help`

<span data-ttu-id="710a2-116">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="710a2-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="710a2-117">Rimuove il riferimento solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.</span><span class="sxs-lookup"><span data-stu-id="710a2-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="710a2-118">Esempi</span><span class="sxs-lookup"><span data-stu-id="710a2-118">Examples</span></span>

<span data-ttu-id="710a2-119">Rimuovere un riferimento al progetto dal progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="710a2-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="710a2-120">Rimuovere più riferimenti al progetto dal progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="710a2-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="710a2-121">Rimuovere più riferimenti al progetto usando un criterio GLOB in Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="710a2-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`

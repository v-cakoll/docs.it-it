---
title: Comando dotnet list reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: a4ceadb6d070d7997e75b472624bbe2c1650396d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="c82b9-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c82b9-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c82b9-104">nome</span><span class="sxs-lookup"><span data-stu-id="c82b9-104">Name</span></span>

<span data-ttu-id="c82b9-105">`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="c82b9-105">`dotnet list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c82b9-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="c82b9-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="c82b9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c82b9-107">Description</span></span>

<span data-ttu-id="c82b9-108">Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto specificato.</span><span class="sxs-lookup"><span data-stu-id="c82b9-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="c82b9-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c82b9-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="c82b9-110">Specifica il file di progetto da usare per l'elenco dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="c82b9-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="c82b9-111">Se non specificato, il comando cercherà un file di progetto nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="c82b9-111">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="c82b9-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c82b9-112">Options</span></span>

`-h|--help`

<span data-ttu-id="c82b9-113">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="c82b9-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="c82b9-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="c82b9-114">Examples</span></span>

<span data-ttu-id="c82b9-115">Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="c82b9-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="c82b9-116">Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="c82b9-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`

---
title: Comando dotnet list reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: b3e903c15a7486faa279d47ad5e2e00c090b19af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="a68e0-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="a68e0-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a68e0-104">Nome</span><span class="sxs-lookup"><span data-stu-id="a68e0-104">Name</span></span>

<span data-ttu-id="a68e0-105">`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="a68e0-105">`dotnet list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a68e0-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a68e0-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="a68e0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a68e0-107">Description</span></span>

<span data-ttu-id="a68e0-108">Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto specificato.</span><span class="sxs-lookup"><span data-stu-id="a68e0-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="a68e0-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a68e0-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="a68e0-110">Specifica il file di progetto da usare per l'elenco dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="a68e0-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="a68e0-111">Se non specificato, il comando cercherà un file di progetto nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a68e0-111">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="a68e0-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a68e0-112">Options</span></span>

`-h|--help`

<span data-ttu-id="a68e0-113">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a68e0-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="a68e0-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="a68e0-114">Examples</span></span>

<span data-ttu-id="a68e0-115">Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="a68e0-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="a68e0-116">Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="a68e0-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`

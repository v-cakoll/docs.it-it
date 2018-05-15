---
title: Comando dotnet list reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 24cb1124fc3f8707afe727e6a73d35d5dde39937
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="d14b8-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="d14b8-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d14b8-104">nome</span><span class="sxs-lookup"><span data-stu-id="d14b8-104">Name</span></span>

<span data-ttu-id="d14b8-105">`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="d14b8-105">`dotnet list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d14b8-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d14b8-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="d14b8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d14b8-107">Description</span></span>

<span data-ttu-id="d14b8-108">Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto specificato.</span><span class="sxs-lookup"><span data-stu-id="d14b8-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="d14b8-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d14b8-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="d14b8-110">Specifica il file di progetto da usare per l'elenco dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="d14b8-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="d14b8-111">Se non specificato, il comando cercherà un file di progetto nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d14b8-111">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="d14b8-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d14b8-112">Options</span></span>

`-h|--help`

<span data-ttu-id="d14b8-113">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d14b8-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d14b8-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="d14b8-114">Examples</span></span>

<span data-ttu-id="d14b8-115">Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="d14b8-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="d14b8-116">Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="d14b8-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`

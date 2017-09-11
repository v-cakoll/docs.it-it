---
title: Comando dotnet-list reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
keywords: dotnet-list, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8f954a0c-03f8-4fbc-a529-b313ab12c623
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 701345e4db51d26b9eefe8f02b6c0526934de5c9
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-list-reference"></a><span data-ttu-id="a2d69-104">dotnet-list reference</span><span class="sxs-lookup"><span data-stu-id="a2d69-104">dotnet-list reference</span></span>

## <a name="name"></a><span data-ttu-id="a2d69-105">Nome</span><span class="sxs-lookup"><span data-stu-id="a2d69-105">Name</span></span>

<span data-ttu-id="a2d69-106">`dotnet-list reference`: visualizza un elenco dei riferimenti da progetto a progetto.</span><span class="sxs-lookup"><span data-stu-id="a2d69-106">`dotnet-list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a2d69-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a2d69-107">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="a2d69-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2d69-108">Description</span></span>

<span data-ttu-id="a2d69-109">Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto specificato.</span><span class="sxs-lookup"><span data-stu-id="a2d69-109">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="a2d69-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a2d69-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="a2d69-111">Specifica il file di progetto da usare per l'elenco dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="a2d69-111">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="a2d69-112">Se non specificato, il comando cercherà un file di progetto nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a2d69-112">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="a2d69-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a2d69-113">Options</span></span>

`-h|--help`

<span data-ttu-id="a2d69-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a2d69-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="a2d69-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="a2d69-115">Examples</span></span>

<span data-ttu-id="a2d69-116">Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:</span><span class="sxs-lookup"><span data-stu-id="a2d69-116">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="a2d69-117">Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="a2d69-117">List the project references for the project in the current directory:</span></span>

`dotnet list reference`


---
title: Comando dotnet-remove package - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-remove package offre un'opzione utile per rimuovere il riferimento al pacchetto NuGet in un progetto.
keywords: dotnet-remove, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 2fcc8d37-16b3-4581-8038-832160e72d36
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3fef846d5850e2c2a158ccd1f30a84e8f23f793
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-remove-package"></a><span data-ttu-id="b91f9-104">dotnet-remove package</span><span class="sxs-lookup"><span data-stu-id="b91f9-104">dotnet-remove package</span></span>

## <a name="name"></a><span data-ttu-id="b91f9-105">Nome</span><span class="sxs-lookup"><span data-stu-id="b91f9-105">Name</span></span>

<span data-ttu-id="b91f9-106">`dotnet-remove package`: rimuove il riferimento al pacchetto da un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b91f9-106">`dotnet-remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b91f9-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="b91f9-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="b91f9-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b91f9-108">Description</span></span>

<span data-ttu-id="b91f9-109">Il comando `dotnet remove package` offre un'opzione utile per rimuovere un riferimento al pacchetto NuGet da un progetto.</span><span class="sxs-lookup"><span data-stu-id="b91f9-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="b91f9-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="b91f9-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="b91f9-111">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="b91f9-111">Specifies the project file.</span></span> <span data-ttu-id="b91f9-112">Se non specificato, il comando ne cercherà uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b91f9-112">If not specified, the command will search the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="b91f9-113">Riferimento al pacchetto da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="b91f9-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="b91f9-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b91f9-114">Options</span></span>

`-h|--help`

<span data-ttu-id="b91f9-115">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="b91f9-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="b91f9-116">Esempi</span><span class="sxs-lookup"><span data-stu-id="b91f9-116">Examples</span></span>

<span data-ttu-id="b91f9-117">Rimuove il pacchetto NuGet `Newtonsoft.Json` da un progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="b91f9-117">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`


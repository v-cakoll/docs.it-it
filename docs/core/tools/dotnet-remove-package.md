---
title: Comando dotnet remove package - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet remove package offre un'opzione utile per rimuovere il riferimento del pacchetto NuGet a un progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 4167f5465571259975572669e27f20c586b910da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="1d9c7-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="1d9c7-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1d9c7-104">Nome</span><span class="sxs-lookup"><span data-stu-id="1d9c7-104">Name</span></span>

<span data-ttu-id="1d9c7-105">`dotnet remove package`: rimuove il riferimento al pacchetto da un file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1d9c7-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1d9c7-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="1d9c7-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="1d9c7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d9c7-107">Description</span></span>

<span data-ttu-id="1d9c7-108">Il comando `dotnet remove package` offre un'opzione utile per rimuovere un riferimento al pacchetto NuGet da un progetto.</span><span class="sxs-lookup"><span data-stu-id="1d9c7-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="1d9c7-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1d9c7-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="1d9c7-110">Specifica il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1d9c7-110">Specifies the project file.</span></span> <span data-ttu-id="1d9c7-111">Se non specificato, il comando ne cercherà uno nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="1d9c7-111">If not specified, the command will search the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="1d9c7-112">Riferimento al pacchetto da rimuovere.</span><span class="sxs-lookup"><span data-stu-id="1d9c7-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="1d9c7-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1d9c7-113">Options</span></span>

`-h|--help`

<span data-ttu-id="1d9c7-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="1d9c7-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="1d9c7-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="1d9c7-115">Examples</span></span>

<span data-ttu-id="1d9c7-116">Rimuove il pacchetto NuGet `Newtonsoft.Json` da un progetto nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="1d9c7-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`

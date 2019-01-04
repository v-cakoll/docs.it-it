---
title: Comando dotnet tool list
description: Il comando dotnet tool list visualizza lo strumento globale .NET Core specificato del computer.
ms.date: 05/29/2018
ms.openlocfilehash: 0c17534beb80ed87a8f260342b0f82882a9e17b6
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169760"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="4271a-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="4271a-103">dotnet tool list</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="4271a-104">nome</span><span class="sxs-lookup"><span data-stu-id="4271a-104">Name</span></span>

<span data-ttu-id="4271a-105">`dotnet tool list` - Elenca tutti gli [strumenti globali .NET Core](global-tools.md) attualmente installati nella directory predefinita nel computer o nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="4271a-105">`dotnet tool list` - Lists all [.NET Core Global Tools](global-tools.md) currently installed in the default directory on your machine or in the specified path.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4271a-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4271a-106">Synopsis</span></span>

```console
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="4271a-107">Description</span><span class="sxs-lookup"><span data-stu-id="4271a-107">Description</span></span>

<span data-ttu-id="4271a-108">Il comando `dotnet tool list` consente di visualizzare tutti gli strumenti globali .NET Core installati a livello utente nel computer (profilo utente corrente) o nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="4271a-108">The `dotnet tool list` command provides a way for you to list all .NET Core Global Tools installed user-wide on your machine (current user profile) or in the specified path.</span></span> <span data-ttu-id="4271a-109">Il comando visualizza il nome del pacchetto, la versione installata e il comando dello strumento globale.</span><span class="sxs-lookup"><span data-stu-id="4271a-109">The command lists the package name, version installed, and the Global Tool command.</span></span> <span data-ttu-id="4271a-110">Per usare il comando, è necessario specificare che si vuole visualizzare tutti gli strumenti a livello utente con l'opzione `--global` oppure specificare un percorso personalizzato con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="4271a-110">To use the list command, you either have to specify that you want to see all user-wide tools using the `--global` option or specify a custom path using the `--tool-path` option.</span></span>

## <a name="options"></a><span data-ttu-id="4271a-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4271a-111">Options</span></span>

`-g|--global`

<span data-ttu-id="4271a-112">Visualizza gli strumenti globali a livello utente.</span><span class="sxs-lookup"><span data-stu-id="4271a-112">Lists user-wide Global Tools.</span></span> <span data-ttu-id="4271a-113">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="4271a-113">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="4271a-114">Se non si specifica questa opzione, è necessario specificare l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="4271a-114">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="4271a-115">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4271a-115">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="4271a-116">Specifica un percorso personalizzato in cui trovare gli strumenti globali.</span><span class="sxs-lookup"><span data-stu-id="4271a-116">Specifies a custom location where to find Global Tools.</span></span> <span data-ttu-id="4271a-117">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="4271a-117">PATH can be absolute or relative.</span></span> <span data-ttu-id="4271a-118">Non può essere usata con l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="4271a-118">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="4271a-119">Se non si specifica questa opzione, è necessario specificare l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="4271a-119">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="4271a-120">Esempi</span><span class="sxs-lookup"><span data-stu-id="4271a-120">Examples</span></span>

<span data-ttu-id="4271a-121">Elenca tutti gli strumenti globali installati a livello utente nel computer (profilo utente corrente):</span><span class="sxs-lookup"><span data-stu-id="4271a-121">Lists all Global Tools installed user-wide on your machine (current user profile):</span></span>

`dotnet tool list -g`

<span data-ttu-id="4271a-122">Elenca gli strumenti globali di una cartella di Windows specifica:</span><span class="sxs-lookup"><span data-stu-id="4271a-122">Lists the Global Tools from a specific Windows folder:</span></span>

`dotnet tool list --tool-path c:\global-tools`

<span data-ttu-id="4271a-123">Elenca gli strumenti globali di una cartella di Linux/macOS specifica:</span><span class="sxs-lookup"><span data-stu-id="4271a-123">Lists the Global Tools from a specific Linux/macOS folder:</span></span>

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="4271a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4271a-124">See also</span></span>

* [<span data-ttu-id="4271a-125">Strumenti globali .NET Core</span><span class="sxs-lookup"><span data-stu-id="4271a-125">.NET Core Global Tools</span></span>](global-tools.md)
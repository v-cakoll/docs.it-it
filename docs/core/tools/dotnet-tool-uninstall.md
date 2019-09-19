---
title: Comando dotnet tool uninstall
description: Il comando dotnet tool uninstall disinstalla lo strumento globale .NET Core specificato nel computer.
ms.date: 05/29/2018
ms.openlocfilehash: 033753f44464e78b826e908e0b6cdf276da8a179
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117550"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="73625-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="73625-103">dotnet tool uninstall</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="73625-104">nome</span><span class="sxs-lookup"><span data-stu-id="73625-104">Name</span></span>

<span data-ttu-id="73625-105">`dotnet tool uninstall` - Disinstalla lo [strumento globale .NET Core](global-tools.md) specificato dal computer.</span><span class="sxs-lookup"><span data-stu-id="73625-105">`dotnet tool uninstall` - Uninstalls the specified [.NET Core Global Tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="73625-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="73625-106">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="73625-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73625-107">Description</span></span>

<span data-ttu-id="73625-108">Il comando `dotnet tool uninstall` consente di disinstallare gli strumenti globali .NET Core dal computer.</span><span class="sxs-lookup"><span data-stu-id="73625-108">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core Global Tools from your machine.</span></span> <span data-ttu-id="73625-109">Per usare il comando, è necessario specificare che si vuole rimuovere uno strumento a livello utente con l'opzione `--global` oppure specificare un percorso in cui è installato lo strumento con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="73625-109">To use the command, you either have to specify that you want to remove a user-wide tool using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="73625-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="73625-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="73625-111">Nome/ID del pacchetto NuGet che contiene lo strumento globale .NET Core da disinstallare.</span><span class="sxs-lookup"><span data-stu-id="73625-111">Name/ID of the NuGet package that contains the .NET Core Global Tool to uninstall.</span></span> <span data-ttu-id="73625-112">È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="73625-112">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="73625-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="73625-113">Options</span></span>

`-g|--global`

<span data-ttu-id="73625-114">Specifica che lo strumento da rimuovere appartiene a un'installazione a livello utente.</span><span class="sxs-lookup"><span data-stu-id="73625-114">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="73625-115">Non può essere usata con l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="73625-115">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="73625-116">Se non si specifica questa opzione, è necessario specificare l'opzione `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="73625-116">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="73625-117">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="73625-117">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="73625-118">Specifica il percorso da cui disinstallare lo strumento globale.</span><span class="sxs-lookup"><span data-stu-id="73625-118">Specifies the location where to uninstall the Global Tool.</span></span> <span data-ttu-id="73625-119">Il valore di PATH può essere assoluto o relativo.</span><span class="sxs-lookup"><span data-stu-id="73625-119">PATH can be absolute or relative.</span></span> <span data-ttu-id="73625-120">Non può essere usata con l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="73625-120">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="73625-121">Se non si specifica questa opzione, è necessario specificare l'opzione `--global`.</span><span class="sxs-lookup"><span data-stu-id="73625-121">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="73625-122">Esempi</span><span class="sxs-lookup"><span data-stu-id="73625-122">Examples</span></span>

<span data-ttu-id="73625-123">Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/):</span><span class="sxs-lookup"><span data-stu-id="73625-123">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool uninstall -g dotnetsay`

<span data-ttu-id="73625-124">Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) da una cartella di Windows specifica:</span><span class="sxs-lookup"><span data-stu-id="73625-124">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Windows folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="73625-125">Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) da una cartella di Linux/macOS specifica:</span><span class="sxs-lookup"><span data-stu-id="73625-125">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Linux/macOS folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="73625-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73625-126">See also</span></span>

- [<span data-ttu-id="73625-127">Strumenti globali .NET Core</span><span class="sxs-lookup"><span data-stu-id="73625-127">.NET Core Global Tools</span></span>](global-tools.md)

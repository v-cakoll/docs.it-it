---
title: Comando di esecuzione dello strumento dotnet
description: Il comando dotnet tool run richiama uno strumento locale.
ms.date: 02/14/2020
ms.openlocfilehash: f79c239363e8b3abbd55c54dd1912443e6777fb7
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463319"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="f293a-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="f293a-103">dotnet tool run</span></span>

<span data-ttu-id="f293a-104">**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="f293a-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="f293a-105">Nome</span><span class="sxs-lookup"><span data-stu-id="f293a-105">Name</span></span>

<span data-ttu-id="f293a-106">`dotnet tool run`- Richiama uno strumento locale.- Invokes a local tool.</span><span class="sxs-lookup"><span data-stu-id="f293a-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f293a-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f293a-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run -h|--help
```

## <a name="description"></a><span data-ttu-id="f293a-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f293a-108">Description</span></span>

<span data-ttu-id="f293a-109">Il `dotnet tool run` comando cerca i file manifesto dello strumento che si trovano nell'ambito della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f293a-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="f293a-110">Quando trova un riferimento allo strumento specificato, esegue lo strumento.</span><span class="sxs-lookup"><span data-stu-id="f293a-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="f293a-111">Per ulteriori informazioni, consultate [Richiamare uno strumento locale.](global-tools.md#invoke-a-local-tool)</span><span class="sxs-lookup"><span data-stu-id="f293a-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="f293a-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f293a-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="f293a-113">Nome del comando dello strumento da eseguire.</span><span class="sxs-lookup"><span data-stu-id="f293a-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="f293a-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f293a-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="f293a-115">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="f293a-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="f293a-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="f293a-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="f293a-117">Esegue `dotnetsay` lo strumento locale.</span><span class="sxs-lookup"><span data-stu-id="f293a-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="f293a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f293a-118">See also</span></span>

- [<span data-ttu-id="f293a-119">Strumenti .NET Core</span><span class="sxs-lookup"><span data-stu-id="f293a-119">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="f293a-120">Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="f293a-120">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)

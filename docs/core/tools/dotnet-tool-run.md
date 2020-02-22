---
title: comando DotNet Tool Run
description: Il comando DotNet Tool Run richiama uno strumento locale.
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543880"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="9641f-103">esecuzione dello strumento DotNet</span><span class="sxs-lookup"><span data-stu-id="9641f-103">dotnet tool run</span></span>

<span data-ttu-id="9641f-104">**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="9641f-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9641f-105">Nome</span><span class="sxs-lookup"><span data-stu-id="9641f-105">Name</span></span>

<span data-ttu-id="9641f-106">`dotnet tool run`: richiama uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="9641f-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9641f-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="9641f-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME> 
dotnet tool run <-h|--help>
```

## <a name="description"></a><span data-ttu-id="9641f-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9641f-108">Description</span></span>

<span data-ttu-id="9641f-109">Il comando `dotnet tool run` Cerca i file manifesto degli strumenti che rientrano nell'ambito della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="9641f-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="9641f-110">Quando viene trovato un riferimento allo strumento specificato, viene eseguito lo strumento.</span><span class="sxs-lookup"><span data-stu-id="9641f-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="9641f-111">Per ulteriori informazioni, vedere [Invoke a local Tool](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="9641f-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="9641f-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9641f-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="9641f-113">Nome del comando dello strumento da eseguire.</span><span class="sxs-lookup"><span data-stu-id="9641f-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="9641f-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9641f-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="9641f-115">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="9641f-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="9641f-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="9641f-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="9641f-117">Esegue lo strumento locale `dotnetsay`.</span><span class="sxs-lookup"><span data-stu-id="9641f-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="9641f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9641f-118">See also</span></span>

- [<span data-ttu-id="9641f-119">Strumenti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="9641f-119">.NET Core tools</span></span>](global-tools.md)

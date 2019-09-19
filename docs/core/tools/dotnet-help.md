---
title: Comando dotnet help
description: Il comando dotnet help mostra documentazione online più dettagliata per il comando specificato.
ms.date: 08/08/2019
ms.openlocfilehash: 533f2c47fa7ec14d31368538092fec2490234820
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117722"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="5e8e8-103">riferimento dotnet help</span><span class="sxs-lookup"><span data-stu-id="5e8e8-103">dotnet help reference</span></span>

<span data-ttu-id="5e8e8-104">**Questo articolo si applica a: ✓** .net core 2,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="5e8e8-104">**This article applies to: ✓** .NET Core 2.0 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a><span data-ttu-id="5e8e8-105">nome</span><span class="sxs-lookup"><span data-stu-id="5e8e8-105">Name</span></span>

<span data-ttu-id="5e8e8-106">`dotnet help` - Mostra documentazione online più dettagliata per il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="5e8e8-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5e8e8-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5e8e8-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="5e8e8-108">Description</span><span class="sxs-lookup"><span data-stu-id="5e8e8-108">Description</span></span>

<span data-ttu-id="5e8e8-109">Il comando `dotnet help` apre la pagina di riferimento per ulteriori informazioni sul comando specificato in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5e8e8-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="5e8e8-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5e8e8-110">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="5e8e8-111">Nome del comando dell’interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5e8e8-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="5e8e8-112">Per un elenco dei comandi dell’interfaccia della riga di comando validi, vedere [i comandi CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="5e8e8-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="5e8e8-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5e8e8-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="5e8e8-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="5e8e8-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="5e8e8-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="5e8e8-115">Examples</span></span>

* <span data-ttu-id="5e8e8-116">Apre la pagina della documentazione per il comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="5e8e8-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```

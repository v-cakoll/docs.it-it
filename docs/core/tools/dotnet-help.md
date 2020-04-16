---
title: Comando dotnet help
description: Il comando dotnet help mostra documentazione online più dettagliata per il comando specificato.
ms.date: 02/14/2020
ms.openlocfilehash: a59e74a318118b6fd39d1895df02d76daa6fc9e1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463683"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="7d3a3-103">riferimento dotnet help</span><span class="sxs-lookup"><span data-stu-id="7d3a3-103">dotnet help reference</span></span>

<span data-ttu-id="7d3a3-104">**Questo articolo si applica a:** ✔️ .NET Core 2.0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="7d3a3-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="7d3a3-105">Nome</span><span class="sxs-lookup"><span data-stu-id="7d3a3-105">Name</span></span>

<span data-ttu-id="7d3a3-106">`dotnet help` - Mostra documentazione online più dettagliata per il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="7d3a3-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7d3a3-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7d3a3-107">Synopsis</span></span>

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="7d3a3-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d3a3-108">Description</span></span>

<span data-ttu-id="7d3a3-109">Il comando `dotnet help` apre la pagina di riferimento per ulteriori informazioni sul comando specificato in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7d3a3-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="7d3a3-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7d3a3-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="7d3a3-111">Nome del comando dell’interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7d3a3-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="7d3a3-112">Per un elenco dei comandi dell’interfaccia della riga di comando validi, vedere [i comandi CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="7d3a3-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="7d3a3-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7d3a3-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="7d3a3-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="7d3a3-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="7d3a3-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="7d3a3-115">Examples</span></span>

- <span data-ttu-id="7d3a3-116">Apre la pagina della documentazione per il comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="7d3a3-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```

---
title: Comando dotnet help
description: Il comando dotnet help mostra documentazione online più dettagliata per il comando specificato.
ms.date: 08/08/2019
ms.openlocfilehash: 9bb4e54d2634c000707752edf53b38af43c4344e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734242"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="eaf0b-103">riferimento dotnet help</span><span class="sxs-lookup"><span data-stu-id="eaf0b-103">dotnet help reference</span></span>

<span data-ttu-id="eaf0b-104">**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="eaf0b-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a><span data-ttu-id="eaf0b-105">Name</span><span class="sxs-lookup"><span data-stu-id="eaf0b-105">Name</span></span>

<span data-ttu-id="eaf0b-106">`dotnet help` - Mostra documentazione online più dettagliata per il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="eaf0b-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="eaf0b-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="eaf0b-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="eaf0b-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eaf0b-108">Description</span></span>

<span data-ttu-id="eaf0b-109">Il comando `dotnet help` apre la pagina di riferimento per ulteriori informazioni sul comando specificato in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="eaf0b-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="eaf0b-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="eaf0b-110">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="eaf0b-111">Nome del comando dell’interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="eaf0b-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="eaf0b-112">Per un elenco dei comandi dell’interfaccia della riga di comando validi, vedere [i comandi CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="eaf0b-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="eaf0b-113">Options</span><span class="sxs-lookup"><span data-stu-id="eaf0b-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="eaf0b-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="eaf0b-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="eaf0b-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="eaf0b-115">Examples</span></span>

* <span data-ttu-id="eaf0b-116">Apre la pagina della documentazione per il comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="eaf0b-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```

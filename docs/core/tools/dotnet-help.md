---
title: Comando dotnet help - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet help mostra documentazione online più dettagliata per il comando specificato.
ms.date: 12/04/2018
ms.openlocfilehash: 60d1cc706ca5c78fa3be877bd679888181213e88
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152175"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="7840d-103">riferimento dotnet help</span><span class="sxs-lookup"><span data-stu-id="7840d-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="7840d-104">nome</span><span class="sxs-lookup"><span data-stu-id="7840d-104">Name</span></span>

<span data-ttu-id="7840d-105">`dotnet help` - Mostra documentazione online più dettagliata per il comando specificato.</span><span class="sxs-lookup"><span data-stu-id="7840d-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7840d-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="7840d-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="7840d-107">Description</span><span class="sxs-lookup"><span data-stu-id="7840d-107">Description</span></span>

<span data-ttu-id="7840d-108">Il comando `dotnet help` apre la pagina di riferimento per ulteriori informazioni sul comando specificato in docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7840d-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="7840d-109">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7840d-109">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="7840d-110">Nome del comando dell’interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7840d-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="7840d-111">Per un elenco dei comandi dell’interfaccia della riga di comando validi, vedere [i comandi CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="7840d-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="7840d-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7840d-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="7840d-113">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="7840d-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="7840d-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="7840d-114">Examples</span></span>

* <span data-ttu-id="7840d-115">Apre la pagina della documentazione per il comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="7840d-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```
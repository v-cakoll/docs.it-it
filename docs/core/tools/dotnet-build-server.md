---
title: Comando dotnet build-server
description: Il comando dotnet build-server interagisce con i server avviati da una compilazione.
ms.date: 04/24/2019
ms.openlocfilehash: 89d1aba104e2cb07b46766a3768eed68d85a7aa7
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117774"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="3cb8f-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="3cb8f-103">dotnet build-server</span></span>

<span data-ttu-id="3cb8f-104">**Questo articolo si applica a: ✓** .NET Core 2.1.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="3cb8f-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="3cb8f-105">nome</span><span class="sxs-lookup"><span data-stu-id="3cb8f-105">Name</span></span>

<span data-ttu-id="3cb8f-106">`dotnet build-server`: interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="3cb8f-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3cb8f-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3cb8f-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="3cb8f-108">Comandi:</span><span class="sxs-lookup"><span data-stu-id="3cb8f-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="3cb8f-109">Arresta i server di compilazione avviati da dotnet.</span><span class="sxs-lookup"><span data-stu-id="3cb8f-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="3cb8f-110">Per impostazione predefinita, vengono arrestati tutti i server.</span><span class="sxs-lookup"><span data-stu-id="3cb8f-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="3cb8f-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3cb8f-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="3cb8f-112">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="3cb8f-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="3cb8f-113">Arresta il server di compilazione MSBuild.</span><span class="sxs-lookup"><span data-stu-id="3cb8f-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="3cb8f-114">Arresta il server di compilazione Razor.</span><span class="sxs-lookup"><span data-stu-id="3cb8f-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="3cb8f-115">Arresta il server di compilazione del compilatore VB/C#.</span><span class="sxs-lookup"><span data-stu-id="3cb8f-115">Shuts down the VB/C# compiler build server.</span></span>

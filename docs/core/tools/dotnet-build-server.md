---
title: Comando dotnet build-server
description: Il comando dotnet build-server interagisce con i server avviati da una compilazione.
ms.date: 12/04/2018
ms.openlocfilehash: 7f78a0cae6e3297f3084754dc56b0da4eac38caf
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169658"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="de486-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="de486-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="de486-104">nome</span><span class="sxs-lookup"><span data-stu-id="de486-104">Name</span></span>

<span data-ttu-id="de486-105">`dotnet build-server`: interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="de486-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="de486-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="de486-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="de486-107">Comandi:</span><span class="sxs-lookup"><span data-stu-id="de486-107">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="de486-108">Arresta i server di compilazione avviati da dotnet.</span><span class="sxs-lookup"><span data-stu-id="de486-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="de486-109">Per impostazione predefinita, vengono arrestati tutti i server.</span><span class="sxs-lookup"><span data-stu-id="de486-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="de486-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="de486-110">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="de486-111">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="de486-111">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="de486-112">Arresta il server di compilazione MSBuild.</span><span class="sxs-lookup"><span data-stu-id="de486-112">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="de486-113">Arresta il server di compilazione Razor.</span><span class="sxs-lookup"><span data-stu-id="de486-113">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="de486-114">Arresta il server di compilazione del compilatore VB/C#.</span><span class="sxs-lookup"><span data-stu-id="de486-114">Shuts down the VB/C# compiler build server.</span></span>
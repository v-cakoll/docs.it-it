---
title: Comando dotnet build-server - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet build-server interagisce con i server avviati da una compilazione.
ms.date: 12/04/2018
ms.openlocfilehash: 2746ade12cc819089258483e84a8c0f02a64c755
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125678"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="89e2e-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="89e2e-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="89e2e-104">nome</span><span class="sxs-lookup"><span data-stu-id="89e2e-104">Name</span></span>

<span data-ttu-id="89e2e-105">`dotnet build-server`: interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="89e2e-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="89e2e-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="89e2e-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="89e2e-107">Comandi:</span><span class="sxs-lookup"><span data-stu-id="89e2e-107">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="89e2e-108">Arresta i server di compilazione avviati da dotnet.</span><span class="sxs-lookup"><span data-stu-id="89e2e-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="89e2e-109">Per impostazione predefinita, vengono arrestati tutti i server.</span><span class="sxs-lookup"><span data-stu-id="89e2e-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="89e2e-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="89e2e-110">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="89e2e-111">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="89e2e-111">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="89e2e-112">Arresta il server di compilazione MSBuild.</span><span class="sxs-lookup"><span data-stu-id="89e2e-112">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="89e2e-113">Arresta il server di compilazione Razor.</span><span class="sxs-lookup"><span data-stu-id="89e2e-113">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="89e2e-114">Arresta il server di compilazione del compilatore VB/C#.</span><span class="sxs-lookup"><span data-stu-id="89e2e-114">Shuts down the VB/C# compiler build server.</span></span>
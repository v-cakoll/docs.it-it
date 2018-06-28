---
title: Comando dotnet build-server - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet build-server interagisce con i server avviati da una compilazione.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 929b8d74aa5f3f0ad73b108be8a5bf22f86e30d6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696254"
---
# <a name="dotnet-build"></a><span data-ttu-id="bfac4-103">dotnet-build</span><span class="sxs-lookup"><span data-stu-id="bfac4-103">dotnet-build</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="bfac4-104">nome</span><span class="sxs-lookup"><span data-stu-id="bfac4-104">Name</span></span>

<span data-ttu-id="bfac4-105">`dotnet build-server`: interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="bfac4-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="bfac4-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="bfac4-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="bfac4-107">Comandi:</span><span class="sxs-lookup"><span data-stu-id="bfac4-107">Commands</span></span>

`shutdown`

<span data-ttu-id="bfac4-108">Arresta i server di compilazione avviati da dotnet.</span><span class="sxs-lookup"><span data-stu-id="bfac4-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="bfac4-109">Per impostazione predefinita, vengono arrestati tutti i server.</span><span class="sxs-lookup"><span data-stu-id="bfac4-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="bfac4-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="bfac4-110">Options</span></span>

`-h|--help`

<span data-ttu-id="bfac4-111">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="bfac4-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="bfac4-112">Arresta il server di compilazione MSBuild.</span><span class="sxs-lookup"><span data-stu-id="bfac4-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="bfac4-113">Arresta il server di compilazione Razor.</span><span class="sxs-lookup"><span data-stu-id="bfac4-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="bfac4-114">Arresta il server di compilazione del compilatore VB/C#.</span><span class="sxs-lookup"><span data-stu-id="bfac4-114">Shuts down the VB/C# compiler build server.</span></span>

---
title: Comando dotnet build-server - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet build-server interagisce con i server avviati da una compilazione.
author: mairaw
ms.author: mairaw
ms.date: 07/02/2018
ms.openlocfilehash: 1c59c85f246b79c7e2552f704db5b4f076f9b502
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404333"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="71687-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="71687-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="71687-104">nome</span><span class="sxs-lookup"><span data-stu-id="71687-104">Name</span></span>

<span data-ttu-id="71687-105">`dotnet build-server`: interagisce con i server avviati da una compilazione.</span><span class="sxs-lookup"><span data-stu-id="71687-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="71687-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="71687-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="71687-107">Comandi:</span><span class="sxs-lookup"><span data-stu-id="71687-107">Commands</span></span>

`shutdown`

<span data-ttu-id="71687-108">Arresta i server di compilazione avviati da dotnet.</span><span class="sxs-lookup"><span data-stu-id="71687-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="71687-109">Per impostazione predefinita, vengono arrestati tutti i server.</span><span class="sxs-lookup"><span data-stu-id="71687-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="71687-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="71687-110">Options</span></span>

`-h|--help`

<span data-ttu-id="71687-111">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="71687-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="71687-112">Arresta il server di compilazione MSBuild.</span><span class="sxs-lookup"><span data-stu-id="71687-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="71687-113">Arresta il server di compilazione Razor.</span><span class="sxs-lookup"><span data-stu-id="71687-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="71687-114">Arresta il server di compilazione del compilatore VB/C#.</span><span class="sxs-lookup"><span data-stu-id="71687-114">Shuts down the VB/C# compiler build server.</span></span>

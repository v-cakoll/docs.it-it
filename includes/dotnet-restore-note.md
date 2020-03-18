---
ms.openlocfilehash: 975edd1bda507b46da353db788d9730560f9b573
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "65632125"
---
> [!NOTE]
> <span data-ttu-id="8c841-101">A partire da .NET Core 2.0 SDK, [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) non è necessario eseguire perché viene eseguito in modo `dotnet new` `dotnet build` implicito da tutti i comandi che richiedono il ripristino, ad esempio , e `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="8c841-101">Starting with .NET Core 2.0 SDK, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build` and `dotnet run`.</span></span>
> <span data-ttu-id="8c841-102">È ancora un comando valido in alcuni scenari in cui ha senso eseguire un ripristino esplicito, ad esempio le [compilazioni di integrazione continua in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) o in sistemi di compilazione che richiedono il controllo esplicito del momento in cui viene eseguito il ripristino.</span><span class="sxs-lookup"><span data-stu-id="8c841-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>

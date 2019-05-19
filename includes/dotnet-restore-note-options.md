---
ms.openlocfilehash: 497ac09e5c9a10470d3ae1932d7e3dc114d121dd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632006"
---
> [!NOTE]
> <span data-ttu-id="9a4fe-101">A partire da .NET Core 2.0, non è necessario eseguire [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) perché viene eseguito in modo implicito da tutti i comandi, ad esempio `dotnet build` e `dotnet run`, che richiedono un ripristino.</span><span class="sxs-lookup"><span data-stu-id="9a4fe-101">Starting with .NET Core 2.0, you don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands, such as `dotnet build` and `dotnet run`, that require a restore to occur.</span></span> <span data-ttu-id="9a4fe-102">È ancora un comando valido in alcuni scenari in cui ha senso eseguire un ripristino esplicito, ad esempio le [compilazioni di integrazione continua in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o in sistemi di compilazione che richiedono il controllo esplicito del momento in cui viene eseguito il ripristino.</span><span class="sxs-lookup"><span data-stu-id="9a4fe-102">It's still a valid command in certain scenarios where doing an explicit restore makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control the time at which the restore occurs.</span></span>
>
> <span data-ttu-id="9a4fe-103">Questo comando supporta anche le opzioni `dotnet restore` passate nel formato lungo (ad esempio, `--source`).</span><span class="sxs-lookup"><span data-stu-id="9a4fe-103">This command also supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="9a4fe-104">Le opzioni in formato breve, come `-s`, non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="9a4fe-104">Short form options, such as `-s`, are not supported.</span></span>

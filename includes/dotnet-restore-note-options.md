---
ms.openlocfilehash: 6c04437c2a211b244e6c5eda0893b267c59668e9
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102769"
---
<span data-ttu-id="58124-101">Non è necessario eseguire [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) perché viene eseguito in modo implicito da tutti `dotnet new`i `dotnet build` `dotnet run`comandi `dotnet test` `dotnet publish`che `dotnet pack`richiedono il ripristino, ad esempio , , , , e .</span><span class="sxs-lookup"><span data-stu-id="58124-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="58124-102">Per disabilitare il `--no-restore` ripristino implicito, utilizzare l'opzione .</span><span class="sxs-lookup"><span data-stu-id="58124-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="58124-103">Il `dotnet restore` comando è comunque utile in alcuni scenari in cui il ripristino esplicito ha senso, ad esempio le compilazioni di [integrazione continua nei servizi DevOps](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) di Azure o nei sistemi di compilazione che devono controllare in modo esplicito quando si verifica il ripristino.</span><span class="sxs-lookup"><span data-stu-id="58124-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="58124-104">Per informazioni su come gestire i feed NuGet, vedere la [ `dotnet restore` documentazione](../docs/core/tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="58124-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>

<span data-ttu-id="58124-105">Questo comando supporta `dotnet restore` le opzioni quando vengono passate `--source`nel formato lungo , ad esempio ).</span><span class="sxs-lookup"><span data-stu-id="58124-105">This command supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="58124-106">Le opzioni in formato breve, come `-s`, non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="58124-106">Short form options, such as `-s`, are not supported.</span></span>

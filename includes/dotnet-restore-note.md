---
ms.openlocfilehash: e140b375f4f289df895052aa093f03f381d62488
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102742"
---
<span data-ttu-id="e4b20-101">Non è necessario eseguire [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) perché viene eseguito in modo implicito da tutti i comandi che richiedono un ripristino, ad esempio `dotnet new` ,, `dotnet build` `dotnet run` , `dotnet test` , `dotnet publish` e `dotnet pack` .</span><span class="sxs-lookup"><span data-stu-id="e4b20-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="e4b20-102">Per disabilitare il ripristino implicito, usare l' `--no-restore` opzione.</span><span class="sxs-lookup"><span data-stu-id="e4b20-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="e4b20-103">Il `dotnet restore` comando è ancora utile in alcuni scenari in cui il ripristino esplicito è significativo, ad esempio le [compilazioni di integrazione continua in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) o nei sistemi di compilazione che devono controllare in modo esplicito quando si verifica il ripristino.</span><span class="sxs-lookup"><span data-stu-id="e4b20-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="e4b20-104">Per informazioni su come gestire i feed NuGet, vedere la [ `dotnet restore` documentazione](../docs/core/tools/dotnet-restore.md)di.</span><span class="sxs-lookup"><span data-stu-id="e4b20-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>

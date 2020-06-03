---
ms.openlocfilehash: e140b375f4f289df895052aa093f03f381d62488
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102742"
---
Non è necessario eseguire [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) perché viene eseguito in modo implicito da tutti i comandi che richiedono un ripristino, ad esempio `dotnet new` ,, `dotnet build` `dotnet run` , `dotnet test` , `dotnet publish` e `dotnet pack` . Per disabilitare il ripristino implicito, usare l' `--no-restore` opzione.

Il `dotnet restore` comando è ancora utile in alcuni scenari in cui il ripristino esplicito è significativo, ad esempio le [compilazioni di integrazione continua in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) o nei sistemi di compilazione che devono controllare in modo esplicito quando si verifica il ripristino.

Per informazioni su come gestire i feed NuGet, vedere la [ `dotnet restore` documentazione](../docs/core/tools/dotnet-restore.md)di.

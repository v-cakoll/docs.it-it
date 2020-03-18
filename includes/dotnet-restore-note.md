---
ms.openlocfilehash: 975edd1bda507b46da353db788d9730560f9b573
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "65632125"
---
> [!NOTE]
> A partire da .NET Core 2.0 SDK, [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) non è necessario eseguire perché viene eseguito in modo `dotnet new` `dotnet build` implicito da tutti i comandi che richiedono il ripristino, ad esempio , e `dotnet run`.
> È ancora un comando valido in alcuni scenari in cui ha senso eseguire un ripristino esplicito, ad esempio le [compilazioni di integrazione continua in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) o in sistemi di compilazione che richiedono il controllo esplicito del momento in cui viene eseguito il ripristino.

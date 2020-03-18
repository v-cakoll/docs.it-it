---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72179968"
---
> [!NOTE]
> A partire da .NET Core 2.0, [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) non è necessario eseguire perché viene eseguito in modo `dotnet build` implicito da tutti i comandi che richiedono un ripristino, ad esempio e `dotnet run`. È ancora un comando valido in alcuni scenari in cui ha senso eseguire un ripristino esplicito, ad esempio le [compilazioni di integrazione continua in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o in sistemi di compilazione che richiedono il controllo esplicito del momento in cui viene eseguito il ripristino.
>
> Questo comando supporta anche le opzioni `dotnet restore` passate nel formato lungo (ad esempio, `--source`). Le opzioni in formato breve, come `-s`, non sono supportate.

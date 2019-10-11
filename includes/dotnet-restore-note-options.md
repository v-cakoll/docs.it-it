---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179968"
---
> [!NOTE]
> A partire da .NET Core 2,0, non è necessario eseguire [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) perché viene eseguito in modo implicito da tutti i comandi che richiedono un ripristino, ad esempio `dotnet build` e `dotnet run`. È ancora un comando valido in alcuni scenari in cui ha senso eseguire un ripristino esplicito, ad esempio le [compilazioni di integrazione continua in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o in sistemi di compilazione che richiedono il controllo esplicito del momento in cui viene eseguito il ripristino.
>
> Questo comando supporta anche le opzioni `dotnet restore` passate nel formato lungo (ad esempio, `--source`). Le opzioni in formato breve, come `-s`, non sono supportate.

---
ms.openlocfilehash: 6c04437c2a211b244e6c5eda0893b267c59668e9
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102769"
---
Non è necessario eseguire [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) perché viene eseguito in modo implicito da tutti `dotnet new`i `dotnet build` `dotnet run`comandi `dotnet test` `dotnet publish`che `dotnet pack`richiedono il ripristino, ad esempio , , , , e . Per disabilitare il `--no-restore` ripristino implicito, utilizzare l'opzione .

Il `dotnet restore` comando è comunque utile in alcuni scenari in cui il ripristino esplicito ha senso, ad esempio le compilazioni di [integrazione continua nei servizi DevOps](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) di Azure o nei sistemi di compilazione che devono controllare in modo esplicito quando si verifica il ripristino.

Per informazioni su come gestire i feed NuGet, vedere la [ `dotnet restore` documentazione](../docs/core/tools/dotnet-restore.md).

Questo comando supporta `dotnet restore` le opzioni quando vengono passate `--source`nel formato lungo , ad esempio ). Le opzioni in formato breve, come `-s`, non sono supportate.

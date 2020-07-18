---
title: Interfaccia della riga di comando di .NET Core
titleSuffix: ''
description: Panoramica del interfaccia della riga di comando di .NET Core e delle relative funzionalità.
ms.date: 02/13/2020
ms.openlocfilehash: f92151c85b4816fef1859e84ad94945445db1854
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86415970"
---
# <a name="net-core-cli-overview"></a>Panoramica dell'interfaccia della riga di comando di .NET Core

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

L'interfaccia della riga di comando di .NET Core è una serie di procedure multipiattaforma per lo sviluppo, la compilazione, l'esecuzione e la pubblicazione di applicazioni .NET Core.

Il interfaccia della riga di comando di .NET Core è incluso nel [.NET Core SDK](../sdk.md). Per informazioni su come installare il .NET Core SDK, vedere [installare .NET Core](../install/windows.md).

## <a name="cli-commands"></a>Comandi dell'interfaccia della riga di comando

Per impostazione predefinita vengono installati i comandi seguenti:

### <a name="basic-commands"></a>Comandi di base

- [`new`](dotnet-new.md)
- [`restore`](dotnet-restore.md)
- [`build`](dotnet-build.md)
- [`publish`](dotnet-publish.md)
- [`run`](dotnet-run.md)
- [`test`](dotnet-test.md)
- [`vstest`](dotnet-vstest.md)
- [`pack`](dotnet-pack.md)
- [`migrate`](dotnet-migrate.md)
- [`clean`](dotnet-clean.md)
- [`sln`](dotnet-sln.md)
- [`help`](dotnet-help.md)
- [`store`](dotnet-store.md)

### <a name="project-modification-commands"></a>Comandi di modifica dei progetti

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a>Comandi avanzati

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a>Comandi di gestione degli strumenti

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- [`tool restore`](global-tools.md#install-a-local-tool)Disponibile a partire da .NET Core SDK 3,0.
- [`tool run`](global-tools.md#invoke-a-local-tool)Disponibile a partire da .NET Core SDK 3,0.
- [`tool uninstall`](dotnet-tool-uninstall.md)

Gli strumenti sono applicazioni console installate da pacchetti NuGet e vengono richiamate dal prompt dei comandi. È possibile scrivere strumenti manualmente oppure installare gli strumenti scritti da terze parti. Gli strumenti sono noti anche come strumenti globali, strumenti per percorsi di strumenti e strumenti locali. Per altre informazioni, vedere [Cenni preliminari sugli strumenti di .NET Core](global-tools.md).

## <a name="command-structure"></a>Struttura dei comandi

La struttura dei comandi dell'interfaccia della riga di comando è composta dal [driver ("dotnet")](#driver), dal [comando](#command) e, in alcuni casi, dagli [argomenti](#arguments) e dalle [opzioni](#options). Questo modello può essere osservato nella maggior parte delle operazioni eseguite dalla riga di comando, inclusa la creazione di una nuova app console e la relativa esecuzione dalla riga di comando, come illustrato dai comandi seguenti quando vengono eseguiti da una directory denominata *my_app*:

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a>Driver

Il driver, denominato [dotnet](dotnet.md), ha due compiti: eseguire un'[app dipendente dal framework](../deploying/index.md) ed eseguire un comando.

Per eseguire un'applicazione dipendente dal framework, specificare l'app dopo il driver, ad esempio `dotnet /path/to/my_app.dll`. Se si esegue il comando dalla cartella in cui si trova la DLL dell'app, è sufficiente eseguire `dotnet my_app.dll`. Se si vuole usare una versione specifica del runtime .NET Core, usare l'opzione `--fx-version <VERSION>` (vedere il riferimento per il [comando dotnet](dotnet.md)).

Nel momento in cui si fornisce un comando al driver, `dotnet.exe` avvia il processo di esecuzione del comando dell'interfaccia della riga di comando. Ad esempio:

```dotnetcli
dotnet build
```

Come prima operazione, il driver determina la versione dell'SDK da usare. Se non è presente alcun [global.jsnel](global-json.md) file, viene usata la versione più recente dell'SDK disponibile. Può essere una versione di anteprima o una versione stabile, a seconda di qual è la più recente disponibile nel computer.  Dopo aver determinato la versione del SDK il driver esegue il comando.

### <a name="command"></a>Comando

Il comando esegue un'azione. Ad esempio, `dotnet build` compila il codice. `dotnet publish` pubblica il codice. I comandi vengono implementati come un'applicazione console usando una convenzione `dotnet {command}`.

### <a name="arguments"></a>Argomenti

Gli argomenti passati alla riga di comando sono gli argomenti per il comando richiamato. Ad esempio, quando si esegue `dotnet publish my_app.csproj` , l' `my_app.csproj` argomento indica il progetto da pubblicare e viene passato al `publish` comando.

### <a name="options"></a>Opzioni

Le opzioni passate alla riga di comando sono le opzioni per il comando richiamato. Ad esempio, quando si esegue `dotnet publish --output /build_output` , l' `--output` opzione e il relativo valore vengono passati al `publish` comando.

## <a name="see-also"></a>Vedere anche

- [repository GitHub DotNet/SDK](https://github.com/dotnet/sdk/)
- [.NET Core installation guide](../install/windows.md) (Guida all'installazione di .NET Core)

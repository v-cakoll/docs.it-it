---
title: Interfaccia della riga di comando di .NET Core
titleSuffix: ''
description: Panoramica dell'interfaccia della riga di comando di .NET Core e delle relative funzionalità.
ms.date: 02/13/2020
ms.openlocfilehash: 45a40063f70a621e807abf5e01ceecb125aecd7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79399119"
---
# <a name="net-core-cli-overview"></a>Panoramica dell'interfaccia della riga di comando di .NET Core

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

L'interfaccia della riga di comando (CLI) di .NET Core è una catena di strumenti multipiattaforma per lo sviluppo, la compilazione, l'esecuzione e la pubblicazione di applicazioni .NET Core.

L'interfaccia della riga di comando di .NET Core è inclusa in [.NET Core SDK.](../sdk.md) Per informazioni su come installare .NET Core SDK, vedere [Installare .NET Core SDK](../install/sdk.md).

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
- [`tool restore`](global-tools.md#install-a-local-tool)Disponibile da .NET Core SDK 3.0.
- [`tool run`](global-tools.md#invoke-a-local-tool)Disponibile da .NET Core SDK 3.0.
- [`tool uninstall`](dotnet-tool-uninstall.md)

Gli strumenti sono applicazioni console installate da pacchetti NuGet e richiamate dal prompt dei comandi. È possibile scrivere strumenti da soli o installare strumenti scritti da terze parti. Gli strumenti sono noti anche come strumenti globali, strumenti per il percorso degli strumenti e strumenti locali. Per ulteriori informazioni, vedere [Panoramica degli strumenti .NET Core](global-tools.md).

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

Come prima operazione, il driver determina la versione dell'SDK da usare. Se non è presente alcun file [global.json,](global-json.md) viene utilizzata la versione più recente dell'SDK. Può essere una versione di anteprima o una versione stabile, a seconda di qual è la più recente disponibile nel computer.  Dopo aver determinato la versione del SDK il driver esegue il comando.

### <a name="command"></a>Comando

Il comando esegue un'azione. Ad esempio, `dotnet build` compila il codice. `dotnet publish` pubblica il codice. I comandi vengono implementati come un'applicazione console usando una convenzione `dotnet {command}`.

### <a name="arguments"></a>Argomenti

Gli argomenti passati alla riga di comando sono gli argomenti per il comando richiamato. Quando si esegue `dotnet publish my_app.csproj`, ad esempio, l'argomento `my_app.csproj` indica il progetto da pubblicare e viene passato al comando `publish`.

### <a name="options"></a>Opzioni

Le opzioni passate alla riga di comando sono le opzioni per il comando richiamato. Quando si esegue `dotnet publish --output /build_output`, ad esempio, l'opzione `--output` e il relativo valore vengono passati al comando `publish`.

## <a name="see-also"></a>Vedere anche

- [repository GitHub dotnet/sdk](https://github.com/dotnet/sdk/)
- [.NET Core installation guide](../install/sdk.md) (Guida all'installazione di .NET Core)

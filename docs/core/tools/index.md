---
title: Interfaccia della riga di comando di .NET Core
titleSuffix: ''
description: Panoramica del interfaccia della riga di comando di .NET Core e delle relative funzionalità.
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920488"
---
# <a name="net-core-cli-overview"></a>Panoramica di interfaccia della riga di comando di .NET Core

L'interfaccia della riga di comando di .NET Core è una serie di procedure multipiattaforma per lo sviluppo, la compilazione, l'esecuzione e la pubblicazione di applicazioni .NET Core.

Il interfaccia della riga di comando di .NET Core è incluso nel [.NET Core SDK](../sdk.md). Per informazioni su come installare il .NET Core SDK, vedere [Install the .NET Core SDK](../install/sdk.md).

## <a name="cli-commands"></a>Comandi dell'interfaccia della riga di comando

Per impostazione predefinita vengono installati i comandi seguenti:

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Comandi di base**

- [new](dotnet-new.md)
- [restore](dotnet-restore.md)
- [build](dotnet-build.md)
- [publish](dotnet-publish.md)
- [run](dotnet-run.md)
- [test](dotnet-test.md)
- [vstest](dotnet-vstest.md)
- [pack](dotnet-pack.md)
- [migrate](dotnet-migrate.md)
- [clean](dotnet-clean.md)
- [sln](dotnet-sln.md)
- [help](dotnet-help.md)
- [store](dotnet-store.md)

**Comandi per la modifica dei progetti**

- [add package](dotnet-add-package.md)
- [add reference](dotnet-add-reference.md)
- [remove package](dotnet-remove-package.md)
- [remove reference](dotnet-remove-reference.md)
- [list reference](dotnet-list-reference.md)

**Comandi avanzati**

- [nuget delete](dotnet-nuget-delete.md)
- [nuget locals](dotnet-nuget-locals.md)
- [nuget push](dotnet-nuget-push.md)
- [msbuild](dotnet-msbuild.md)
- [dotnet install script](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Comandi di base**

- [new](dotnet-new.md)
- [restore](dotnet-restore.md)
- [build](dotnet-build.md)
- [publish](dotnet-publish.md)
- [run](dotnet-run.md)
- [test](dotnet-test.md)
- [vstest](dotnet-vstest.md)
- [pack](dotnet-pack.md)
- [migrate](dotnet-migrate.md)
- [clean](dotnet-clean.md)
- [sln](dotnet-sln.md)

**Comandi per la modifica dei progetti**

- [add package](dotnet-add-package.md)
- [add reference](dotnet-add-reference.md)
- [remove package](dotnet-remove-package.md)
- [remove reference](dotnet-remove-reference.md)
- [list reference](dotnet-list-reference.md)

**Comandi avanzati**

- [nuget delete](dotnet-nuget-delete.md)
- [nuget locals](dotnet-nuget-locals.md)
- [nuget push](dotnet-nuget-push.md)
- [msbuild](dotnet-msbuild.md)
- [dotnet install script](dotnet-install-script.md)

---

L'interfaccia della riga di comando adotta un modello di estendibilità che consente di specificare altri strumenti per i progetti. Per altre informazioni, vedere l'argomento [Modello di estendibilità dell'interfaccia della riga di comando di .NET Core](extensibility.md).

## <a name="command-structure"></a>Struttura dei comandi

La struttura dei comandi dell'interfaccia della riga di comando è composta dal [driver ("dotnet")](#driver), dal [comando](#command) e, in alcuni casi, dagli [argomenti](#arguments) e dalle [opzioni](#options). Questo modello può essere osservato nella maggior parte delle operazioni eseguite dalla riga di comando, inclusa la creazione di una nuova app console e la relativa esecuzione dalla riga di comando, come illustrato dai comandi seguenti quando vengono eseguiti da una directory denominata *my_app*:

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a>Driver

Il driver, denominato [dotnet](dotnet.md), ha due compiti: eseguire un'[app dipendente dal framework](../deploying/index.md) ed eseguire un comando. 

Per eseguire un'applicazione dipendente dal framework, specificare l'app dopo il driver, ad esempio `dotnet /path/to/my_app.dll`. Se si esegue il comando dalla cartella in cui si trova la DLL dell'app, è sufficiente eseguire `dotnet my_app.dll`. Se si vuole usare una versione specifica del runtime .NET Core, usare l'opzione `--fx-version <VERSION>` (vedere il riferimento per il [comando dotnet](dotnet.md)).

Nel momento in cui si fornisce un comando al driver, `dotnet.exe` avvia il processo di esecuzione del comando dell'interfaccia della riga di comando. Ad esempio:

```dotnetcli
dotnet build
```

Come prima operazione, il driver determina la versione dell'SDK da usare. Se non è presente nessuna voce ['global.json'](global-json.md) viene usata la versione più recente disponibile del SDK. Può essere una versione di anteprima o una versione stabile, a seconda di qual è la più recente disponibile nel computer.  Dopo aver determinato la versione del SDK il driver esegue il comando.

### <a name="command"></a>Comando

Il comando esegue un'azione. Ad esempio, `dotnet build` compila il codice. `dotnet publish` pubblica il codice. I comandi vengono implementati come un'applicazione console usando una convenzione `dotnet {command}`.

### <a name="arguments"></a>Argomenti

Gli argomenti passati alla riga di comando sono gli argomenti per il comando richiamato. Quando si esegue `dotnet publish my_app.csproj`, ad esempio, l'argomento `my_app.csproj` indica il progetto da pubblicare e viene passato al comando `publish`.

### <a name="options"></a>Options

Le opzioni passate alla riga di comando sono le opzioni per il comando richiamato. Quando si esegue `dotnet publish --output /build_output`, ad esempio, l'opzione `--output` e il relativo valore vengono passati al comando `publish`.

## <a name="migration-from-projectjson"></a>Migrazione da project.json

Se si sono usati gli strumenti della Preview 2 per generare progetti basati su *project.json*, consultare l'argomento [dotnet migrate](dotnet-migrate.md) per informazioni sulla migrazione del progetto in MSBuild/ *.csproj* per l'uso con gli strumenti di rilascio. Per i progetti .NET Core creati prima del rilascio degli strumenti della Preview 2, aggiornare manualmente il progetto seguendo le istruzioni disponibili in [Migrazione da DNX all'interfaccia della riga di comando di .NET Core (project.json)](../migration/from-dnx.md) e usare `dotnet migrate` o aggiornare direttamente i progetti.

## <a name="see-also"></a>Vedere anche

- [repository GitHub DotNet/SDK](https://github.com/dotnet/sdk/)
- [.NET Core installation guide](https://aka.ms/dotnetcoregs) (Guida all'installazione di .NET Core)

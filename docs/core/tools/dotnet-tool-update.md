---
title: Comando dotnet tool update
description: Il comando DotNet Tool Update aggiorna lo strumento .NET Core specificato nel computer.
ms.date: 07/08/2020
ms.openlocfilehash: 7c4bde44ac9964828074baeb1a697ba64ed17887
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226621"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool update`: Aggiorna lo [strumento .NET Core](global-tools.md) specificato nel computer.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet tool update` comando fornisce un modo per aggiornare gli strumenti di .NET Core nel computer alla versione stabile più recente del pacchetto. Il comando disinstalla e reinstalla uno strumento aggiornandolo. Per utilizzare il comando, è necessario specificare una delle opzioni seguenti:

* Per aggiornare uno strumento globale che è stato installato nel percorso predefinito, usare l' `--global` opzione
* Per aggiornare uno strumento globale installato in un percorso personalizzato, utilizzare l' `--tool-path` opzione.
* Per aggiornare uno strumento locale, utilizzare l' `--local` opzione.

**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**

## <a name="arguments"></a>Argomenti

- **`PACKAGE_ID`**

  Nome/ID del pacchetto NuGet che contiene lo strumento globale .NET Core da aggiornare. È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Opzioni

- **`--add-source <SOURCE>`**

  Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.

- **`--configfile <FILE>`**

  File di configurazione NuGet (*nuget.config*) da usare.

- **`--disable-parallel`**

  Impedisci il ripristino di più progetti in parallelo.

- **`--framework <FRAMEWORK>`**

  Specifica il [framework di destinazione](../../standard/frameworks.md) per cui aggiornare lo strumento.

- **`--ignore-failed-sources`**

  Considera gli errori di origine del pacchetto come avvisi.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).

- **`--local`**

  Aggiornare lo strumento e il manifesto dello strumento locale. Non può essere usata con l'opzione `--global`.

- **`--no-cache`**

  Non memorizzare nella cache pacchetti e richieste HTTP.

- **`--tool-manifest <PATH>`**

  Percorso del file manifesto.

- **`--tool-path <PATH>`**

  Specifica il percorso in cui è installato lo strumento globale. Il valore di PATH può essere assoluto o relativo. Non può essere usata con l'opzione `--global`. `--global`Se si omette e `--tool-path` si specifica che lo strumento da aggiornare è uno strumento locale.

- **`--version <VERSION>`**

  Intervallo di versioni del pacchetto di strumenti in cui eseguire l'aggiornamento. Questa operazione non può essere usata per eseguire il downgrade delle versioni. è necessario `uninstall` prima di tutto le versioni più recenti.

- **`-g|--global`**

  Specifica che l'aggiornamento è per uno strumento a livello utente. Non può essere usata con l'opzione `--tool-path`. `--global`Se si omette e `--tool-path` si specifica che lo strumento da aggiornare è uno strumento locale.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

## <a name="examples"></a>Esempi

- **`dotnet tool update -g dotnetsay`**

  Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) .

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) che si trova in una directory di Windows specifica.

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) che si trova in una directory Linux/MacOS specifica.

- **`dotnet tool update dotnetsay`**

  Aggiorna lo strumento locale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) installato per la directory corrente.

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) alla versione più recente della patch, con una versione principale di `2` e una versione secondaria di `0` .

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  Aggiorna lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) alla versione più bassa nell'intervallo specificato `(> 2.0.0 && < 2.1.4)` `2.1.0` . verrà installata la versione. Per altre informazioni sugli intervalli di controllo delle versioni semantico, vedere [intervalli di versione del pacchetto NuGet](/nuget/concepts/package-versioning#version-ranges).

## <a name="see-also"></a>Vedere anche

- [Strumenti di .NET Core](global-tools.md)
- [Versionamento Semantico](https://semver.org)
- [Esercitazione: installare e usare uno strumento globale .NET Core usando il interfaccia della riga di comando di .NET Core](global-tools-how-to-use.md)
- [Esercitazione: installare e usare uno strumento locale di .NET Core usando il interfaccia della riga di comando di .NET Core](local-tools-how-to-use.md)

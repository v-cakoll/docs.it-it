---
title: Comando dotnet tool install
description: Il comando dotnet tool install installa lo strumento .NET Core specificato nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 1e142773d1f981a8dc3b552d5a23d2864cdd82c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146463"
---
# <a name="dotnet-tool-install"></a>dotnet tool install

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool install`- Installa lo strumento .NET Core specificato nel computer.- Installs the specified [.NET Core tool](global-tools.md) on your machine.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME> <--tool-path>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <PACKAGE_NAME>
    [--add-source] [--configfile] [--framework]
    [-v|--verbosity] [--version]

dotnet tool install <-h|--help>
```

## <a name="description"></a>Descrizione

Il `dotnet tool install` comando consente di installare gli strumenti .NET Core nel computer. Per utilizzare il comando, specificare una delle seguenti opzioni di installazione:

* Per installare uno strumento globale nel `--global` percorso predefinito, utilizzare l'opzione .
* Per installare uno strumento globale in `--tool-path` un percorso personalizzato, utilizzare l'opzione .
* Per installare uno strumento locale, `--global` `--tool-path` omettere le opzioni e .

**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0.**

Gli strumenti globali vengono installati nelle seguenti `-g` directory `--global` per impostazione predefinita quando si specifica l'opzione o :

| OS          | Path                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Gli strumenti locali vengono aggiunti a un file *tool-manifest.json* in una directory *.config* nella directory corrente. Se non esiste ancora un file manifesto, crearlo eseguendo il comando seguente:

```dotnetcli
dotnet new tool-manifest
```

Per ulteriori informazioni, consultate [Installare uno strumento locale.](global-tools.md#install-a-local-tool)

## <a name="arguments"></a>Argomenti

- **`PACKAGE_NAME`**

  Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da installare.

## <a name="options"></a>Opzioni

- **`add-source <SOURCE>`**

  Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.

- **`configfile <FILE>`**

  File di configurazione NuGet (*nuget.config*) da usare.

- **`framework <FRAMEWORK>`**

  Specifica il [framework di destinazione](../../standard/frameworks.md) per cui installare lo strumento. Per impostazione predefinita, .NET Core SDK tenta di scegliere il framework di destinazione più appropriato.

- **`-g|--global`**

  Specifica che l'installazione è a livello utente. Non può essere usata con l'opzione `--tool-path`. Omettendo `--global` entrambi `--tool-path` e specifica un'installazione dello strumento locale.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`tool-path <PATH>`**

  Specifica il percorso in cui disinstallare lo strumento globale. Il valore di PATH può essere assoluto o relativo. Se PATH non esiste, il comando tenta di creare la variabile. Omettendo `--global` entrambi `--tool-path` e specifica un'installazione dello strumento locale.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

- **`--version <VERSION_NUMBER>`**

  La versione dello strumento da installare. Per impostazione predefinita, viene installata la versione del pacchetto stabile più recente. Usare questa opzione per installare le versioni di anteprima o precedenti dello strumento.

## <a name="examples"></a>Esempi

- **`dotnet tool install -g dotnetsay`**

  Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale nel percorso predefinito.

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale in una directory di Windows specifica.

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale in una directory Linux/macOS specifica.

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  Installa la versione 2.0.0 di [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale.

- **`dotnet tool install dotnetsay`**

  Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento locale per la directory corrente.

## <a name="see-also"></a>Vedere anche

- [Strumenti .NET Core](global-tools.md)
- [Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI](global-tools-how-to-use.md)
- [Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md)

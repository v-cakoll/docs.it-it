---
title: Comando dotnet tool install
description: Il comando dotnet tool install installa lo strumento globale .NET Core specificato nel computer.
ms.date: 05/29/2018
ms.openlocfilehash: d6f691117e93a39c9837b282dca19e452515c80a
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117468"
---
# <a name="dotnet-tool-install"></a>dotnet tool install

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>nome

`dotnet tool install` - Installa lo [strumento globale .NET Core](global-tools.md) specificato nel computer.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a>Descrizione

Il comando `dotnet tool install` consente di installare gli strumenti globali .NET Core nel computer. Per usare il comando, è necessario specificare che si vuole un'installazione a livello utente con l'opzione `--global` oppure specificare un percorso per l'installazione con l'opzione `--tool-path`.

Gli strumenti globali vengono installati nelle directory seguenti per impostazione predefinita quando si specifica l'opzione `-g` (o `--global`):

| Sistema operativo          | Path                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| WINDOWS     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a>Argomenti

`PACKAGE_NAME`

Nome/ID del pacchetto NuGet che contiene lo strumento globale .NET Core da installare.

## <a name="options"></a>Opzioni

`--add-source <SOURCE>`

Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.

`--configfile <FILE>`

File di configurazione NuGet (*nuget.config*) da usare.

`--framework <FRAMEWORK>`

Specifica il [framework di destinazione](../../standard/frameworks.md) per cui installare lo strumento. Per impostazione predefinita, .NET Core SDK tenta di scegliere il framework di destinazione più appropriato.

`-g|--global`

Specifica che l'installazione è a livello utente. Non può essere usata con l'opzione `--tool-path`. Se non si specifica questa opzione, è necessario specificare l'opzione `--tool-path`.

`-h|--help`

Stampa una breve guida per il comando.

`--tool-path <PATH>`

Specifica il percorso in cui disinstallare lo strumento globale. Il valore di PATH può essere assoluto o relativo. Se PATH non esiste, il comando tenta di creare la variabile. Non può essere usata con l'opzione `--global`. Se non si specifica questa opzione, è necessario specificare l'opzione `--global`.

`-v|--verbosity <LEVEL>`

Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

`--version <VERSION_NUMBER>`

La versione dello strumento da installare. Per impostazione predefinita, viene installata la versione del pacchetto stabile più recente. Usare questa opzione per installare le versioni di anteprima o precedenti dello strumento.

## <a name="examples"></a>Esempi

Installa lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) nel percorso predefinito:

`dotnet tool install -g dotnetsay`

Installa lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in una cartella di Windows specifica:

`dotnet tool install dotnetsay --tool-path c:\global-tools`

Installa lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) in una cartella di Linux/macOS specifica:

`dotnet tool install dotnetsay --tool-path ~/bin`

Installa la versione 2.0.0 dello strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a>Vedere anche

- [Strumenti globali .NET Core](global-tools.md)

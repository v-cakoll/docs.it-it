---
title: Comando dotnet tool install
description: Il comando DotNet tool install installa lo strumento .NET Core specificato nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 2705defe9b77009ca1411da28dd86d144ccc19e6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543469"
---
# <a name="dotnet-tool-install"></a>dotnet tool install

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool install`: installa lo [strumento .NET Core](global-tools.md) specificato nel computer.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a>Descrizione

Il comando `dotnet tool install` consente di installare gli strumenti di .NET Core nel computer. Per utilizzare il comando, è necessario specificare una delle opzioni di installazione seguenti:

* Per installare uno strumento globale nel percorso predefinito, usare l'opzione `--tool-path`.
* Per installare uno strumento globale in un percorso personalizzato, utilizzare l'opzione `--tool-path`.
* Per installare uno strumento locale, omettere le opzioni `--global` e `--tool-path`.

**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**

Per impostazione predefinita, gli strumenti globali vengono installati nelle directory seguenti quando si specifica l'opzione `-g` o `--global`:

| OS          | Path                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Gli strumenti locali vengono aggiunti a un file con estensione *JSON dello strumento* in una directory *. config* nella directory corrente. Se un file manifesto non esiste ancora, crearlo eseguendo il comando seguente:

```dotnetcli
dotnet new tool-manifest
```

Per ulteriori informazioni, vedere [Install a local Tool](global-tools.md#install-a-local-tool).

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

  Specifica che l'installazione è a livello utente. Non può essere usata con l'opzione `--tool-path`. Omettere sia `--global` che `--tool-path` specifica un'installazione dello strumento locale. 

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`tool-path <PATH>`**

  Specifica il percorso in cui disinstallare lo strumento globale. Il valore di PATH può essere assoluto o relativo. Se PATH non esiste, il comando tenta di creare la variabile. Omettere sia `--global` che `--tool-path` specifica un'installazione dello strumento locale. 

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

  Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale in una directory Linux/MacOS specifica.

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  Installa la versione 2.0.0 di [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento globale.

- **`dotnet tool install dotnetsay`**

  Installa [dotnetsay](https://www.nuget.org/packages/dotnetsay/) come strumento locale per la directory corrente.

## <a name="see-also"></a>Vedere anche

- [Strumenti di .NET Core](global-tools.md)

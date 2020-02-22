---
title: Comando dotnet tool update
description: Il comando DotNet Tool Update aggiorna lo strumento .NET Core specificato nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 50bb366fedfb0ea69b8b6007ff89e366b4f689de
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543417"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool update`: aggiorna lo [strumento .NET Core](global-tools.md) specificato nel computer.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <-h|--help>
```

## <a name="description"></a>Descrizione

Il `dotnet tool update` comando fornisce un modo per aggiornare gli strumenti di .NET Core nel computer alla versione stabile più recente del pacchetto. Il comando disinstalla e reinstalla uno strumento aggiornandolo. Per utilizzare il comando, è necessario specificare una delle opzioni seguenti:

* Per aggiornare uno strumento globale che è stato installato nel percorso predefinito, usare l'opzione `--global`
* Per aggiornare uno strumento globale installato in un percorso personalizzato, utilizzare l'opzione `--tool-path`.
* Per aggiornare uno strumento locale, omettere le opzioni `--global` e `--tool-path`.

**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**

## <a name="arguments"></a>Argomenti

- **`PACKAGE_NAME`**

  Nome/ID del pacchetto NuGet che contiene lo strumento globale .NET Core da aggiornare. È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Opzioni

- **`--add-source <SOURCE>`**

  Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.

- **`--configfile <FILE>`**

  File di configurazione NuGet (*nuget.config*) da usare.

- **`--framework <FRAMEWORK>`**

  Specifica il [framework di destinazione](../../standard/frameworks.md) per cui aggiornare lo strumento.

- **`-g|--global`**

  Specifica che l'aggiornamento è per uno strumento a livello utente. Non può essere usata con l'opzione `--tool-path`. Omettendo sia `--global` che `--tool-path` specifica che lo strumento da aggiornare è uno strumento locale. 

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--tool-path <PATH>`**

  Specifica il percorso in cui è installato lo strumento globale. Il valore di PATH può essere assoluto o relativo. Non può essere usata con l'opzione `--global`. Omettendo sia `--global` che `--tool-path` specifica che lo strumento da aggiornare è uno strumento locale. 

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

## <a name="see-also"></a>Vedere anche

- [Strumenti di .NET Core](global-tools.md)

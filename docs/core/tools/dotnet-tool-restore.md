---
title: Comando di ripristino dello strumento dotnet
description: Il comando dotnet tool restore installa nel computer gli strumenti locali .NET Core che rientrano nell'ambito della directory corrente.
ms.date: 02/14/2020
ms.openlocfilehash: cb46f70afb58e482b6aedfddfbf5f3a0c40674f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146437"
---
# <a name="dotnet-tool-restore"></a>dotnet tool restore

**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool restore`- Installa nel computer gli strumenti locali .NET Core che rientrano nell'ambito della directory corrente.- Installs on your machine the .NET Core local tools that are in scope for the current directory.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool restore <PACKAGE_NAME>
    [--configfile] [--add-source] [tool-manifest]
    [--disable-parallel] [--ignore-failed-sources]
    [--no-cache] [-interactive] [-v|--verbosity]

dotnet tool restore <-h|--help>
```

## <a name="description"></a>Descrizione

Il `dotnet tool restore` comando trova il file manifesto dello strumento che si trova nell'ambito della directory corrente e installa gli strumenti elencati in esso. Per informazioni sui file manifesto, consultate [Installare uno strumento locale](global-tools.md#install-a-local-tool) e [Richiamare uno strumento locale.](global-tools.md#invoke-a-local-tool)

## <a name="arguments"></a>Argomenti

- **`PACKAGE_NAME`**

Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da installare.

## <a name="options"></a>Opzioni

- **`--configfile <FILE>`**

  File di configurazione NuGet (*nuget.config*) da usare.

- **`--add-source <SOURCE>`**

  Aggiunge un'altra origine pacchetto NuGet da usare durante l'installazione.

- **`--tool-manifest <PATH>`**

  Percorso del file manifesto.

- **`--disable-parallel`**

  Impedire il ripristino di più progetti in parallelo.

- **`--ignore-failed-sources`**

  Considerare gli errori di origine del pacchetto come avvisi.

- **`--no-cache`**

  Non memorizzare nella cache i pacchetti e le richieste http.

- **`--interactive`**

  Consente al comando di arrestarsi e attendere l'input o l'azione dell'utente (ad esempio, il completamento dell'autenticazione).

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`-v|--verbosity <LEVEL>`**

  Imposta il livello di dettaglio del comando. I valori consentiti sono `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` e `diag[nostic]`.

## <a name="example"></a>Esempio

- **`dotnet tool restore`**

  Ripristina gli strumenti locali per la directory corrente.

## <a name="see-also"></a>Vedere anche

- [Strumenti .NET Core](global-tools.md)
- [Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md)

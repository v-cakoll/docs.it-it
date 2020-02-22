---
title: comando DotNet Tool Restore
description: Il comando DotNet Tool Restore installa nel computer gli strumenti locali di .NET Core inclusi nell'ambito per la directory corrente.
ms.date: 02/14/2020
ms.openlocfilehash: 2900d431987661a9232ceed10d9a424093f8be45
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543908"
---
# <a name="dotnet-tool-restore"></a>ripristino strumento DotNet

**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool restore`: installa nel computer gli strumenti locali di .NET Core che rientrano nell'ambito della directory corrente.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool restore <PACKAGE_NAME> [--configfile] [--add-source] [tool-manifest] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [-interactive] [-v|--verbosity]
dotnet tool restore <-h|--help>
```

## <a name="description"></a>Descrizione

Il comando `dotnet tool restore` trova il file manifesto dello strumento nell'ambito della directory corrente e installa gli strumenti elencati. Per informazioni sui file manifesto, vedere [Install a local Tool](global-tools.md#install-a-local-tool) e [Invoke an local Tool](global-tools.md#invoke-a-local-tool).

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

  Impedisci il ripristino di più progetti in parallelo.

- **`--ignore-failed-sources`**

  Considera gli errori di origine del pacchetto come avvisi.

- **`--no-cache`**

  Non memorizzare nella cache pacchetti e richieste HTTP.

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

- [Strumenti di .NET Core](global-tools.md)

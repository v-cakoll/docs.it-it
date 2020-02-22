---
title: Comando dotnet tool list
description: Il comando DotNet Tool List elenca gli strumenti di .NET Core installati nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: bb74cfeaf441cf8a1a030d97d16655f85d8267d1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543456"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool list`: elenca tutti gli [strumenti di .NET Core](global-tools.md) del tipo specificato attualmente installato nel computer.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list
dotnet tool list <-h|--help>
```

## <a name="description"></a>Descrizione

Il `dotnet tool list` comando fornisce un modo per elencare tutti gli strumenti globali, di percorso degli strumenti e di .NET Core installati nel computer. Il comando elenca il nome del pacchetto, la versione installata e il comando dello strumento.  Per utilizzare il comando, è necessario specificare uno dei seguenti elementi:

* Uno strumento globale installato nel percorso predefinito. Usare l'opzione `--global`
* Uno strumento globale installato in un percorso personalizzato. Usare l'opzione `--tool-path`.
* Uno strumento locale. Omettere le opzioni `--global` e `--tool-path`.

**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**

## <a name="options"></a>Opzioni

- **`-g|--global`**

  Elenca gli strumenti globali a livello di utente. Non può essere usata con l'opzione `--tool-path`. Omettere sia `--global` che `--tool-path` elenca gli strumenti locali. 

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--tool-path <PATH>`**

  Specifica una posizione personalizzata in cui trovare gli strumenti globali. Il valore di PATH può essere assoluto o relativo. Non può essere usata con l'opzione `--global`. Omettere sia `--global` che `--tool-path` elenca gli strumenti locali. 

## <a name="examples"></a>Esempi

- **`dotnet tool list -g`**

  Elenca tutti gli strumenti globali installati a livello di utente nel computer (profilo utente corrente).

- **`dotnet tool list --tool-path c:\global-tools`**

  Elenca gli strumenti globali da una directory di Windows specifica.

- **`dotnet tool list --tool-path ~/bin`**

  Elenca gli strumenti globali da una directory Linux/macOS specifica.

- **`dotnet tool list`**

  Elenca tutti gli strumenti locali disponibili nella directory corrente.

## <a name="see-also"></a>Vedere anche

- [Strumenti di .NET Core](global-tools.md)

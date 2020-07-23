---
title: Comando dotnet tool list
description: Il comando DotNet Tool List elenca gli strumenti di .NET Core installati nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 4035c5be233232e53c6d7150485f737108c1e18d
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925462"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool list`: Elenca tutti gli [strumenti di .NET Core](global-tools.md) del tipo specificato attualmente installato nel computer.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet tool list` comando fornisce un modo per elencare tutti gli strumenti globali, di percorso degli strumenti e di .net core installati nel computer. Il comando elenca il nome del pacchetto, la versione installata e il comando dello strumento.  Per utilizzare il comando, è necessario specificare uno dei seguenti elementi:

* Per elencare gli strumenti globali installati nel percorso predefinito, usare l' `--global` opzione
* Per elencare gli strumenti globali installati in un percorso personalizzato, utilizzare l' `--tool-path` opzione.
* Per elencare gli strumenti locali, utilizzare l' `--local` opzione oppure omettere le `--global` `--tool-path` Opzioni, e `--local` .

**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**

## <a name="options"></a>Opzioni

- **`-g|--global`**

  Elenca gli strumenti globali a livello di utente. Non può essere usata con l'opzione `--tool-path`. Omettendo `--global` ed `--tool-path` elenca gli strumenti locali.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--local`**

  Elenca gli strumenti locali per la directory corrente. Non può essere combinato con `--global` le `--tool-path` Opzioni o. L'omissione `--global` di entrambi `--tool-path` gli strumenti e l'elenco degli strumenti locali anche se `--local` non è specificato.

- **`--tool-path <PATH>`**

  Specifica una posizione personalizzata in cui trovare gli strumenti globali. Il valore di PATH può essere assoluto o relativo. Non può essere usata con l'opzione `--global`. Omettendo `--global` ed `--tool-path` elenca gli strumenti locali.

## <a name="examples"></a>Esempi

- **`dotnet tool list -g`**

  Elenca tutti gli strumenti globali installati a livello di utente nel computer (profilo utente corrente).

- **`dotnet tool list --tool-path c:\global-tools`**

  Elenca gli strumenti globali da una directory di Windows specifica.

- **`dotnet tool list --tool-path ~/bin`**

  Elenca gli strumenti globali da una directory Linux/macOS specifica.

- **`dotnet tool list`** o**`dotnet tool list --local`**

  Elenca tutti gli strumenti locali disponibili nella directory corrente.

## <a name="see-also"></a>Vedere anche

- [Strumenti di .NET Core](global-tools.md)
- [Esercitazione: installare e usare uno strumento globale .NET Core usando il interfaccia della riga di comando di .NET Core](global-tools-how-to-use.md)
- [Esercitazione: installare e usare uno strumento locale di .NET Core usando il interfaccia della riga di comando di .NET Core](local-tools-how-to-use.md)

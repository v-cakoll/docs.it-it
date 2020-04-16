---
title: Comando dotnet tool list
description: Il comando dotnet tool list elenca gli strumenti .NET Core installati nel computer.
ms.date: 02/14/2020
ms.openlocfilehash: 28f9155407d1238f8b0960b69b34ea329ca0e8e6
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463353"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool list`- Elenca tutti [gli strumenti .NET Core](global-tools.md) del tipo specificato attualmente installati nel computer.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet tool list` comando consente di elencare tutti gli strumenti globali, di percorso degli strumenti o locali di .NET Core installati nel computer. Il comando elenca il nome del pacchetto, la versione installata e il comando dello strumento.  Per utilizzare il comando, specificare una delle opzioni seguenti:

* Uno strumento globale installato nel percorso predefinito. Utilizzare `--global` l'opzione
* Strumento globale installato in una posizione personalizzata. Usare l'opzione `--tool-path`.
* Uno strumento locale. Omettere le `--global` `--tool-path` opzioni e .

**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0.**

## <a name="options"></a>Opzioni

- **`-g|--global`**

  Elenca gli strumenti globali a livello di utente. Non può essere usata con l'opzione `--tool-path`. Omettendo `--global` sia `--tool-path` ed elenca gli strumenti locali.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--tool-path <PATH>`**

  Specifica una posizione personalizzata in cui trovare gli strumenti globali. Il valore di PATH può essere assoluto o relativo. Non può essere usata con l'opzione `--global`. Omettendo `--global` sia `--tool-path` ed elenca gli strumenti locali.

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

- [Strumenti .NET Core](global-tools.md)
- [Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI](global-tools-how-to-use.md)
- [Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md)

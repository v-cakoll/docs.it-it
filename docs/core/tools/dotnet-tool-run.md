---
title: Comando di esecuzione dello strumento dotnet
description: Il comando dotnet tool run richiama uno strumento locale.
ms.date: 02/14/2020
ms.openlocfilehash: a088cd0b7f4bba014234a8189a42a63aa6d88f4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847846"
---
# <a name="dotnet-tool-run"></a>dotnet tool run

**Questo articolo si applica a:** ✔️ .NET Core 3.0 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool run`- Richiama uno strumento locale.- Invokes a local tool.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run <-h|--help>
```

## <a name="description"></a>Descrizione

Il `dotnet tool run` comando cerca i file manifesto dello strumento che si trovano nell'ambito della directory corrente. Quando trova un riferimento allo strumento specificato, esegue lo strumento. Per ulteriori informazioni, consultate [Richiamare uno strumento locale.](global-tools.md#invoke-a-local-tool)

## <a name="arguments"></a>Argomenti

- **`COMMAND_NAME`**

  Nome del comando dello strumento da eseguire.

## <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una breve guida per il comando.

## <a name="example"></a>Esempio

- **`dotnet tool run dotnetsay`**

  Esegue `dotnetsay` lo strumento locale.

## <a name="see-also"></a>Vedere anche

- [Strumenti .NET Core](global-tools.md)
- [Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md)

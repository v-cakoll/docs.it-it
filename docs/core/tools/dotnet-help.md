---
title: Comando dotnet help
description: Il comando dotnet help mostra documentazione online più dettagliata per il comando specificato.
ms.date: 02/14/2020
ms.openlocfilehash: a59e74a318118b6fd39d1895df02d76daa6fc9e1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463683"
---
# <a name="dotnet-help-reference"></a>riferimento dotnet help

**Questo articolo si applica a:** ✔️ .NET Core 2.0 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet help` - Mostra documentazione online più dettagliata per il comando specificato.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a>Descrizione

Il comando `dotnet help` apre la pagina di riferimento per ulteriori informazioni sul comando specificato in docs.microsoft.com.

## <a name="arguments"></a>Argomenti

- **`COMMAND_NAME`**

  Nome del comando dell’interfaccia della riga di comando di .NET Core. Per un elenco dei comandi dell’interfaccia della riga di comando validi, vedere [i comandi CLI](index.md#cli-commands).

## <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

- Apre la pagina della documentazione per il comando [dotnet new](dotnet-new.md):

  ```dotnetcli
  dotnet help new
  ```

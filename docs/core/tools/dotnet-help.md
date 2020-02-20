---
title: Comando dotnet help
description: Il comando dotnet help mostra documentazione online più dettagliata per il comando specificato.
ms.date: 02/14/2020
ms.openlocfilehash: f5d9221ae18653451a3bf97dc82fae396ae4e288
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503721"
---
# <a name="dotnet-help-reference"></a>riferimento dotnet help

**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet help` - Mostra documentazione online più dettagliata per il comando specificato.

## <a name="synopsis"></a>Riepilogo

`dotnet help <COMMAND_NAME> [-h|--help]`

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

---
title: Comando dotnet help
description: Il comando dotnet help mostra documentazione online più dettagliata per il comando specificato.
ms.date: 08/08/2019
ms.openlocfilehash: 9bb4e54d2634c000707752edf53b38af43c4344e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734242"
---
# <a name="dotnet-help-reference"></a>riferimento dotnet help

**Questo articolo si applica a:** ✔️ .net core 2,0 SDK e versioni successive

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a>Name

`dotnet help` - Mostra documentazione online più dettagliata per il comando specificato.

## <a name="synopsis"></a>Riepilogo

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet help` apre la pagina di riferimento per ulteriori informazioni sul comando specificato in docs.microsoft.com.

## <a name="arguments"></a>Argomenti

* **`COMMAND_NAME`**

  Nome del comando dell’interfaccia della riga di comando di .NET Core. Per un elenco dei comandi dell’interfaccia della riga di comando validi, vedere [i comandi CLI](index.md#cli-commands).

## <a name="options"></a>Options

* **`-h|--help`**

  Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

* Apre la pagina della documentazione per il comando [dotnet new](dotnet-new.md):

  ```dotnetcli
  dotnet help new
  ```

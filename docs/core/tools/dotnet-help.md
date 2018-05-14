---
title: Comando dotnet help - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet help mostra documentazione online più dettagliata per il comando specificato.
author: mairaw
ms.author: mairaw
ms.date: 08/17/2017
ms.openlocfilehash: 846ca15fa40a4cf9e1bd18c14cbcd9aef5cab97d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-help-reference"></a>riferimento dotnet help

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>nome

`dotnet help` - Mostra documentazione online più dettagliata per il comando specificato.

## <a name="synopsis"></a>Riepilogo

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet help` apre la pagina di riferimento per ulteriori informazioni sul comando specificato in docs.microsoft.com.

## <a name="arguments"></a>Argomenti

`COMMAND_NAME`

Nome del comando dell’interfaccia della riga di comando di .NET Core. Per un elenco dei comandi dell’interfaccia della riga di comando validi, vedere [i comandi CLI](index.md#cli-commands).

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

Apre la pagina della documentazione per il comando [dotnet new](dotnet-new.md):

`dotnet help new`

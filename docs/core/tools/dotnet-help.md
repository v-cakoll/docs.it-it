---
title: Comando dotnet help - Interfaccia della riga di comando di .NET Core
description: "Il comando dotnet help mostra documentazione online più dettagliata per il comando specificato."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: b33d21d7578bb4c1b33c655103f720b32aaf2203
ms.contentlocale: it-it
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-help-reference"></a>riferimento dotnet help

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>nome

`dotnet help` - Mostra documentazione online più dettagliata per il comando specificato.

## <a name="synopsis"></a>Riepilogo

`dotnet list <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet help` apre la pagina di riferimento per ulteriori informazioni sul comando specificato in docs.microsoft.com.

## <a name="arguments"></a>Argomenti

`COMMAND_NAME`

Nome del comando dell’interfaccia della riga di comando di .NET Core. Per un elenco dei comandi dell’interfaccia della riga di comando validi, vedere [i comandi CLI](index.md#cli-commands).

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:

`dotnet list app/app.csproj reference`

Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:

`dotnet list reference`


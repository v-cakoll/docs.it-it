---
title: Comando dotnet list reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: a4ceadb6d070d7997e75b472624bbe2c1650396d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet list reference`: visualizza un elenco dei riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet list reference` offre un'opzione utile per visualizzare un elenco dei riferimenti al progetto per un progetto specificato.

## <a name="arguments"></a>Argomenti

`PROJECT`

Specifica il file di progetto da usare per l'elenco dei riferimenti. Se non specificato, il comando cercherà un file di progetto nella directory corrente.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

## <a name="examples"></a>Esempi

Visualizzare l'elenco dei riferimenti al progetto per il progetto specificato:

`dotnet list app/app.csproj reference`

Visualizzare l'elenco dei riferimenti al progetto per il progetto nella directory corrente:

`dotnet list reference`

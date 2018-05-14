---
title: Comando dotnet list reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet list reference offre un'opzione utile per visualizzare un elenco dei riferimenti da progetto a progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 24cb1124fc3f8707afe727e6a73d35d5dde39937
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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

---
title: Comando dotnet remove reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet remove reference offre un'opzione utile per rimuovere riferimenti da progetto a progetto.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 209f1ad62221e8a80efa161354a2c074d74b7c5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet remove reference`: rimuove i riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet remove reference` offre un'opzione utile per rimuovere i riferimenti al progetto da un progetto.

## <a name="arguments"></a>Argomenti

`PROJECT`

File di progetto di destinazione. Se non specificato, il comando ne cerca uno nella directory corrente.

`PROJECT_REFERENCES`

Riferimenti da progetto a progetto da rimuovere. È possibile specificare uno o più progetti. I [criteri GLOB](https://en.wikipedia.org/wiki/Glob_(programming)) sono supportati nei terminali basati su Unix/Linux.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

`-f|--framework <FRAMEWORK>`

Rimuove il riferimento solo quando la destinazione è un [framework](../../standard/frameworks.md) specifico.

## <a name="examples"></a>Esempi

Rimuovere un riferimento al progetto dal progetto specificato:

`dotnet remove app/app.csproj reference lib/lib.csproj`

Rimuovere più riferimenti al progetto dal progetto nella directory corrente:

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

Rimuovere più riferimenti al progetto usando un criterio GLOB in Unix/Linux:

`dotnet remove app/app.csproj reference **/*.csproj`

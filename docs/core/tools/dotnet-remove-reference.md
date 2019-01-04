---
title: Comando dotnet remove reference
description: Il comando dotnet remove reference offre un'opzione utile per rimuovere riferimenti da progetto a progetto.
ms.date: 05/29/2018
ms.openlocfilehash: bfac4721743babcf48fd8e86a50c8df136e1bfce
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170613"
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet remove reference`: rimuove i riferimenti da progetto a progetto.

## <a name="synopsis"></a>Riepilogo

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>Description

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

---
title: Comando dotnet-remove reference - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-remove reference offre un'opzione utile per rimuovere riferimenti da progetto a progetto.
keywords: dotnet-remove, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 889c6b7e-a313-40b1-9fd3-6a6f4c52f1d0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e22f64370be4b56597a303d79d3aabe1ff22a78a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-remove-reference"></a>dotnet-remove reference

## <a name="name"></a>Nome

`dotnet-remove reference`: rimuove i riferimenti da progetto a progetto.

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


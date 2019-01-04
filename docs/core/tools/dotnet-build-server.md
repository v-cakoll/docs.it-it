---
title: Comando dotnet build-server
description: Il comando dotnet build-server interagisce con i server avviati da una compilazione.
ms.date: 12/04/2018
ms.openlocfilehash: 7f78a0cae6e3297f3084754dc56b0da4eac38caf
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169658"
---
# <a name="dotnet-build-server"></a>dotnet build-server

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>nome

`dotnet build-server`: interagisce con i server avviati da una compilazione.

## <a name="synopsis"></a>Riepilogo

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>Comandi:

* **`shutdown`**

  Arresta i server di compilazione avviati da dotnet. Per impostazione predefinita, vengono arrestati tutti i server.

## <a name="options"></a>Opzioni

* **`-h|--help`**

  Stampa una breve guida per il comando.

* **`--msbuild`**

  Arresta il server di compilazione MSBuild.

* **`--razor`**

  Arresta il server di compilazione Razor.

* **`--vbcscompiler`**

  Arresta il server di compilazione del compilatore VB/C#.
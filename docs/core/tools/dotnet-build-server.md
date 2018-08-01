---
title: Comando dotnet build-server - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet build-server interagisce con i server avviati da una compilazione.
author: mairaw
ms.author: mairaw
ms.date: 07/02/2018
ms.openlocfilehash: 1c59c85f246b79c7e2552f704db5b4f076f9b502
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404333"
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

`shutdown`

Arresta i server di compilazione avviati da dotnet. Per impostazione predefinita, vengono arrestati tutti i server.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

`--msbuild`

Arresta il server di compilazione MSBuild.

`--razor`

Arresta il server di compilazione Razor.

`--vbcscompiler`

Arresta il server di compilazione del compilatore VB/C#.

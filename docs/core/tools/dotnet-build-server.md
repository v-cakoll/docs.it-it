---
title: Comando dotnet build-server
description: Il comando dotnet build-server interagisce con i server avviati da una compilazione.
ms.date: 02/14/2020
ms.openlocfilehash: a6a9cd6de66371caef66d1101b3f844dffc771ef
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503772"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet build-server`: interagisce con i server avviati da una compilazione.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>Comandi:

- **`shutdown`**

  Arresta i server di compilazione avviati da dotnet. Per impostazione predefinita, vengono arrestati tutti i server.

## <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--msbuild`**

  Arresta il server di compilazione MSBuild.

- **`--razor`**

  Arresta il server di compilazione Razor.

- **`--vbcscompiler`**

  Arresta il server di compilazione del compilatore VB/C#.

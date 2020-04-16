---
title: Comando dotnet build-server
description: Il comando dotnet build-server interagisce con i server avviati da una compilazione.
ms.date: 02/14/2020
ms.openlocfilehash: 882b697c07aac0e20266f3ad4e6c11888a0b7acc
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463733"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet build-server`: interagisce con i server avviati da una compilazione.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]

dotnet build-server shutdown -h|--help

dotnet build-server -h|--help
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

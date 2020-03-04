---
title: comando DotNet Tool Run
description: Il comando DotNet Tool Run richiama uno strumento locale.
ms.date: 02/14/2020
ms.openlocfilehash: 76830b8a8088fbf21f14ab0722b9547eabde7ba4
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156959"
---
# <a name="dotnet-tool-run"></a>dotnet tool run

**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool run`: richiama uno strumento locale.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool run <COMMAND NAME>
dotnet tool run <-h|--help>
```

## <a name="description"></a>Descrizione

Il comando `dotnet tool run` Cerca i file manifesto degli strumenti che rientrano nell'ambito della directory corrente. Quando viene trovato un riferimento allo strumento specificato, viene eseguito lo strumento. Per ulteriori informazioni, vedere [Invoke a local Tool](global-tools.md#invoke-a-local-tool).

## <a name="arguments"></a>Argomenti

- **`COMMAND_NAME`**

  Nome del comando dello strumento da eseguire.

## <a name="options"></a>Opzioni

- **`-h|--help`**

  Stampa una breve guida per il comando.

## <a name="example"></a>Esempio

- **`dotnet tool run dotnetsay`**

  Esegue lo strumento locale `dotnetsay`.

## <a name="see-also"></a>Vedere anche

- [Strumenti di .NET Core](global-tools.md)

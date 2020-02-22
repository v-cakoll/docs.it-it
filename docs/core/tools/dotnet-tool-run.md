---
title: comando DotNet Tool Run
description: Il comando DotNet Tool Run richiama uno strumento locale.
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543880"
---
# <a name="dotnet-tool-run"></a>esecuzione dello strumento DotNet

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

---
title: Comando dotnet tool uninstall
description: Il comando DotNet Tool uninstall Disinstalla lo strumento .NET Core specificato dal computer.
ms.date: 02/14/2020
ms.openlocfilehash: 7a15c169c73cf5a743e0fa6f47645d6bccedbde3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157045"
---
# <a name="dotnet-tool-uninstall"></a>dotnet tool uninstall

**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool uninstall`: disinstalla lo [strumento .NET Core](global-tools.md) specificato dal computer.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <PACKAGE_NAME>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a>Descrizione

Il comando `dotnet tool uninstall` fornisce un modo per disinstallare gli strumenti di .NET Core dal computer. Per utilizzare il comando, è necessario specificare una delle opzioni seguenti:

* Per disinstallare uno strumento globale che è stato installato nel percorso predefinito, usare l'opzione `--global`.
* Per disinstallare uno strumento globale installato in un percorso personalizzato, utilizzare l'opzione `--tool-path`.
* Per disinstallare uno strumento locale, omettere le opzioni `--global` e `--tool-path`.

**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.**

## <a name="arguments"></a>Argomenti

- **`PACKAGE_NAME`**

  Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da disinstallare. È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Opzioni

- **`-g|--global`**

  Specifica che lo strumento da rimuovere appartiene a un'installazione a livello utente. Non può essere usata con l'opzione `--tool-path`. Omettendo sia `--global` che `--tool-path` specifica che lo strumento da rimuovere è uno strumento locale.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--tool-path <PATH>`**

  Specifica il percorso in cui disinstallare lo strumento. Il valore di PATH può essere assoluto o relativo. Non può essere usata con l'opzione `--global`. Omettendo sia `--global` che `--tool-path` specifica che lo strumento da rimuovere è uno strumento locale.

## <a name="examples"></a>Esempi

- **`dotnet tool uninstall -g dotnetsay`**

  Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) .

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) da una directory di Windows specifica.

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) da una directory Linux/MacOS specifica.

- **`dotnet tool uninstall dotnetsay`**

  Disinstalla lo strumento locale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) dalla directory corrente.

## <a name="see-also"></a>Vedere anche

- [Strumenti di .NET Core](global-tools.md)

---
title: Comando dotnet tool uninstall
description: Il comando dotnet tool uninstalls lo strumento .NET Core specificato dal computer.
ms.date: 02/14/2020
ms.openlocfilehash: 0416f91019a49e17f1be14a1d928ad1fafaa736c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463316"
---
# <a name="dotnet-tool-uninstall"></a>dotnet tool uninstall

**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet tool uninstall`- Disinstalla lo [strumento .NET Core](global-tools.md) specificato dal computer.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> -g|--global

dotnet tool uninstall <PACKAGE_NAME> --tool-path <PATH>

dotnet tool uninstall <PACKAGE_NAME>

dotnet tool uninstall -h|--help
```

## <a name="description"></a>Descrizione

Il `dotnet tool uninstall` comando consente di disinstallare gli strumenti .NET Core dal computer. Per utilizzare il comando, specificare una delle seguenti opzioni:

* Per disinstallare uno strumento globale installato nel `--global` percorso predefinito, utilizzare l'opzione .
* Per disinstallare uno strumento globale installato in `--tool-path` un percorso personalizzato, utilizzare l'opzione .
* Per disinstallare uno strumento locale, omettere le `--global` opzioni e `--tool-path` .

**Gli strumenti locali sono disponibili a partire da .NET Core SDK 3.0.**

## <a name="arguments"></a>Argomenti

- **`PACKAGE_NAME`**

  Nome/ID del pacchetto NuGet che contiene lo strumento .NET Core da disinstallare. È possibile trovare il nome del pacchetto usando il comando [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Opzioni

- **`-g|--global`**

  Specifica che lo strumento da rimuovere appartiene a un'installazione a livello utente. Non può essere usata con l'opzione `--tool-path`. Omettendo `--global` entrambi `--tool-path` e specifica che lo strumento da rimuovere è uno strumento locale.

- **`-h|--help`**

  Stampa una breve guida per il comando.

- **`--tool-path <PATH>`**

  Specifica il percorso in cui disinstallare lo strumento. Il valore di PATH può essere assoluto o relativo. Non può essere usata con l'opzione `--global`. Omettendo `--global` entrambi `--tool-path` e specifica che lo strumento da rimuovere è uno strumento locale.

## <a name="examples"></a>Esempi

- **`dotnet tool uninstall -g dotnetsay`**

  Disinstalla lo strumento globale [dotnetsay.](https://www.nuget.org/packages/dotnetsay/)

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) da una directory di Windows specifica.

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  Disinstalla lo strumento globale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) da una directory Linux/macOS specifica.

- **`dotnet tool uninstall dotnetsay`**

  Disinstalla lo strumento locale [dotnetsay](https://www.nuget.org/packages/dotnetsay/) dalla directory corrente.

## <a name="see-also"></a>Vedere anche

- [Strumenti .NET Core](global-tools.md)
- [Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI](global-tools-how-to-use.md)
- [Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI](local-tools-how-to-use.md)

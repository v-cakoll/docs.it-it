---
title: InstallareF#
description: Informazioni su come installare F# nel proprio ambiente.
ms.date: 08/28/2018
ms.openlocfilehash: 873d3021ba884ec81992469e5d0f3b7c18b1e0f4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975251"
---
# <a name="install-f"></a>Installare F\#

È possibile installare F# in diversi modi, a seconda dell'ambiente.

## <a name="install-f-with-visual-studio"></a>Installare F# con Visual Studio

Se si sta scaricando [Visual Studio](https://visualstudio.microsoft.com/) per la prima volta, verranno installati prima il programma di installazione di Visual Studio. Installare l'appropriato dello SKU di Visual Studio dal programma di installazione. Se già installato, fare clic su **Modify**.

Successivamente, si verrà visualizzato un elenco dei carichi di lavoro. Selezionare **sviluppo ASP.NET e web** che verrà installato F# supporto di supporto e .NET Core per progetti ASP.NET Core.

Fare quindi clic **Modify** nel lato inferiore destro.  Verranno installati tutti gli elementi selezionati. È quindi possibile aprire Visual Studio 2017 con F# supporto del linguaggio facendo **avvio veloce**.

## <a name="install-f-with-visual-studio-for-mac"></a>Installare F# con Visual Studio per Mac

F#viene installato per impostazione predefinita in [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/), indipendentemente dal quale configurazione scelto.

Al termine dell'installazione, scegliere "Avvia Visual Studio". È anche possibile avviarla tramite Finder in macOS.

## <a name="install-f-with-visual-studio-code"></a>Installare F# con Visual Studio Code

È necessario disporre [git installato](https://git-scm.com/download) ed è disponibile nel percorso desiderato per rendere utilizzare modelli di progetto. È possibile verificare che sia installato correttamente, digitando `git --version` in un prompt dei comandi e premendo **invio**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](https://www.mono-project.com) serve [ F# Interactive](../tutorials/fsharp-interactive/index.md) supportano. Il modo più semplice per installare Mono in macOS è tramite Homebrew. È sufficiente digitare quanto segue nel terminale:

```console
brew install mono
```

Installare anche il [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com) serve [ F# Interactive](../tutorials/fsharp-interactive/index.md) supportano. Se si usa Ubuntu o Debian, è possibile usare quanto segue:

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Installare anche il [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Installare [di Visual Studio con F# supportano](#install-f-with-visual-studio). Ciò consente di installare tutti i componenti necessari per scrivere, compilare ed eseguire F# codice.

Installare anche il [.NET Core SDK](https://www.microsoft.com/net/download/).

---

Sarà quindi necessario [Visual Studio Code](https://code.visualstudio.com) installato.

Successivamente, fare clic sull'icona delle estensioni e cercare "Ionide":

Il plug-in unico necessari per F# è il supporto in Visual Studio Code [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Tuttavia, è anche possibile installare [Ionide FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere [FAKE](https://fsharp.github.io/FAKE/) supportano e [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) ottenere [Paket](https://fsprojects.github.io/Paket/) supportano. SIMULARE e Paket sono descritti altri F# strumenti della community per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.

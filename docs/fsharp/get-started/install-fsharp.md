---
title: Installare F#
description: Informazioni su come installare F# in base all'ambiente in uso.
ms.date: 09/05/2019
ms.openlocfilehash: dffa30eac0bdb59c85a66dca6cafd62b25daa572
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855794"
---
# <a name="install-f"></a>Installare F\#

È possibile installare F# in diversi modi, a seconda dell'ambiente.

## <a name="install-f-with-visual-studio"></a>Eseguire F# l'installazione con Visual Studio

Se si sta scaricando [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) per la prima volta, verrà prima installato il programma di installazione di Visual Studio. Installare lo SKU di Visual Studio appropriato dal programma di installazione. Se è già installato, fare clic su **modifica**.

Verrà visualizzato un elenco di carichi di lavoro. Selezionare **ASP.NET e sviluppo Web** per installare F# il supporto e il supporto di .NET Core per i progetti ASP.NET Core.

Quindi, fare clic su **modifica** nella parte inferiore destra.  Verrà installato tutto ciò che è stato selezionato. È quindi possibile aprire Visual Studio 2017 con F# supporto per la lingua facendo clic su **Avvia**.

## <a name="install-f-with-visual-studio-for-mac"></a>Installare F# con Visual Studio per Mac

F#viene installato per impostazione predefinita in [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), indipendentemente dalla configurazione scelta.

Al termine dell'installazione, scegliere "avvia Visual Studio". È anche possibile avviarlo tramite il Finder in macOS.

## <a name="install-f-with-visual-studio-code"></a>Installare F# con Visual Studio Code

Per usare i modelli di progetto, è necessario che [git sia installato](https://git-scm.com/download) e disponibile nel percorso. È possibile verificare che sia installato correttamente digitando `git --version` al prompt dei comandi e premendo **invio**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](https://www.mono-project.com) viene usato per [ F# ](../tutorials/fsharp-interactive/index.md) il supporto interattivo. Il modo più semplice per installare Mono in macOS è tramite Homebrew. È sufficiente digitare quanto segue nel terminale:

```console
brew install mono
```

Installare anche il [.NET Core SDK](https://dotnet.microsoft.com/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com) viene usato per [ F# ](../tutorials/fsharp-interactive/index.md) il supporto interattivo. Se si è in Debian o Ubuntu, è possibile usare quanto segue:

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Installare anche il [.NET Core SDK](https://dotnet.microsoft.com/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Installare [Visual Studio con F# supporto](#install-f-with-visual-studio). In questo modo vengono installati tutti i componenti necessari per scrivere, compilare F# ed eseguire il codice.

Installare anche il [.NET Core SDK](https://dotnet.microsoft.com/download).

---

Sarà quindi necessario [Visual Studio Code](https://code.visualstudio.com) installato.

Fare quindi clic sull'icona delle estensioni e cercare "Ionide":

Il solo plug-in F# necessario per il supporto nel Visual Studio Code è [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Tuttavia, è anche possibile installare [Ionide-Fake](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere supporto [Fake](https://fsharp.github.io/FAKE/) e [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) per ottenere il supporto di [Paket](https://fsprojects.github.io/Paket/) . FAKE e pake sono strumenti aggiuntivi F# della community per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.

## <a name="install-f-on-a-build-server"></a>Installare F# in un server di compilazione

Se si usa .NET Core o .NET Framework tramite .NET SDK, è sufficiente installare .NET SDK nel server di compilazione. Sono disponibili tutti gli elementi necessari.

Se si usa .NET Framework e **non** si usa .NET SDK, sarà necessario installare lo [SKU di Visual Studio Build Tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) in Windows Server. Nel programma di installazione selezionare **strumenti di compilazione desktop .NET** , quindi selezionare **F#** il componente del compilatore sul lato destro del menu programma di installazione.

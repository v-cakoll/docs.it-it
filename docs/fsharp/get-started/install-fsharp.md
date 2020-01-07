---
title: Installare F#
description: Informazioni su come installare F# in diversi modi.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346556"
---
# <a name="install-f"></a>Installare F\#

È possibile installare F# in diversi modi, a seconda dell'ambiente.

## <a name="install-f-with-visual-studio"></a>Eseguire F# l'installazione con Visual Studio

1. Se si sta scaricando [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) per la prima volta, verrà prima di tutto installato programma di installazione di Visual Studio. Installare la versione appropriata di Visual Studio dal programma di installazione.

   Se Visual Studio è già installato, scegliere **modifica** accanto all'edizione a cui si desidera aggiungere F# .

2. Nella pagina carichi di lavoro selezionare il carico di lavoro **sviluppo Web e ASP.NET** , che F# include il supporto per .NET Core e per i progetti ASP.NET Core.

3. Scegliere **modifica** nell'angolo in basso a destra per installare tutti gli elementi selezionati.

   È quindi possibile aprire Visual Studio con F# scegliendo **Avvia** in programma di installazione di Visual Studio.

## <a name="install-f-with-visual-studio-code"></a>Installare F# con Visual Studio Code

1. Assicurarsi che [git](https://git-scm.com/download) sia installato e disponibile nel percorso. È possibile verificare che sia installato correttamente immettendo `git --version` al prompt dei comandi e premendo **invio**.

2. Installare il [.NET Core SDK](https://dotnet.microsoft.com/download) e [Visual Studio Code](https://code.visualstudio.com).

3. Selezionare l'icona delle estensioni e cercare "Ionide":

   Il solo plug-in F# necessario per il supporto nel Visual Studio Code è [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Tuttavia, è anche possibile installare [Ionide-Fake](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere supporto [Fake](https://fake.build/) e [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) per ottenere il supporto di [Paket](https://fsprojects.github.io/Paket/) . FAKE e pake sono strumenti aggiuntivi F# della community per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.

## <a name="install-f-with-visual-studio-for-mac"></a>Installare F# con Visual Studio per Mac

F#viene installato per impostazione predefinita in [Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), indipendentemente dalla configurazione scelta.

Al termine dell'installazione, scegliere **Avvia Visual Studio**. È anche possibile aprire Visual Studio tramite il Finder in macOS.

## <a name="install-f-on-a-build-server"></a>Installare F# in un server di compilazione

Se si usa .NET Core o .NET Framework tramite .NET SDK, è sufficiente installare .NET SDK nel server di compilazione. Sono disponibili tutti gli elementi necessari.

Se si usa .NET Framework e **non** si usa .NET SDK, è necessario installare lo [SKU Visual Studio Build Tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) nel server Windows. Nel programma di installazione selezionare **strumenti di compilazione desktop .NET**, quindi selezionare il **F#** componente del compilatore sul lato destro del menu programma di installazione.

---
title: Installare F#
description: Scopri come installare F , in vari modi diversi.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79400246"
---
# <a name="install-f"></a>Installazione F\#

È possibile installare F , in diversi modi, a seconda dell'ambiente.

## <a name="install-f-with-visual-studio"></a>Installazione di F , con Visual Studio

1. Se si scarica [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) per la prima volta, verrà innanzitutto installato il programma di installazione di Visual Studio.If you're downloading Visual Studio for the first time, it will first install Visual Studio Installer. Installare l'edizione appropriata di Visual Studio dal programma di installazione.

   Se Visual Studio è già installato in Visual Studio, scegliere **Modifica** accanto all'edizione a cui si vuole aggiungere F.

2. Nella pagina Carichi di lavoro selezionare il carico di lavoro **di sviluppo Web e ASP.NET,** che include il supporto di F e .NET Core per i progetti ASP.NET Core.

3. Scegli **Modifica** nell'angolo in basso a destra per installare tutto ciò che hai selezionato.

   È quindi possibile aprire Visual Studio con F, scegliendo Avvia nel programma di installazione di Visual Studio.You can then open Visual Studio with F's by choosing **Launch** in Visual Studio Installer.

## <a name="install-f-with-visual-studio-code"></a>Installazione di F , con Visual Studio Code

1. Assicurati di aver installato [git](https://git-scm.com/download) e disponibile sul tuo PATH. È possibile verificare che sia `git --version` installato correttamente immettendo al prompt dei comandi e premendo **INVIO**.

2. Installare [.NET Core SDK](https://dotnet.microsoft.com/download) e [Visual Studio Code](https://code.visualstudio.com).

3. Selezionare l'icona Estensioni e cercare "Ionide":

   L'unico plug-in necessario per il supporto F , nel codice di Visual Studio è [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Tuttavia, puoi anche installare [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) per ottenere il supporto [FAKE](https://fake.build/) e [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) per ottenere il supporto [Paket.](https://fsprojects.github.io/Paket/) FAKE e Paket sono strumenti aggiuntivi per la community di F per la compilazione di progetti e la gestione delle dipendenze, rispettivamente.

## <a name="install-f-with-visual-studio-for-mac"></a>Installazione di F , con Visual Studio per Mac

Per impostazione predefinita, f è installato in [Visual Studio per Mac,](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)indipendentemente dalla configurazione scelta.

Al termine dell'installazione, scegliere **Avvia Visual Studio**. Puoi anche aprire Visual Studio tramite Finder su macOS.You can also open Visual Studio through Finder on macOS.

## <a name="install-f-on-a-build-server"></a>Installare F in un server di compilazioneInstall F ' on a build server

Se si usa .NET Core o .NET Framework tramite .NET SDK, è sufficiente installare .NET SDK nel server di compilazione. Ha tutto ciò di cui hai bisogno.

Se si utilizza .NET Framework e **non** si utilizza .NET SDK, sarà necessario installare lo SKU degli strumenti di [compilazione](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) di Visual Studio in Windows Server. Nel programma di installazione selezionare Strumenti di **compilazione desktop .NET**, quindi selezionare il componente **del compilatore F,** sul lato destro del menu del programma di installazione.

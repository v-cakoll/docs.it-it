---
title: Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac
description: In questo argomento viene descritto il processo di creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.openlocfilehash: f751e7532e9627de3d3733476f7214654089e468
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170731"
---
# <a name="getting-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac

Visual Studio per Mac offre un ambiente di sviluppo integrato completo per lo sviluppo di applicazioni .NET Core. In questo argomento viene descritto il processo di creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.

> [!NOTE]
> Microsoft considera di fondamentale importanza i commenti e i suggerimenti degli utenti. Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:
> * In Visual Studio per Mac scegliere **Aiuto** > **Segnala un problema** dal menu o **Segnala un problema** dalla schermata iniziale per visualizzare una finestra per l'archiviazione di un report sul bug. È possibile tenere traccia dei commenti e dei suggerimenti inviati nel portale della [community di sviluppatori](https://developercommunity.visualstudio.com/spaces/8/index.html).
> * Per inviare un suggerimento, scegliere **Aiuto** > **Invia un suggerimento** dal menu o **Invia un suggerimento** dalla schermata iniziale per aprire la [pagina Web Developer Community di Visual Studio per Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Prerequisiti

Vedere l'argomento [Prerequisiti per .NET Core in Mac](../../core/macos-prerequisites.md).

## <a name="getting-started"></a>Per iniziare

Se i prerequisiti e Visual Studio per Mac sono già installati, ignorare questa sezione e passare a [Creazione di un progetto](#creating-a-project). Seguire questa procedura per installare i prerequisiti e Visual Studio per Mac:

Scaricare il [programma di installazione di Visual Studio per Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/). Eseguire il programma di installazione. Leggere e accettare il contratto di licenza. Durante l'installazione viene offerta la possibilità di installare Xamarin, una tecnologia per lo sviluppo di app per dispositivi mobili multipiattaforma. L'installazione di Xamarin e dei relativi componenti è facoltativa per lo sviluppo di .NET Core. Per una descrizione dettagliata del processo di installazione di Visual Studio per Mac, vedere [Presentazione di Visual Studio per Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/). Al termine dell'installazione, avviare l'IDE di Visual Studio per Mac.

## <a name="creating-a-project"></a>Creazione di un progetto

1. Nella schermata iniziale selezionare **Nuovo progetto**.

   ![Nuovo pulsante di progetto nella schermata iniziale di Visual Studio per Mac](./media/using-on-mac-vs/vsmac1.png)

1. Nella finestra di dialogo **Nuovo progetto** selezionare **App** sotto il nodo **.NET Core**. Selezionare il modello **Applicazione console** e quindi scegliere **Avanti**.

   ![Nuovo elenco di modelli di progetto](./media/using-on-mac-vs/vsmac2.png)

1. Digitare "HelloWorld" nel campo **Nome progetto**. Scegliere **Crea**.

   ![Finestra di dialogo di configurazione della nuova applicazione console](./media/using-on-mac-vs/vsmac3.png)

1. Attendere che vengano ripristinate le dipendenze del progetto. Il progetto è costituito da un unico file C#, *Program.cs*, contenente una classe `Program` con un metodo `Main`. L'istruzione `Console.WriteLine` consentirà la visualizzazione di "Hello World!" nella console all'avvio dell'app.

   ![Finestra principale con il file Program.cs aperto](./media/using-on-mac-vs/vsmac4.png)

## <a name="run-the-application"></a>Esecuzione dell'applicazione

Eseguire l'app in modalità di debug premendo <kbd>F5</kbd> o in modalità di rilascio premendo <kbd>CTRL</kbd>+<kbd>F5</kbd>.

![Nel riquadro di output dell'applicazione viene visualizzato Hello World!](./media/using-on-mac-vs/vsmac5.png)

## <a name="next-step"></a>Passaggio successivo

L'argomento [Creazione di una soluzione .NET Core completa in macOS con Visual Studio per Mac](using-on-mac-vs-full-solution.md) illustra come creare una soluzione .NET Core completa contenente librerie riutilizzabili e unit test.

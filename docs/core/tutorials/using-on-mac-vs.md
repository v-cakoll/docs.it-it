---
title: Introduzione a .NET Core con Visual Studio per Mac
description: In questo argomento viene descritto il processo di creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.
author: mairaw
ms.date: 12/19/2019
ms.custom: seodec18
ms.openlocfilehash: f6faf5519109202a2865b0f316251bd2c85a5606
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75342958"
---
# <a name="get-started-with-net-core-on-macos-using-visual-studio-for-mac"></a>Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac

Visual Studio per Mac offre un ambiente di sviluppo integrato completo per lo sviluppo di applicazioni .NET Core. Questo articolo illustra la creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.

> [!NOTE]
> Microsoft considera di fondamentale importanza i commenti e i suggerimenti degli utenti. Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:
>
> * In Visual Studio per Mac scegliere **Aiuto** > **Segnala un problema** dal menu o **Segnala un problema** dalla schermata iniziale per visualizzare una finestra per l'archiviazione di un report sul bug. È possibile tenere traccia dei commenti e dei suggerimenti inviati nel portale della [community di sviluppatori](https://developercommunity.visualstudio.com/spaces/8/index.html).
> * Per inviare un suggerimento, scegliere **Aiuto** > **Invia un suggerimento** dal menu o **Invia un suggerimento** dalla schermata iniziale per aprire la [pagina Web Developer Community di Visual Studio per Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Prerequisiti

Vedere l'articolo [dipendenze e requisiti di .NET Core](../install/dependencies.md?pivots=os-macos) .

Per assicurarsi di usare una versione supportata di .NET Core, vedere l'articolo del [supporto tecnico di .NET Core](/visualstudio/mac/net-core-support) .

## <a name="get-started"></a>Attività iniziali

Se i prerequisiti e Visual Studio per Mac sono già installati, ignorare questa sezione e passare a [Creazione di un progetto](#creating-a-project). Seguire questa procedura per installare i prerequisiti e Visual Studio per Mac:

Scaricare il [programma di installazione di Visual Studio per Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Eseguire il programma di installazione. Leggere e accettare il contratto di licenza. Durante l'installazione selezionare l'opzione per installare .NET Core. Viene offerta la possibilità di installare Xamarin, una tecnologia per lo sviluppo di app per dispositivi mobili multipiattaforma. L'installazione di Xamarin e dei relativi componenti è facoltativa per lo sviluppo di .NET Core. Per una descrizione dettagliata del processo di installazione di Visual Studio per Mac, vedere la [documentazione di Visual Studio per Mac](/visualstudio/mac/). Al termine dell'installazione, avviare l'IDE di Visual Studio per Mac.

## <a name="creating-a-project"></a>Creazione di un progetto

1. Selezionare **nuovo** nella finestra di avvio.

   ![Pulsante Nuovo nella schermata iniziale di Visual Studio per Mac](./media/using-on-mac-vs/visual-studio-mac-new-project.png)

1. Nella finestra di dialogo **Nuovo progetto** selezionare **App** sotto il nodo **.NET Core**. Selezionare il modello **Applicazione console** e quindi scegliere **Avanti**.

   ![Nuovo elenco di modelli di progetto](./media/using-on-mac-vs/visual-studio-mac-new-dialog.png)

1. Se è installata più di una versione di .NET Core, selezionare il framework di destinazione per il progetto.

1. Digitare "HelloWorld" nel campo **Nome progetto**. Scegliere **Crea**.

   ![Finestra di dialogo di configurazione della nuova applicazione console](./media/using-on-mac-vs/visual-studio-mac-new-options.png)

1. Attendere che vengano ripristinate le dipendenze del progetto. Il progetto è costituito da un unico file C#, *Program.cs*, contenente una classe `Program` con un metodo `Main`. L'istruzione `Console.WriteLine` consentirà la visualizzazione di "Hello World!" nella console all'avvio dell'app.

   ![Finestra principale con il file Program.cs aperto](./media/using-on-mac-vs/visual-studio-mac-editor.png)

## <a name="run-the-application"></a>Esecuzione dell'applicazione

Eseguire l'app in modalità debug usando ⌘ ↵ (Comando + Invio) o in modalità versione usando ⌥ ⌘ ↵ (Opzione + Comando + Invio).

![Nel riquadro di output dell'applicazione viene visualizzato Hello World!](./media/using-on-mac-vs/visual-studio-mac-output.png)

## <a name="next-step"></a>Passaggio successivo

L'argomento [Creazione di una soluzione .NET Core completa in macOS con Visual Studio per Mac](using-on-mac-vs-full-solution.md) illustra come creare una soluzione .NET Core completa contenente librerie riutilizzabili e unit test.

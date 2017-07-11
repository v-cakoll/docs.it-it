---
title: Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac | Microsoft Docs
description: In questo argomento viene descritto il processo di creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8902e849-dd17-42c0-8264-cc7ae3927a0c
ms.translationtype: Human Translation
ms.sourcegitcommit: 83200e452bccc20bfa82d94899514019e9d05a23
ms.openlocfilehash: c377d0669efed9abb50965652d286ceb6fad3299
ms.contentlocale: it-it
ms.lasthandoff: 07/05/2017

---

<a id="getting-started-with-net-core-on-macos-using-visual-studio-for-mac" class="xliff"></a>

# Introduzione all'uso di .NET Core su macOS con Visual Studio per Mac

Visual Studio per Mac offre un ambiente di sviluppo integrato completo per lo sviluppo di applicazioni .NET Core. In questo argomento viene descritto il processo di creazione di una semplice applicazione console con Visual Studio per Mac e .NET Core.

> [!NOTE]
> Visual Studio per Mac è un software di anteprima. Come per qualsiasi versione di anteprima di prodotti Microsoft, il feedback dei clienti è sempre tenuto in grande considerazione. Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:
> * In Visual Studio per Mac scegliere **? > Segnala un problema** dal menu o **Segnala un problema** dalla schermata iniziale per visualizzare una finestra per l'archiviazione di un report di bug.
> * Per inviare un suggerimento, scegliere **? > Invia un suggerimento** dal menu o **Invia un suggerimento** dalla schermata iniziale per aprire la [pagina Web UserVoice di Visual Studio per Mac](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac).

<a id="prerequisites" class="xliff"></a>

## Prerequisiti

Per altre informazioni sui prerequisiti, vedere [Prerequisiti per .NET Core in Mac](../../core/macos-prerequisites.md).

<a id="getting-started" class="xliff"></a>

## Per iniziare

Se i prerequisiti e Visual Studio per Mac sono già installati, ignorare questa sezione e passare a [Creazione di un progetto](#creating-a-project). Seguire questa procedura per installare i prerequisiti e Visual Studio per Mac:

Scaricare il [programma di installazione di Visual Studio per Mac](https://www.visualstudio.com/vs/visual-studio-mac/). Eseguire il programma di installazione. Leggere e accettare il contratto di licenza. Durante l'installazione viene offerta la possibilità di installare Xamarin, una tecnologia per lo sviluppo di app per dispositivi mobili multipiattaforma. L'installazione di Xamarin e dei relativi componenti è facoltativa per lo sviluppo di .NET Core. Per una descrizione dettagliata del processo di installazione di Visual Studio per Mac, vedere [Presentazione di Visual Studio per Mac](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/). Al termine dell'installazione, avviare l'IDE di Visual Studio per Mac.

<a id="creating-a-project" class="xliff"></a>

## Creazione di un progetto

1. Nella schermata iniziale selezionare **Nuovo progetto**.

   ![Nuovo pulsante di progetto nella schermata iniziale di Visual Studio per Mac](./media/using-on-mac-vs/vsmac1.png)

1. Nella finestra di dialogo **Nuovo progetto** selezionare **App** sotto il nodo **.NET Core**. Selezionare il modello **Applicazione console** e quindi scegliere **Avanti**.

   ![Nuovo elenco di modelli di progetto](./media/using-on-mac-vs/vsmac2.png)

1. Digitare "HelloWorld" nel campo **Nome progetto**. Scegliere **Crea**.

   ![Finestra di dialogo di configurazione della nuova applicazione console](./media/using-on-mac-vs/vsmac3.png)

1. Attendere che vengano ripristinate le dipendenze del progetto. Il progetto è costituito da un unico file C#, *Program.cs*, contenente una classe `Program` con un metodo `Main`. L'istruzione `Console.WriteLine` consentirà la visualizzazione di "Hello World!" nella console all'avvio dell'app.

   ![Finestra principale con il file Program.cs aperto](./media/using-on-mac-vs/vsmac4.png)

<a id="run-the-application" class="xliff"></a>

## Esecuzione dell'applicazione

Eseguire l'app in modalità di debug premendo <kbd>F5</kbd> o in modalità di rilascio premendo <kbd>CTRL</kbd>+<kbd>F5</kbd>.

![Nel riquadro di output dell'applicazione viene visualizzato Hello World!](./media/using-on-mac-vs/vsmac5.png)

<a id="next-step" class="xliff"></a>

## Passaggio successivo

L'argomento [Creazione di una soluzione .NET Core completa in macOS con Visual Studio per Mac](using-on-mac-vs-full-solution.md) illustra come creare una soluzione .NET Core completa contenente librerie riutilizzabili e unit test.


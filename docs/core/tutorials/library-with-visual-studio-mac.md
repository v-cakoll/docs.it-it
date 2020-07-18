---
title: Creare una libreria di classi .NET Standard usando Visual Studio per Mac
description: Informazioni su come creare una libreria di classi .NET Standard usando Visual Studio per Mac.
ms.date: 06/08/2020
ms.openlocfilehash: 8e1e4ca3bc1b12d889b847d80318f3d6cd1bbe46
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416005"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-for-mac"></a>Esercitazione: creare una libreria di .NET Standard usando Visual Studio per Mac

In questa esercitazione viene creata una libreria di classi che contiene un singolo metodo di gestione delle stringhe. Viene implementato come metodo di [estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md) in modo che sia possibile chiamarlo come se fosse un membro della <xref:System.String> classe.

La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione. Una libreria di classi destinata a .NET Standard 2,1 può essere usata da un'applicazione destinata a qualsiasi implementazione di .NET che supporta la versione 2,1 di .NET Standard. Una volta completata la libreria di classi, è possibile distribuirla come componente di terze parti o come componente in bundle con una o più applicazioni.

> [!NOTE]
> Microsoft considera di fondamentale importanza i commenti e i suggerimenti degli utenti. Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:
>
> - In Visual Studio per Mac selezionare **Guida**  >  **segnala un problema** dal menu o **segnala un problema** dalla schermata iniziale, che apre una finestra per la presentazione di un report sui bug. È possibile tenere traccia dei commenti e dei suggerimenti inviati nel portale della [community di sviluppatori](https://developercommunity.visualstudio.com/spaces/41/index.html).
> - Per **inviare un suggerimento, scegliere**  >  ?**fornire un suggerimento** dal menu o **fornire un suggerimento** dalla schermata iniziale, che consente di ottenere la [pagina Web della community di sviluppatori Visual Studio per Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Prerequisiti

* [Installare Visual Studio per Mac versione 8,6 o successiva](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Selezionare l'opzione per installare .NET Core. L'installazione di Novell è facoltativa per lo sviluppo di .NET Core. Per altre informazioni, vedere le risorse seguenti:

  * [Esercitazione: installare Visual Studio per Mac](/visualstudio/mac/installation).
  * [Versioni di MacOS supportate](../install/dependencies.md?pivots=os-macos).
  * [Versioni di .NET Core supportate da Visual Studio per Mac](/visualstudio/mac/net-core-support).

## <a name="create-a-solution-with-a-class-library-project"></a>Creare una soluzione con un progetto di libreria di classi

Una soluzione di Visual Studio funge da contenitore per uno o più progetti. Creare una soluzione e un progetto libreria di classi nella soluzione. Verranno aggiunti altri progetti correlati alla stessa soluzione in un secondo momento.

1. Avviare Visual Studio per Mac.

1. Nella finestra Start selezionare **nuovo progetto**.

1. Nella finestra di dialogo **nuovo progetto** nel nodo **multipiattaforma** Selezionare **libreria**, quindi selezionare il modello **libreria .NET standard** e fare clic su **Avanti**.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Finestra di dialogo nuovo progetto":::

1. Nella finestra di dialogo **Configura la nuova libreria .NET standard** scegliere ".NET standard 2,1" e quindi fare clic su **Avanti**.

   :::image type="content" source="media/library-with-visual-studio-mac/choose-net-std-21.png" alt-text="Scegliere .NET Standard 2,1":::

1. Denominare il progetto "StringLibrary" e la soluzione "ClassLibraryProjects". Lasciare **Crea una directory del progetto nella directory della soluzione** selezionata. Selezionare **Crea**.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Opzioni della finestra di dialogo Nuovo progetto di Visual Studio per Mac":::

1. Dal menu principale selezionare **Visualizza**  >  **Pads**  >  **soluzione**Pad e selezionare l'icona di ancoraggio per lasciare aperto il riquadro.

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="Icona di ancoraggio per il riquadro della soluzione":::

1. Nel riquadro della **soluzione** espandere il `StringLibrary` nodo per visualizzare il file di classe fornito dal modello, *Class1.cs*. fare clic con il <kbd>pulsante destro del</kbd>mouse sul file, scegliere **Rinomina** dal menu di scelta rapida e rinominare il file in *StringLibrary.cs*. Aprire il file e sostituire il contenuto con il codice seguente:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. Premere <kbd>⌘</kbd><kbd>s</kbd> (<kbd>Command</kbd> + <kbd>s</kbd>) per salvare il file.

1. Selezionare **Errori** nel margine inferiore della finestra dell'IDE per aprire il pannello **Errori**. Selezionare il pulsante **Output di compilazione**.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="Margine inferiore della finestra dell'IDE di Visual Studio per Mac con il pulsante Errori":::

1. Scegliere **Compila**  >  **Compila tutto** dal menu.

   La soluzione viene compilata e il riquadro dell'output di compilazione indica che la compilazione ha avuto esito positivo.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="Riquadro dell'output di compilazione del pannello Errori con il messaggio di compilazione riuscita di Visual Studio per Mac":::

## <a name="add-a-console-app-to-the-solution"></a>Aggiungere un'app console alla soluzione

Aggiungere un'applicazione console che usa la libreria di classi. L'app chiede all'utente di immettere una stringa e segnala se la stringa inizia con un carattere maiuscolo.

1. Nel riquadro della **soluzione** , fare clic con il <kbd>pulsante destro del</kbd>mouse sulla `ClassLibraryProjects` soluzione. Aggiungere un nuovo progetto di **applicazione console** selezionando il modello dai modelli di app **Web e console**  >  **App** e quindi fare clic su **Avanti**.

1. Selezionare **.NET Core 3,1** come **Framework di destinazione** e selezionare **Avanti**.

1. Denominare il progetto **Showcase**. Scegliere **Crea** per creare il progetto nella soluzione.

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="Aggiungi progetto ShowCase":::

1. Aprire il file *Program.cs* . Sostituire il codice con il codice seguente:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   Il programma richiede all'utente di immettere una stringa. Indica se la stringa inizia con un carattere maiuscolo. Se l'utente preme il tasto <kbd>invio</kbd> senza immettere una stringa, l'applicazione termina e la finestra della console si chiude.

   Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console. Ogni volta che è maggiore o uguale a 25, il codice Cancella la finestra della console e visualizza un messaggio all'utente.

## <a name="add-a-project-reference"></a>Aggiungere un riferimento al progetto

Inizialmente, il nuovo progetto di app console non ha accesso alla libreria di classi. Per consentire la chiamata di metodi nella libreria di classi, creare un riferimento di progetto al progetto libreria di classi.

1. Nel riquadro **soluzioni** , fare clic con il <kbd>pulsante destro del</kbd>mouse sul nodo **dipendenze** del nuovo progetto **Showcase** . Nel menu di scelta rapida selezionare **Aggiungi riferimento**.

1. Nella finestra di dialogo **riferimenti** selezionare **StringLibrary** e quindi fare clic su **OK**.

## <a name="run-the-app"></a>Eseguire l'app

1. fare clic con il <kbd>pulsante destro del</kbd>mouse sul progetto Showcase e scegliere **Esegui progetto** dal menu di scelta rapida.

1. Per provare il programma, immettere le stringhe e premere <kbd>invio</kbd>, quindi premere <kbd>invio</kbd> per uscire.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="Finestra della console di Visual Studio per Mac con l'app in esecuzione":::

## <a name="additional-resources"></a>Risorse aggiuntive

* [Sviluppare librerie con la interfaccia della riga di comando di .NET Core](libraries.md)
* [.NET standard le versioni e le piattaforme supportate](../../standard/net-standard.md).
* [Note sulla versione di Visual Studio 2019 per Mac](/visualstudio/releasenotes/vs2019-mac-relnotes)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione sono stati creati una soluzione e un progetto di libreria e è stato aggiunto un progetto di app console che usa la libreria. Nell'esercitazione successiva si aggiunge un progetto di unit test alla soluzione.

> [!div class="nextstepaction"]
> [Testare una libreria di .NET Standard con .NET Core usando Visual Studio per Mac](testing-library-with-visual-studio-mac.md)

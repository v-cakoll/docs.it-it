---
title: Creare un'applicazione Hello World con .NET Core in Visual StudioCreate a Hello World application with .NET Core in Visual Studio
description: Informazioni su come creare la prima applicazione console .NET Core con Visual Basic o C .
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ba996e4add1cfe44681154b00a6530b1f3e70b37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714004"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a>Esercitazione: Creare la prima applicazione console .NET Core in Visual Studio 2019Tutorial: Create your first .NET Core console application in Visual Studio 2019

In questo articolo viene fornita un'introduzione dettagliata per creare ed eseguire un'applicazione console Hello World .NET Core in Visual Studio 2019. Un'applicazione Hello World viene tradizionalmente utilizzata per introdurre i principianti in un nuovo linguaggio di programmazione. Questo programma visualizza semplicemente la frase "Hello World!" sullo schermo.

## <a name="prerequisites"></a>Prerequisites

- [Visual Studio 2019 versione 16.4 o successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro di **sviluppo multipiattaforma .NET Core** installato. .NET Core 3.1 SDK viene installato automaticamente quando si seleziona questo carico di lavoro.

Per altre informazioni, vedere la sezione [Installare con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) nell'articolo Installare [.NET Core SDK.](../install/sdk.md?pivots=os-windows)

## <a name="create-the-app"></a>Creare l'app

Le istruzioni seguenti creano una semplice applicazione console Hello World:The following instructions create a simple Hello World console application:

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C #](#tab/csharp)

1. Aprire Visual Studio 2019.

1. Creare un nuovo progetto di app console di C .NET Core denominato "HelloWorld".

   1. Nella finestra di avvio scegliere **Crea un nuovo progetto.**

      ![Creare un nuovo pulsante di progetto selezionato nella finestra di avvio di Visual StudioCreate a new project button selected on the Visual Studio start window](./media/with-visual-studio/start-window.png)

   1. Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca. Successivamente, scegliere **C '** dall'elenco linguaggio e quindi scegliere Tutte **le piattaforme** dall'elenco Piattaforma. Scegliere il modello **App console (.NET Core)** e quindi scegliere **Avanti**.

      ![Crea una nuova finestra di progetto con i filtri selezionati](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > Se i modelli .NET Core non vengono visualizzati, è probabile che il carico di lavoro richiesto sia installato. Sotto il messaggio **Non si trova quello che stai cercando?** scegliere il collegamento Installa altri strumenti e **funzionalità.** Verrà aperto il programma di installazione di Visual Studio.The Visual Studio Installer opens. Assicurarsi di avere installato il carico di lavoro di **sviluppo multipiattaforma .NET Core.Make** sure you have the .NET Core cross-platform development workload installed.

   1. Nella pagina **Configura il nuovo progetto** immettere **HelloWorld** nella casella **Nome progetto.** Scegliere quindi **Crea,** quindi Crea .

      ![Configurare la finestra del nuovo progetto con i campi Nome progetto, Percorso e Nome soluzione](./media/with-visual-studio/configure-new-project.png)

   Il modello C# Console Application per .NET Core definisce automaticamente una classe, `Program`, con un singolo metodo, `Main`, che accetta una matrice <xref:System.String> come argomento. `Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione. Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.

   ![Visual Studio e il nuovo progetto HelloWorld](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Aprire Visual Studio 2019.

1. Creare un nuovo progetto di app console di Visual Basic .NET Core denominato "HelloWorld".

   1. Nella finestra di avvio scegliere **Crea un nuovo progetto.**

      ![Creare un nuovo pulsante di progetto selezionato nella finestra di avvio di Visual StudioCreate a new project button selected on the Visual Studio start window](./media/with-visual-studio/start-window.png)

   1. Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca. Scegliere quindi **Visual Basic** dall'elenco Linguaggio, quindi scegliere Tutte le **piattaforme** dall'elenco Piattaforma. Scegliere il modello **App console (.NET Core)** e quindi scegliere **Avanti**.

      ![Scegliere il modello Visual Basic per l'app console (.NET Framework)](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > Se i modelli .NET Core non vengono visualizzati, è probabile che il carico di lavoro richiesto sia installato. Sotto il messaggio **Non si trova quello che stai cercando?** scegliere il collegamento Installa altri strumenti e **funzionalità.** Verrà aperto il programma di installazione di Visual Studio.The Visual Studio Installer opens. Assicurarsi di avere installato il carico di lavoro di **sviluppo multipiattaforma .NET Core.Make** sure you have the .NET Core cross-platform development workload installed.

   1. Nella pagina **Configura il nuovo progetto** immettere **HelloWorld** nella casella **Nome progetto.** Scegliere quindi **Crea,** quindi Crea .

   Il modello di app console per .NET `Program`Core definisce `Main`automaticamente una <xref:System.String> classe, , con un singolo metodo, , che accetta una matrice come argomento. `Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione. Tutti gli argomenti della `args` riga di comando forniti quando viene avviata l'applicazione sono disponibili nel parametro.

   ![Visual Studio e il nuovo progetto HelloWorld](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   Il modello crea una semplice applicazione "Hello World". Chiama il metodo <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> per visualizzare la stringa letterale "Hello World!" nella finestra della console.

## <a name="run-the-app"></a>Eseguire l'app

1. Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.

   ![Barra degli strumenti di Visual Studio con il pulsante Esegui HelloWorld selezionato](./media/with-visual-studio/run-program.png)

   Si apre una finestra della console con il testo "Hello World!" stampate sullo schermo e alcune informazioni di debug di Visual Studio.

   ![Finestra della console con il messaggio Hello World che chiede di premere un tasto qualsiasi per continuare](./media/with-visual-studio/hello-world-console.png)

1. Premere un tasto per chiudere la finestra della console.

## <a name="enhance-the-app"></a>Migliorare l'app

Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e ora. Le seguenti istruzioni modificano ed eseguono nuovamente l'app:

# <a name="c"></a>[C #](#tab/csharp)

1. Sostituire il contenuto `Main` del metodo , che attualmente `Console.WriteLine`è solo la riga che chiama , con il codice seguente:

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   Il codice visualizza "What is your name?" nella console e attende che l'utente inserisca una stringa e prema INVIO. Archivia la stringa in una variabile denominata `name`. Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`. Usa infine una [stringa interpolata](../../csharp/language-reference/tokens/interpolated.md) per visualizzare questi valori nella finestra della console.

1. Compilare il programma scegliendo **Compila** > **soluzione**.

1. Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.

1. Rispondere al prompt immettendo un nome e premendo il tasto **Invio.**

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. Premere un tasto per chiudere la finestra della console.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Sostituire il contenuto `Main` del metodo , che attualmente `Console.WriteLine`è solo la riga che chiama , con il codice seguente:

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   Il codice visualizza "What is your name?" nella console e attende che l'utente inserisca una stringa e prema INVIO. Archivia la stringa in una variabile denominata `name`. Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`. Usa infine una [stringa interpolata](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) per visualizzare questi valori nella finestra della console.

1. Compilare il programma scegliendo **Compila** > **soluzione**.

1. Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.

1. Rispondere al prompt immettendo un nome e premendo il tasto **Invio.**

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. Premere un tasto per chiudere la finestra della console.

---

## <a name="next-steps"></a>Passaggi successivi

In questo articolo è stata creata ed eseguita la prima applicazione .NET Core.In this article, you've created and run your first .NET Core application. Nel passaggio successivo verrà eseguito il debug dell'app.

> [!div class="nextstepaction"]
> [Debug a .NET Core Hello World application in Visual Studio](debugging-with-visual-studio.md)

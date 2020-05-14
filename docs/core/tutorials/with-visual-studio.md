---
title: Creare un'applicazione Hello World con .NET Core in Visual Studio
description: Informazioni su come creare la prima applicazione console .NET Core con C# o Visual Basic con Visual Studio.
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 738fc49a820c3c5d94fb35c1bf7a8b718ed75cb3
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394831"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a>Esercitazione: creare la prima applicazione console .NET Core in Visual Studio 2019

Questo articolo fornisce un'introduzione dettagliata per creare ed eseguire un'applicazione console Hello World .NET Core in Visual Studio 2019. Un'applicazione Hello World viene tradizionalmente utilizzata per introdurre i principianti di un nuovo linguaggio di programmazione. Questo programma visualizza semplicemente la frase "Hello World!" sullo schermo.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019 versione 16,4 o una versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro **sviluppo multipiattaforma .NET Core** installato. .NET Core 3,1 SDK viene installato automaticamente quando si seleziona questo carico di lavoro.

Per ulteriori informazioni, vedere la sezione [install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) nell'articolo [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) .

## <a name="create-the-app"></a>Creare l'app

Le istruzioni seguenti creano una semplice applicazione console Hello World:

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

1. Aprire Visual Studio 2019.

1. Creare un nuovo progetto di app console .NET Core C# denominato "HelloWorld".

   1. Nella finestra Start scegliere **Crea un nuovo progetto**.

      ![Pulsante Crea un nuovo progetto selezionato nella finestra di avvio di Visual Studio](./media/with-visual-studio/start-window.png)

   1. Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca. Scegliere quindi **C#** dall'elenco lingua, quindi scegliere **tutte le piattaforme** dall'elenco piattaforma. Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.

      ![Crea una nuova finestra del progetto con i filtri selezionati](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > Se non vengono visualizzati i modelli .NET Core, probabilmente manca il carico di lavoro richiesto installato. Nel messaggio **non trovare ciò che si sta cercando?** scegliere il collegamento **Installa altri strumenti e funzionalità** . Verrà visualizzata la Programma di installazione di Visual Studio. Assicurarsi che sia installato il carico di lavoro **sviluppo multipiattaforma .NET Core** .

   1. Nella pagina **Configura nuovo progetto** immettere **HelloWorld** nella casella **nome progetto** . Quindi scegliere **Crea**.

      ![Configurare la finestra nuovo progetto con i campi nome progetto, percorso e nome soluzione](./media/with-visual-studio/configure-new-project.png)

   Il modello C# Console Application per .NET Core definisce automaticamente una classe, `Program`, con un singolo metodo, `Main`, che accetta una matrice <xref:System.String> come argomento. `Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione. Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.

   ![Visual Studio e il nuovo progetto HelloWorld](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Aprire Visual Studio 2019.

1. Creare un nuovo progetto di app console di Visual Basic .NET Core denominato "HelloWorld".

   1. Nella finestra Start scegliere **Crea un nuovo progetto**.

      ![Pulsante Crea un nuovo progetto selezionato nella finestra di avvio di Visual Studio](./media/with-visual-studio/start-window.png)

   1. Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca. Successivamente, scegliere **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma. Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.

      ![Scegliere il modello Visual Basic per l'app console (.NET Framework)](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > Se non vengono visualizzati i modelli .NET Core, probabilmente manca il carico di lavoro richiesto installato. Nel messaggio **non trovare ciò che si sta cercando?** scegliere il collegamento **Installa altri strumenti e funzionalità** . Verrà visualizzata la Programma di installazione di Visual Studio. Assicurarsi che sia installato il carico di lavoro **sviluppo multipiattaforma .NET Core** .

   1. Nella pagina **Configura nuovo progetto** immettere **HelloWorld** nella casella **nome progetto** . Quindi scegliere **Crea**.

   Il modello di app console per .NET Core definisce automaticamente una classe, `Program` , con un singolo metodo, `Main` , che accetta una <xref:System.String> matrice come argomento. `Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione. Qualsiasi argomento della riga di comando fornito quando viene avviata l'applicazione è disponibile nel `args` parametro.

   ![Visual Studio e il nuovo progetto HelloWorld](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   Il modello crea una semplice applicazione "Hello World". Chiama il metodo <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> per visualizzare la stringa letterale "Hello World!" nella finestra della console.

## <a name="run-the-app"></a>Eseguire l'app

1. Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.

   ![Barra degli strumenti di Visual Studio con il pulsante di esecuzione HelloWorld selezionato](./media/with-visual-studio/run-program.png)

   Viene visualizzata una finestra della console con il testo "Hello World!" stampato sullo schermo e alcune informazioni di debug di Visual Studio.

   ![Finestra della console con il messaggio Hello World che chiede di premere un tasto qualsiasi per continuare](./media/with-visual-studio/hello-world-console.png)

1. Premere un tasto per chiudere la finestra della console.

## <a name="enhance-the-app"></a>Migliorare l'app

Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e ora. Le istruzioni seguenti modificano ed eseguono di nuovo l'app:

# <a name="c"></a>[C#](#tab/csharp)

1. Sostituire il contenuto del `Main` metodo, che attualmente è solo la riga che chiama `Console.WriteLine` , con il codice seguente:

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/HelloWorld.cs#1)]

   Il codice visualizza "What is your name?" nella console e attende che l'utente inserisca una stringa e prema INVIO. Archivia la stringa in una variabile denominata `name`. Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`. Usa infine una [stringa interpolata](../../csharp/language-reference/tokens/interpolated.md) per visualizzare questi valori nella finestra della console.

1. Compilare il programma scegliendo **Compila**  >  **compilazione soluzione**.

1. Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.

1. Per rispondere alla richiesta, immettere un nome e premere il tasto **invio** .

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. Premere un tasto per chiudere la finestra della console.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Sostituire il contenuto del `Main` metodo, che attualmente è solo la riga che chiama `Console.WriteLine` , con il codice seguente:

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/Program.vb#1)]

   Il codice visualizza "What is your name?" nella console e attende che l'utente inserisca una stringa e prema INVIO. Archivia la stringa in una variabile denominata `name`. Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`. Usa infine una [stringa interpolata](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) per visualizzare questi valori nella finestra della console.

1. Compilare il programma scegliendo **Compila**  >  **compilazione soluzione**.

1. Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.

1. Per rispondere alla richiesta, immettere un nome e premere il tasto **invio** .

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. Premere un tasto per chiudere la finestra della console.

---

## <a name="next-steps"></a>Passaggi successivi

In questo articolo è stata creata ed eseguita la prima applicazione .NET Core. Nel passaggio successivo verrà eseguito il debug dell'applicazione.

> [!div class="nextstepaction"]
> [Eseguire il debug di un'applicazione Hello World .NET Core in Visual Studio](debugging-with-visual-studio.md)

---
title: Compilazione di un'applicazione Hello World con .NET Core e Visual Basic in Visual Studio 2017
description: Informazioni su come compilare una semplice applicazione console .NET Core con Visual Basic usando Visual Studio 2017.
keywords: .NET Core, applicazione console .NET Core, Visual Studio 2017
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-vb
dev_langs: vb
ms.openlocfilehash: 3ff4681f06da06533db5e8e2ce2498a31604bdb7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="build-a-visual-basic-hello-world-application-with-net-core-in-visual-studio-2017"></a>Compilare un'applicazione Hello World in Visual Basic con .NET Core in Visual Studio 2017

Questo argomento offre un'introduzione dettagliata per la compilazione, il debug e la pubblicazione di una semplice applicazione console .NET Core usando Visual Basic in Visual Studio 2017. Visual Studio 2017 offre un ambiente di sviluppo completo per la creazione di applicazioni .NET Core. Se l'applicazione non ha alcuna dipendenza specifica della piattaforma, è possibile eseguirla su qualsiasi piattaforma usata come destinazione da .NET Core o su qualsiasi sistema in cui è installato .NET Core.

## <a name="prerequisites"></a>Prerequisiti

[Visual Studio 2017](https://www.visualstudio.com/downloads/) con il carico di lavoro "Sviluppo multipiattaforma .NET Core" installato. È possibile sviluppare l'app con .NET Core 2.0.

Per altre informazioni, vedere [Prerequisiti per .NET Core in Windows](../../core/windows-prerequisites.md).

## <a name="a-simple-hello-world-application"></a>Semplice applicazione Hello World

Di seguito viene descritta la creazione di una semplice applicazione console "Hello World". Attenersi ai passaggi riportati di seguito.

1. Avviare Visual Studio 2017. Selezionare **File** > **Nuovo** > **Progetto** dalla barra dei menu. Nella finestra di dialogo *Nuovo progetto** selezionare il nodo **Visual Basic** aggiungendo il nodo **.NET Core**. Selezionare quindi il modello di progetto **App console (.NET Core)**. Nella casella di testo **Nome** digitare "HelloWorld". Selezionare il pulsante **OK** .

   ![Finestra di dialogo Nuovo progetto con App console selezionata](./media/vb-with-visual-studio/new-project.png)
   
1. Visual Studio usa il modello per creare il progetto. Il modello App console di Visual Basic per .NET Core definisce automaticamente una classe, `Program`, con un singolo metodo, `Main` che accetta una matrice <xref:System.String> come argomento. `Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione. Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.

   ![Visual Studio e il nuovo progetto HelloWorld](./media/vb-with-visual-studio/devenv.png)

   Il modello crea una semplice applicazione "Hello World". Chiama il metodo <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> per visualizzare la stringa letterale "Hello World!" nella finestra della console. Facendo clic sul pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti è possibile eseguire il programma in modalità debug. Se si esegue questa operazione, la finestra della console rimane visibile solo per un intervallo di tempo molto breve. Questo si verifica perché il metodo `Main` termina e l'applicazione viene chiusa non appena viene eseguita l'unica istruzione del metodo `Main`.

1. Per impostare l'applicazione in modo che sospenda la finestra della console prima di chiuderla, aggiungere il codice seguente immediatamente dopo la chiamata al metodo <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>:

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   Il codice chiede all'utente di premere un tasto qualsiasi e quindi sospende il programma fino a quando non viene premuto un tasto.

1. Nella barra dei menu selezionare **Compila** > **Compila soluzione**. Il programma viene compilato in un linguaggio intermedio (IL) che viene successivamente convertito in codice binario da un compilatore JIT (Just-In-Time).

1. Eseguire il programma facendo clic sul pulsante **HelloWorld** con la freccia verde sulla barra degli strumenti.

   ![Finestra della console con il messaggio Hello World che chiede di premere un tasto qualsiasi per continuare](./media/with-visual-studio/helloworld1.png)

1. Premere un tasto qualsiasi per chiudere la finestra della console.

## <a name="enhancing-the-hello-world-application"></a>Miglioramento dell'applicazione Hello World

Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora. Per modificare e testare il programma, seguire questa procedura:

1. Immettere il codice Visual Basic seguente nella finestra del codice immediatamente dopo la parentesi quadra di apertura che segue la riga `Sub Main(args As String())` e prima della prima parentesi quadra di chiusura:

   [!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   Questo codice sostituisce le istruzioni <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, <xref:System.Console.Write%2A?displayProperty=nameWithType> e <xref:System.Console.ReadKey%2A?displayProperty=nameWithType> esistenti.

   ![File di programma Visual Studio con il metodo Main aggiornato](./media/vb-with-visual-studio/codewindow.png)

   Il codice visualizza "What is your name?" nella console e attende che l'utente inserisca una stringa e prema INVIO. Archivia la stringa in una variabile denominata `name`. Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `currentDate`. Usa infine una [stringa interpolata](../../csharp/language-reference/keywords/interpolated-strings.md) per visualizzare questi valori nella finestra della console.

1. Compilare il programma scegliendo **Compila** > **Compila soluzione**.

1. Eseguire il programma in modalità debug in Visual Studio selezionando la freccia verde sulla barra degli strumenti, premendo F5 oppure scegliendo la voce di menu **Debug** > **Avvia debug**. Rispondere alla richiesta immettendo un nome e premendo il tasto INVIO.

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/helloworld2.png)

1. Premere un tasto qualsiasi per chiudere la finestra della console.

L'applicazione è stata creata ed eseguita. Per sviluppare un'applicazione professionale, eseguire alcuni passaggi aggiuntivi per rendere un'applicazione pronta per il rilascio:

- Per altre informazioni sul debug dell'applicazione, vedere [Debug dell'applicazione C# Hello World con Visual Studio 2017](debugging-with-visual-studio.md).

- Per informazioni sullo sviluppo e la pubblicazione di una versione distribuibile dell'applicazione, vedere [Publishing your C# Hello World application with Visual Studio 2017](publishing-with-visual-studio.md) (Pubblicazione dell'applicazione Hello World usando C# con Visual Studio 2017).

<!--
## Related topics

Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017. For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).

You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor. For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md). -->

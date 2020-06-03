---
title: Creare un'applicazione console con .NET Core in Visual Studio
description: Informazioni su come creare un'applicazione console .NET Core con C# o Visual Basic con Visual Studio.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 144d7bb087034839ad2cde2fa28a4961cff4321f
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306994"
---
# <a name="tutorial-create-a-net-core-console-application-in-visual-studio-2019"></a>Esercitazione: creare un'applicazione console .NET Core in Visual Studio 2019

Questa esercitazione illustra come creare ed eseguire un'applicazione console .NET Core in Visual Studio 2019.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019 versione 16,6 o una versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro **sviluppo multipiattaforma .NET Core** installato. .NET Core 3,1 SDK viene installato automaticamente quando si seleziona questo carico di lavoro.

  Per ulteriori informazioni, vedere la sezione [install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) nell'articolo [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) .

## <a name="create-the-app"></a>Creare l'app

<!-- markdownlint-disable MD025 -->

1. Aprire Visual Studio 2019.

1. Creare un nuovo progetto di app console .NET Core denominato "HelloWorld".

   1. Nella pagina iniziale scegliere **Crea un nuovo progetto**.

      ![Pulsante Crea un nuovo progetto selezionato nella pagina iniziale di Visual Studio](./media/with-visual-studio/start-window.png)

   1. Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca. Successivamente, scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma. Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.

      ![Crea una nuova finestra del progetto con i filtri selezionati](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > Se i modelli .NET Core non sono visibili, probabilmente manca il carico di lavoro richiesto. Nel messaggio **non trovare ciò che si sta cercando?** scegliere il collegamento **Installa altri strumenti e funzionalità** . Verrà visualizzata la Programma di installazione di Visual Studio. Assicurarsi che sia installato il carico di lavoro **sviluppo multipiattaforma .NET Core** .

   1. Nella pagina **Configura nuovo progetto** immettere **HelloWorld** nella casella **nome progetto** . Scegli quindi **Crea**.

      ![Configurare la finestra nuovo progetto con i campi nome progetto, percorso e nome soluzione](./media/with-visual-studio/configure-new-project.png)

   Il modello di applicazione console per .NET Core definisce una classe, `Program` , con un singolo metodo, `Main` , che accetta una <xref:System.String> matrice come argomento. `Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione. Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.

   Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.

   ```csharp
   using System;

   namespace HelloWorld
   {
       class Program
       {
           static void Main(string[] args)
           {
               Console.WriteLine("Hello World!");
           }
       }
   }
   ```

   ```vb
   Imports System

   Module Program
       Sub Main(args As String())
           Console.WriteLine("Hello World!")
       End Sub
   End Module
   ```

   Il modello crea una semplice applicazione "Hello World". Chiama il <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> metodo per visualizzare "Hello World!" nella finestra della console.

## <a name="run-the-app"></a>Eseguire l'app

1. Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.

   ![Barra degli strumenti di Visual Studio con il pulsante di esecuzione HelloWorld selezionato](./media/with-visual-studio/run-program.png)

   Viene visualizzata una finestra della console con il testo "Hello World!" stampato sullo schermo e alcune informazioni di debug di Visual Studio.

   ![Finestra della console con il messaggio Hello World che chiede di premere un tasto qualsiasi per continuare](./media/with-visual-studio/hello-world-console.png)

1. Premere un tasto per chiudere la finestra della console.

## <a name="enhance-the-app"></a>Migliorare l'app

Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora. Le istruzioni seguenti modificano l'app ed eseguono di nuovo l'app:

1. Sostituire il contenuto del `Main` metodo, che attualmente è solo la riga che chiama `Console.WriteLine` , con il codice seguente:

   [!code-csharp[GettingStarted#1](./snippets/with-visual-studio/csharp/Program.cs#1)]
   [!code-vb[GettingStarted#1](./snippets/with-visual-studio/vb/Program.vb#1)]

   Il codice visualizza "What is your name?" nella console e attende che l'utente inserisca una stringa e prema INVIO. Archivia la stringa in una variabile denominata `name` . Recupera inoltre il valore della <xref:System.DateTime.Now?displayProperty=nameWithType> proprietà che contiene l'ora locale corrente e la assegna a una variabile denominata `date` ( `currentDate` in Visual Basic). Infine, questi valori vengono visualizzati nella finestra della console.

   `\n`( `vbCrLf` In Visual Basic) rappresenta un carattere di nuova riga.

   Il segno di dollaro ( `$` ) davanti a una stringa consente di inserire espressioni come i nomi delle variabili tra parentesi graffe nella stringa. Il valore dell'espressione viene inserito nella stringa al posto dell'espressione. Questa sintassi è detta [stringhe interpolate](../../csharp/language-reference/tokens/interpolated.md).

1. Per eseguire il programma, scegliere **HelloWorld** sulla barra degli strumenti oppure premere **F5**.

1. Per rispondere alla richiesta, immettere un nome e premere il tasto **invio** .

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. Premere un tasto per chiudere la finestra della console.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata creata un'applicazione .NET Core. Nell'esercitazione successiva si esegue il debug dell'app.

> [!div class="nextstepaction"]
> [Eseguire il debug di un'applicazione console .NET Core in Visual Studio](debugging-with-visual-studio.md)

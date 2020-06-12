---
title: Creare un'applicazione console .NET Core usando Visual Studio Code
description: Informazioni su come creare un'applicazione console .NET Core usando Visual Studio Code e il interfaccia della riga di comando di .NET Core.
ms.date: 05/22/2020
ms.openlocfilehash: 6d8f9adb2f77dbfd2d1cf54c80f1cdea582b1d96
ms.sourcegitcommit: f6350c2c542e6edd52d7e9d6667b96d85d810e67
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84717510"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-code"></a>Esercitazione: creare un'applicazione console .NET Core usando Visual Studio Code

In questa esercitazione viene illustrato come creare ed eseguire un'applicazione console .NET Core utilizzando Visual Studio Code e il interfaccia della riga di comando di .NET Core. Le attività del progetto, come la creazione, la compilazione e l'esecuzione di un progetto, vengono eseguite utilizzando la interfaccia della riga di comando di .NET Core. È possibile seguire questa esercitazione con un editor di codice diverso ed eseguire comandi in un terminale, se si preferisce.

## <a name="prerequisites"></a>Prerequisiti

1. [Visual Studio Code](https://code.visualstudio.com/) con l' [estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installata. Per informazioni su come installare le estensioni in Visual Studio Code, vedere [vs code Marketplace di estensione](https://code.visualstudio.com/docs/editor/extension-gallery).
2. [.NET Core 3,1 SDK o versione successiva](https://dotnet.microsoft.com/download)

## <a name="create-the-app"></a>Creare l'app

Creare un progetto di app console .NET Core denominato "HelloWorld".

1. Avviare Visual Studio Code.

1. Selezionare **file**  >  **Apri cartella** (**file**  >  **Apri...** in MacOS) dal menu principale.

1. Nella finestra di dialogo **Apri cartella** creare una cartella *HelloWorld* e fare clic su **Seleziona cartella** (**Apri** in MacOS).

   Per impostazione predefinita, il nome della cartella diventa il nome del progetto e il nome dello spazio dei nomi. Si aggiungerà il codice più avanti nell'esercitazione che presuppone che lo spazio dei nomi del progetto sia `HelloWorld` .

1. Aprire il **terminale** in Visual Studio Code selezionando **Visualizza**  >  **terminale** dal menu principale.

   Il **terminale** verrà aperto con il prompt dei comandi nella cartella *HelloWorld* .

1. Nel **terminale**immettere il comando seguente:

   ```dotnetcli
   dotnet new console
   ```

Il modello crea una semplice applicazione "Hello World". Chiama il <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> metodo per visualizzare "Hello World!" nella finestra della console.

Il codice del modello definisce una classe, `Program` , con un singolo metodo, `Main` , che accetta una <xref:System.String> matrice come argomento:

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

`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione. Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.

## <a name="run-the-app"></a>Eseguire l'app

Eseguire il comando seguente nel **terminale**:

```dotnetcli
dotnet run
```

Il programma Visualizza "Hello World!" e termina.

![Comando run di dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a>Migliorare l'app

Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora.

1. Aprire il file *Program.cs* facendo clic su di esso.

   La prima volta che si apre un file C# in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) viene caricato nell'editor.

   ![Aprire il file Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. Selezionare **Sì** quando Visual Studio Code richiede di aggiungere le risorse mancanti per compilare ed eseguire il debug dell'app.

   ![Richiesta delle risorse mancanti](media/with-visual-studio-code/missing-assets.png)

1. Sostituire il contenuto del `Main` metodo in *Program.cs*, che è la riga che chiama `Console.WriteLine` , con il codice seguente:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="1":::

   Il codice visualizza "What is your name?" nella finestra della console e attende che l'utente immetta una stringa seguita dal tasto <kbd>invio</kbd> . Archivia la stringa in una variabile denominata `name` . Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`. Infine, questi valori vengono visualizzati nella finestra della console.

   L'oggetto `\n` rappresenta un carattere di nuova riga.

   Il segno di dollaro ( `$` ) davanti a una stringa consente di inserire espressioni come i nomi delle variabili tra parentesi graffe nella stringa. Il valore dell'espressione viene inserito nella stringa al posto dell'espressione. Questa sintassi è detta [stringhe interpolate](../../csharp/language-reference/tokens/interpolated.md).

1. Salvare le modifiche.

   > [!IMPORTANT]
   > In Visual Studio Code, è necessario salvare in modo esplicito le modifiche. Diversamente da Visual Studio, le modifiche ai file non vengono salvate automaticamente durante la compilazione e l'esecuzione di un'app.

1. Eseguire di nuovo il programma:

   ```dotnetcli
   dotnet run
   ```

1. Per rispondere alla richiesta, immettere un nome e premere il tasto <kbd>invio</kbd> .

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Finestra del terminale con output del programma modificato":::

1. Premere un tasto qualsiasi per uscire dal programma.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Setting up Visual Studio Code (Impostazione di Visual Studio Code)](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata creata un'applicazione console .NET Core. Nell'esercitazione successiva si esegue il debug dell'app.

> [!div class="nextstepaction"]
> [Eseguire il debug di un'applicazione console .NET Core usando Visual Studio Code](debugging-with-visual-studio-code.md)

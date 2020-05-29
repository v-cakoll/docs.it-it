---
title: Creare un'applicazione console con .NET Core usando Visual Studio Code
description: Informazioni su come creare un'applicazione console .NET Core usando Visual Studio Code e il interfaccia della riga di comando di .NET Core.
ms.date: 05/22/2020
ms.openlocfilehash: 673c4a639a2cab26261b7cdafd5d8e20acfafb94
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201692"
---
# <a name="tutorial-create-a-console-application-with-net-core-using-visual-studio-code"></a>Esercitazione: creare un'applicazione console con .NET Core usando Visual Studio Code

In questa esercitazione viene illustrato come creare ed eseguire un'applicazione console .NET Core utilizzando Visual Studio Code e il interfaccia della riga di comando di .NET Core. Le attività del progetto, come la creazione, la compilazione e l'esecuzione di un progetto, vengono eseguite usando l'interfaccia della riga di comando, quindi è possibile seguire questa esercitazione con un editor di codice diverso ed eseguire comandi in un terminale, se lo si preferisce.

## <a name="prerequisites"></a>Prerequisiti

1. [Visual Studio Code](https://code.visualstudio.com/) con l' [estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installata. Per informazioni su come installare le estensioni in Visual Studio Code, vedere [vs code Marketplace di estensione](https://code.visualstudio.com/docs/editor/extension-gallery).
2. [.NET Core 3,1 SDK o versione successiva](https://dotnet.microsoft.com/download)

## <a name="create-the-app"></a>Creare l'app

1. Aprire Visual Studio Code.

1. Creare un progetto.

   1. Selezionare **file**  >  **Apri cartella** / **Apri...** dal menu principale, creare una cartella *HelloWorld* , quindi fare clic su **Seleziona cartella** / **Apri**.

      Per impostazione predefinita, il nome della cartella diventa il nome del progetto e il nome dello spazio dei nomi. Si aggiungerà il codice più avanti nell'esercitazione che presuppone che lo spazio dei nomi del progetto sia `HelloWorld` .

   1. Aprire il **terminale** in Visual Studio Code selezionando **Visualizza**  >  **terminale** dal menu principale.

      Il **terminale** verrà aperto con il prompt dei comandi nella cartella *HelloWorld* .

   1. Nel **terminale**immettere il comando seguente:

      ```dotnetcli
      dotnet new console
      ```

Il modello di applicazione console per .NET Core definisce una classe, `Program` , con un singolo metodo, `Main` , che accetta una <xref:System.String> matrice come argomento. Il file *Program.cs* contiene il codice seguente:

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

Il modello crea un'applicazione semplice che chiama il <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> metodo per visualizzare "Hello World!" nella finestra della console.

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

1. Sostituire il contenuto del `Main` metodo in *Program.cs*, che attualmente è solo la riga che chiama `Console.WriteLine` , con il codice seguente:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   Il codice visualizza "What is your name?" nella finestra della console e attende che l'utente immetta una stringa seguita dal tasto **invio** . Archivia la stringa in una variabile denominata `name` . Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`. Infine, questi valori vengono visualizzati nella finestra della console.

   L'oggetto `\n` rappresenta un carattere di nuova riga.

   Il segno di dollaro ( `$` ) davanti a una stringa consente di inserire espressioni come i nomi delle variabili tra parentesi graffe nella stringa. Il valore dell'espressione viene inserito nella stringa al posto dell'espressione. Questa sintassi è detta [stringhe interpolate](../../csharp/language-reference/tokens/interpolated.md).

1. Salvare le modifiche.

   > [!IMPORTANT]
   > In Visual Studio Code, è necessario salvare in modo esplicito le modifiche. Diversamente da Visual Studio, le modifiche ai file non vengono salvate automaticamente durante la compilazione e l'esecuzione di un'app.

1. Eseguire di nuovo il programma:

   ```dotnetcli
   dotnet run
   ```

1. Per rispondere alla richiesta, immettere un nome e premere il tasto **invio** .

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Finestra del terminale con output del programma modificato":::

1. Premere un tasto qualsiasi per uscire dal programma.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Setting up Visual Studio Code (Impostazione di Visual Studio Code)](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata creata un'applicazione .NET Core. Nell'esercitazione successiva si esegue il debug dell'app.

> [!div class="nextstepaction"]
> [Eseguire il debug di un'applicazione console .NET Core usando Visual Studio Code](debugging-with-visual-studio-code.md)

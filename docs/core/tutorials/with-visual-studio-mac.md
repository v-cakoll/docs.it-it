---
title: Creare un'applicazione console .NET Core usando Visual Studio per Mac
description: Informazioni su come creare un'applicazione console .NET Core usando Visual Studio per Mac.
ms.date: 06/02/2020
ms.openlocfilehash: 9cab838eaab2c59d8a0270267514f57acb7c60fb
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "84811661"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-for-mac"></a>Esercitazione: creare un'applicazione console .NET Core usando Visual Studio per Mac

In questa esercitazione viene illustrato come creare ed eseguire un'applicazione console .NET Core utilizzando Visual Studio per Mac.

> [!NOTE]
> Microsoft considera di fondamentale importanza i commenti e i suggerimenti degli utenti. Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:
>
> * In Visual Studio per Mac selezionare **Guida**  >  **segnala un problema** dal menu o **segnala un problema** dalla schermata iniziale, che consente di aprire una finestra per la presentazione di un report sui bug. È possibile tenere traccia dei commenti e dei suggerimenti inviati nel portale della [community di sviluppatori](https://developercommunity.visualstudio.com/spaces/8/index.html).
> * Per inviare un suggerimento, scegliere **Guida**dal menu o fornire un suggerimento dalla  >  **Provide a Suggestion** schermata iniziale, che consente di passare alla [pagina Web della community di sviluppatori Visual Studio per Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41). **Provide a Suggestion**

## <a name="prerequisites"></a>Prerequisiti

* [Visual Studio per Mac versione 8,6 o successiva](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Selezionare l'opzione per installare .NET Core. L'installazione di Novell è facoltativa per lo sviluppo di .NET Core. Per altre informazioni, vedere le seguenti risorse:

  * [Esercitazione: installare Visual Studio per Mac](/visualstudio/mac/installation).
  * [Versioni di MacOS supportate](../install/dependencies.md?pivots=os-macos).
  * [Versioni di .NET Core supportate da Visual Studio per Mac](/visualstudio/mac/net-core-support).

## <a name="create-the-app"></a>Creare l'app

Creare un progetto di app console .NET Core denominato "HelloWorld".

1. Avviare Visual Studio per Mac.

1. Selezionare **nuovo** nella finestra di avvio.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Pulsante Nuovo nella schermata iniziale di Visual Studio per Mac":::

1. Nella finestra di dialogo **nuovo progetto** selezionare **app** nel nodo **Web e console** . Selezionare il modello **applicazione console** e fare clic su **Avanti**.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Nuovo elenco di modelli di progetto":::

1. Nell'elenco a discesa **Framework di destinazione** della finestra di dialogo **Configura nuova applicazione console** Selezionare **.NET Core 3,1**, quindi fare clic su **Avanti**.

   :::image type="content" source="media/with-visual-studio-mac/target-framework.png" alt-text="Selezionare il Framework di destinazione":::

1. Digitare "HelloWorld" per il **nome del progetto**e selezionare **Crea**.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Finestra di dialogo di configurazione della nuova applicazione console":::

Il modello crea una semplice applicazione "Hello World". Chiama il <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> metodo per visualizzare "Hello World!" nella finestra del terminale.

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

`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione. Gli eventuali argomenti della riga di comando forniti quando viene avviata l'applicazione sono disponibili nella `args` matrice.

## <a name="run-the-app"></a>Eseguire l'app

1. Premere <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opzione</kbd> + <kbd>comando</kbd> + <kbd>invio</kbd>) per eseguire l'app senza debug.

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="Il terminale Mostra Hello World!":::

1. Chiudere la finestra del **terminale** .

## <a name="enhance-the-app"></a>Migliorare l'app

Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora.

1. In *Program.cs*sostituire il contenuto del `Main` metodo, ovvero la riga che chiama `Console.WriteLine` , con il codice seguente:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   Il codice visualizza "What is your name?" nella finestra della console e attende che l'utente immetta una stringa seguita dal tasto <kbd>invio</kbd> . Archivia la stringa in una variabile denominata `name` . Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`. Infine, questi valori vengono visualizzati nella finestra della console.

   L'oggetto `\n` rappresenta un carattere di nuova riga.

   Il segno di dollaro ( `$` ) davanti a una stringa consente di inserire espressioni come i nomi delle variabili tra parentesi graffe nella stringa. Il valore dell'espressione viene inserito nella stringa al posto dell'espressione. Questa sintassi è detta [stringhe interpolate](../../csharp/language-reference/tokens/interpolated.md).

1. Premere <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opzione</kbd> + <kbd>comando</kbd> + <kbd>invio</kbd>) per eseguire l'app.

1. Per rispondere alla richiesta, immettere un nome e premere <kbd>invio</kbd>.

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Il terminale Mostra l'output del programma modificato":::

1. Chiudere il terminale.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata creata un'applicazione console .NET Core. Nell'esercitazione successiva si esegue il debug dell'app.

> [!div class="nextstepaction"]
> [Eseguire il debug di un'applicazione console .NET Core in Visual Studio](debugging-with-visual-studio-mac.md)

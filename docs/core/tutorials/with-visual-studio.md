---
title: Creare un'applicazione console .NET Core con Visual Studio
description: Informazioni su come creare un'applicazione console .NET Core con C# o Visual Basic con Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 3c8fc7c4702b786c05e14397dc36d994c77e114d
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "84811659"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio"></a>Esercitazione: creare un'applicazione console .NET Core con Visual Studio

Questa esercitazione illustra come creare ed eseguire un'applicazione console .NET Core in Visual Studio 2019.

## <a name="prerequisites"></a>Prerequisiti

- [Visual Studio 2019 versione 16,6 o una versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro **sviluppo multipiattaforma .NET Core** installato. .NET Core 3,1 SDK viene installato automaticamente quando si seleziona questo carico di lavoro.

  Per altre informazioni, vedere [installare il .NET Core SDK con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio).

## <a name="create-the-app"></a>Creare l'app

Creare un progetto di app console .NET Core denominato "HelloWorld".

1. Avviare Visual Studio 2019.

1. Nella pagina iniziale scegliere **Crea un nuovo progetto**.

   ![Pulsante Crea un nuovo progetto selezionato nella pagina iniziale di Visual Studio](./media/with-visual-studio/start-window.png)

1. Nella pagina **Crea un nuovo progetto** immettere **console** nella casella di ricerca. Successivamente, scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma. Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.

   ![Crea una nuova finestra del progetto con i filtri selezionati](./media/with-visual-studio/create-new-project.png)

   > [!TIP]
   > Se i modelli .NET Core non sono visibili, probabilmente manca il carico di lavoro richiesto. Nel messaggio **non trovare ciò che si sta cercando?** scegliere il collegamento **Installa altri strumenti e funzionalità** . Verrà visualizzata la Programma di installazione di Visual Studio. Assicurarsi che sia installato il carico di lavoro **sviluppo multipiattaforma .NET Core** .

1. Nella finestra di dialogo **Configura nuovo progetto** immettere **HelloWorld** nella casella **nome progetto** . Scegli quindi **Crea**.

   ![Configurare la finestra nuovo progetto con i campi nome progetto, percorso e nome soluzione](./media/with-visual-studio/configure-new-project.png)

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

```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine("Hello World!")
    End Sub
End Module
```

`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione. Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.

Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.

## <a name="run-the-app"></a>Eseguire l'app

1. Premere <kbd>MAIUSC</kbd> + <kbd>F5</kbd> per eseguire il programma senza debug.

   Viene visualizzata una finestra della console con il testo "Hello World!" stampato sullo schermo e alcune informazioni di debug di Visual Studio.

   ![Finestra della console con il messaggio Hello World che chiede di premere un tasto qualsiasi per continuare](./media/with-visual-studio/hello-world-console.png)

1. Premere un tasto per chiudere la finestra della console.

## <a name="enhance-the-app"></a>Migliorare l'app

Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora.

1. In *Program.cs* o *Program. vb*sostituire il contenuto del `Main` metodo, ovvero la riga che chiama `Console.WriteLine` , con il codice seguente:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   Il codice visualizza "What is your name?" nella finestra della console e attende che l'utente immetta una stringa seguita dal tasto <kbd>invio</kbd> . Archivia la stringa in una variabile denominata `name` . Recupera inoltre il valore della <xref:System.DateTime.Now?displayProperty=nameWithType> proprietà che contiene l'ora locale corrente e la assegna a una variabile denominata `date` ( `currentDate` in Visual Basic). Infine, questi valori vengono visualizzati nella finestra della console.

   `\n`( `vbCrLf` In Visual Basic) rappresenta un carattere di nuova riga.

   Il segno di dollaro ( `$` ) davanti a una stringa consente di inserire espressioni come i nomi delle variabili tra parentesi graffe nella stringa. Il valore dell'espressione viene inserito nella stringa al posto dell'espressione. Questa sintassi è detta [stringhe interpolate](../../csharp/language-reference/tokens/interpolated.md).

1. Premere <kbd>MAIUSC</kbd> + <kbd>F5</kbd> per eseguire il programma senza debug.

1. Per rispondere alla richiesta, immettere un nome e premere il tasto <kbd>invio</kbd> .

   ![Finestra della console con output del programma modificato](./media/with-visual-studio/hello-world-update.png)

1. Premere un tasto per chiudere la finestra della console.

## <a name="next-steps"></a>Passaggi successivi

In questa esercitazione è stata creata un'applicazione console .NET Core. Nell'esercitazione successiva si esegue il debug dell'app.

> [!div class="nextstepaction"]
> [Eseguire il debug di un'applicazione console .NET Core in Visual Studio](debugging-with-visual-studio.md)

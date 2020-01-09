---
title: Hello World--il primo programma con Visual Studio in Windows o Mac- C# Guida alla programmazione
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 910fa4af1b4e45ce627b589a06910dc168490047
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712143"
---
# <a name="hello-world----your-first-program"></a>Hello World--il primo programma

In questo articolo si userà Visual Studio per creare la tradizionale "Hello World!" tradizionale. Visual Studio è un ambiente di sviluppo integrato (IDE) professionale con molte funzionalità progettate per lo sviluppo in .NET. Per creare questo programma, verranno usate solo alcune delle funzionalità di Visual Studio. Per ulteriori informazioni su Visual Studio, vedere [Introduzione con Visual C# ](/visualstudio/ide/quickstart-csharp-console).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a>Creare una nuova applicazione

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

Avviare Visual Studio. In Windows verrà visualizzata l'immagine seguente:

![Schermata iniziale di Visual Studio in Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

Selezionare **Crea un nuovo progetto** nell'angolo in basso a destra dell'immagine. Visual Studio Visualizza la finestra di dialogo **nuovo progetto** :

![Schermata nuovo progetto di Visual Studio in Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> Se è la prima volta che si avvia Visual Studio, l'elenco dei **modelli di progetto recenti** è vuoto.

Nella finestra di dialogo nuovo progetto scegliere "app console (.NET Core)" e quindi fare clic su **Avanti**. Assegnare un nome al progetto, ad esempio "HelloWorld", quindi fare clic su **Crea**.

Visual Studio apre il progetto. Si tratta già di una "Hello World!" di base. standard. Premere `Ctrl` + `F5` per eseguire il progetto. Visual Studio compila il progetto, convertendo il codice sorgente in un file eseguibile. Viene quindi avviata una finestra di comando che esegue la nuova applicazione. Nella finestra dovrebbe essere visualizzato il testo seguente:

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

Premere un tasto per chiudere la finestra.

# <a name="macostabmacos"></a>[macOS](#tab/macos)

Avviare Visual Studio per Mac. In Mac verrà visualizzata l'immagine seguente:

![Schermata iniziale di Visual Studio su Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> Se è la prima volta che si inizia Visual Studio per Mac, l'elenco dei **progetti recenti** è vuoto.

Selezionare **nuovo** nell'angolo in alto a destra dell'immagine. Visual Studio per Mac Visualizza la finestra di dialogo **nuovo progetto** :

![Schermata nuovo progetto di Visual Studio in Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

Nella finestra di dialogo nuovo progetto scegliere ".NET Core" e "app console" e quindi fare clic su **Avanti**. È necessario selezionare il Framework di destinazione. Il valore predefinito è corretto, quindi fare clic su Avanti. Assegnare un nome al progetto, ad esempio "HelloWorld", quindi fare clic su **Crea**. È possibile utilizzare il percorso predefinito del progetto. Non aggiungere questo progetto al controllo del codice sorgente.

Visual Studio per Mac apre il progetto. Si tratta già di una "Hello World!" di base. standard. Premere `Ctrl` + `Fn` + `F5` per eseguire il progetto. Visual Studio per Mac compila il progetto, convertendo il codice sorgente in un file eseguibile. Viene quindi avviata una finestra di comando che esegue la nuova applicazione. Nella finestra dovrebbe essere visualizzato il testo seguente:

```console
Hello World!

Press any key to close this window . . .
```

Premere un tasto per terminare la sessione.

---

## <a name="elements-of-a-c-program"></a>Elementi di un C# programma

Esaminiamo le parti importanti di questo programma. La prima riga contiene un commento. I caratteri `//` convertono il resto della riga in un commento.

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

È anche possibile commentare un blocco di testo racchiudendolo tra i caratteri `/*` e `*/`, come illustrato nell'esempio riportato di seguito.

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

È necessario che un'applicazione console C# contenga un metodo `Main`, in cui il controllo inizia e finisce. Il metodo `Main` consente di creare oggetti e di eseguire altri metodi.

Il metodo `Main` è un metodo di tipo [static](../../language-reference/keywords/static.md) che si trova all'interno di una classe o di uno struct. Nell'esempio "Hello World!" precedente si trovava in una classe denominata `Hello`. È possibile dichiarare il metodo `Main` in uno dei modi seguenti:

- Può restituire un valore `void`. Ciò significa che il programma non restituisce un valore.

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- Può restituire anche un valore intero. Il valore integer è il **codice di uscita** per l'applicazione.

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- Con entrambi i tipi restituiti, può accettare argomenti.

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

oppure

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

Il parametro del metodo `Main`, `args`, è una matrice `string` che contiene gli argomenti della riga di comando usati per richiamare il programma.

Per ulteriori informazioni sull'utilizzo degli argomenti della riga di comando, vedere gli esempi in [Main () e argomenti della riga di comando](../main-and-command-args/index.md).

## <a name="input-and-output"></a>Input e output

In genere i programmi C# usano i servizi di input/output offerti dalla libreria run-time di .NET Framework. L'istruzione `System.Console.WriteLine("Hello World!");` usa il metodo <xref:System.Console.WriteLine%2A>. Questo è uno dei metodi di output della classe <xref:System.Console> nella libreria di runtime. Visualizza il parametro di tipo stringa sul flusso di output standard seguito da una nuova riga. Sono disponibili altri metodi <xref:System.Console> per diverse operazioni di input e output. Se si include la direttiva `using System;` all'inizio del programma, è possibile usare direttamente le classi e i metodi <xref:System> senza specificarne il nome completo. Ad esempio, è possibile chiamare `Console.WriteLine` anziché `System.Console.WriteLine`:

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

Per altre informazioni sui metodi di input/output, vedere <xref:System.IO>.

## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Esempi ed esercitazioni](../../../samples-and-tutorials/index.md)
- [Main() e argomenti della riga di comando](../main-and-command-args/index.md)
- [Introduzione con VisualC#](/visualstudio/ide/quickstart-csharp-console)

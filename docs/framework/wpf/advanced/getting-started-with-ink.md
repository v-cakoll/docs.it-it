---
title: Creare InkCanvas in Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737884"
---
# <a name="get-started-with-ink-in-wpf"></a>Introduzione a input penna in WPF

Windows Presentation Foundation (WPF) dispone di una funzionalità di input penna che semplifica l'incorporamento dell'input penna digitale nell'app.

## <a name="prerequisites"></a>Prerequisiti

Per usare gli esempi seguenti, installare innanzitutto [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). Consente inoltre di comprendere come scrivere app WPF di base. Per informazioni introduttive su WPF, vedere [procedura dettagliata: applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="quick-start"></a>Introduzione

Questa sezione consente di scrivere una semplice applicazione WPF che raccoglie input penna.

### <a name="got-ink"></a>Hai un input penna?

Per creare un'applicazione WPF che supporti l'input penna:

1. Apri Visual Studio.

2. Creare una nuova **app WPF**.

   Nella finestra di dialogo **nuovo progetto** espandere la categoria **installato** > **Visual C#**  o **Visual Basic** > desktop di **Windows** . Quindi, selezionare il modello app **WPF (.NET Framework)** . Immettere un nome e quindi fare clic su **OK**.

   Visual Studio crea il progetto e *MainWindow. XAML* si apre nella finestra di progettazione.

3. Digitare `<InkCanvas/>` tra i tag di `<Grid>`.

   ![Finestra di progettazione XAML con tag InkCanvas](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. Premere **F5** per avviare l'applicazione nel debugger.

5. Usando uno stilo o un mouse, scrivere **Hello World** nella finestra.

Hai scritto l'equivalente dell'input penna di un'applicazione "Hello World" con solo 12 sequenze di tasti.

### <a name="spice-up-your-app"></a>Ravviva la tua app

È ora opportuno usufruire di alcune funzionalità di WPF. Sostituire tutti gli elementi tra la finestra di \<di apertura e di chiusura > Tag con il markup seguente:

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

Questo codice XAML crea uno sfondo del pennello sfumatura sull'area di Inking.

![Colori sfumatura sull'area Inking nell'app WPF](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a>Aggiungere codice sottostante a XAML

Mentre XAML rende molto semplice progettare l'interfaccia utente, qualsiasi applicazione reale deve aggiungere codice per gestire gli eventi. Ecco un semplice esempio che esegue lo zoom avanti sull'input penna in risposta a un clic con il pulsante destro del mouse.

1. Impostare il gestore `MouseRightButtonUp` in XAML:

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. In **Esplora soluzioni**espandere MainWindow. XAML e aprire il file code-behind (MainWindow.XAML.cs o MainWindow. XAML. vb). Aggiungere il seguente codice del gestore eventi:

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. Eseguire l'applicazione. Aggiungere un input penna, quindi fare clic con il pulsante destro del mouse con il mouse o eseguire un valore equivalente a premere e tenere premuto uno stilo.

   La visualizzazione viene ingrandita ogni volta che si fa clic con il pulsante destro del mouse.

### <a name="use-procedural-code-instead-of-xaml"></a>Usa codice procedurale anziché XAML

È possibile accedere a tutte le funzionalità WPF dal codice procedurale. Seguire questa procedura per creare un'applicazione "Hello Ink World" per WPF che non usa alcun codice XAML.

1. Creare un nuovo progetto di applicazione console in Visual Studio.

   Nella finestra di dialogo **nuovo progetto** espandere la categoria **installato** > **Visual C#**  o **Visual Basic** > desktop di **Windows** . Quindi, selezionare il modello app **Console (.NET Framework)** . Immettere un nome e quindi fare clic su **OK**.

1. Incollare il codice seguente nel file Program.cs o Program. vb:

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. Aggiungere riferimenti agli assembly PresentationCore, PresentationFramework e WindowsBase facendo clic con il pulsante destro del mouse su **riferimenti** in **Esplora soluzioni** e scegliendo **Aggiungi riferimento**.

   ![Gestione riferimenti che mostra PresentationCore e PresentationFramework](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. Compilare l'applicazione premendo **F5**.

## <a name="see-also"></a>Vedere anche

- [Input penna](digital-ink.md)
- [Raccolta di input penna](collecting-ink.md)
- [Riconoscimento della grafia](handwriting-recognition.md)
- [Archiviazione dell'input penna](storing-ink.md)

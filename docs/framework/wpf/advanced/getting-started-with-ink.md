---
title: Creare un oggetto InkCanvas in un'app WPF in Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: d633111c5abc572b0fc27c1a5b32050681504073
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/24/2019
ms.locfileid: "63807966"
---
# <a name="get-started-with-ink-in-wpf"></a>Introduzione a input penna in WPF

Windows Presentation Foundation (WPF) è una funzionalità di input penna che rende più semplice incorporare input penna digitale nella tua app.

## <a name="prerequisites"></a>Prerequisiti

Per usare gli esempi seguenti, installare innanzitutto [Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). È anche utile per sapere come scrivere le app WPF di base. Per informazioni sulla Guida introduttiva a WPF, vedere [procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="quick-start"></a>Guida introduttiva

In questa sezione consente di scrivere una semplice applicazione WPF che consente di raccogliere input penna.

### <a name="got-ink"></a>Ricevuto input penna?

Per creare un'app WPF che supporta l'input penna:

1. Aprire Visual Studio.

2. Creare una nuova **App WPF**.

   Nel **nuovo progetto** finestra di dialogo espandere il **installato** > **Visual c#** oppure **Visual Basic**  >   **Windows Desktop** categoria. Selezionare quindi il **App WPF (.NET Framework)** modello di app. Immettere un nome e quindi selezionare **OK**.

   Visual Studio crea il progetto, e *MainWindow. XAML* nella finestra di progettazione.

3. Tipo di `<InkCanvas/>` tra il `<Grid>` tag.

   ![Finestra di progettazione XAML con tag InkCanvas](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. Premere **F5** per avviare l'applicazione nel debugger.

5. Tramite uno stilo o un mouse, scrivere **HelloWorld** nella finestra.

L'equivalente dell'input penna di un'applicazione "hello world" con solo 12 tasti scritto!

### <a name="spice-up-your-app"></a>Migliorare le prestazioni dell'App

È possibile sfruttare i vantaggi di alcune funzionalità di WPF. Sostituire tutto il contenuto tra l'apertura e chiusura \<finestra > tag con il markup seguente:

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

Questo XAML crea uno sfondo pennello sfumato nella superficie dell'input penna.

![Colori sfumati in input penna di surface in app WPF](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a>Aggiungere il codice dietro il XAML

Mentre XAML è molto semplice progettare l'interfaccia utente, tutte le applicazioni del mondo reale deve aggiungere il codice per gestire gli eventi. Ecco un esempio semplice che viene ingrandita sull'input penna in risposta al pulsante destro del mouse.

1. Impostare il `MouseRightButtonUp` gestore nel XAML:

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. Nelle **Esplora soluzioni**espandere MainWindow. XAML e aprire il file code-behind (MainWindow.xaml.cs o XAML. vb). Aggiungere il codice del gestore eventi seguente:

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. Eseguire l'applicazione. Aggiungere alcuni input penna, quindi fare clic con il mouse o eseguire un equivalente premere e tenere con uno stilo.

   La visualizzazione viene ingrandita ogni volta che si fa clic con il pulsante destro del mouse.

### <a name="use-procedural-code-instead-of-xaml"></a>Usare codice procedurale anziché XAML

Tutte le funzionalità WPF è possibile accedere dal codice procedurale. Seguire questi passaggi per creare un'applicazione "Hello dell'input penna World" per WPF che non utilizza affatto qualsiasi XAML.

1. Creare un nuovo progetto applicazione console in Visual Studio.

   Nel **nuovo progetto** finestra di dialogo espandere il **installato** > **Visual c#** oppure **Visual Basic**  >   **Windows Desktop** categoria. Selezionare quindi il **App Console (.NET Framework)** modello di app. Immettere un nome e quindi selezionare **OK**.

1. Incollare il codice seguente nel file Program.cs o Program. vb:

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. Aggiungere riferimenti agli assembly PresentationCore, PresentationFramework e WindowsBase facendo clic su **riferimenti** nelle **Esplora soluzioni** e scegliendo **Aggiungi riferimento**.

   ![Gestione di riferimenti che mostra PresentationCore e PresentationFramework](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. Compilare l'applicazione premendo **F5**.

## <a name="see-also"></a>Vedere anche

- [Input penna](digital-ink.md)
- [Raccolta di input penna](collecting-ink.md)
- [Riconoscimento della grafia](handwriting-recognition.md)
- [Archiviazione dell'input penna](storing-ink.md)

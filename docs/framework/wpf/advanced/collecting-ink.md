---
title: Raccogliere l'input penna nelle applicazioni WPF
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 25f9c0141a97d8e52e0883b14fd3e1f4574a05ea
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44195072"
---
# <a name="collect-ink"></a>Raccogliere l'input penna

La raccolta di input penna è una delle funzionalità principali della piattaforma [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md). In questo argomento illustra i metodi per la raccolta dell'input penna in Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>Prerequisiti

Per usare gli esempi seguenti, è innanzitutto necessario installare Visual Studio e [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. È inoltre necessario comprendere come scrivere applicazioni per l'applicazione WPF. Per altre informazioni sulle operazioni iniziali con WPF, vedere [procedura dettagliata: prima applicazione desktop WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="use-the-inkcanvas-element"></a>Usare l'elemento InkCanvas

Il <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> elemento fornisce il modo più semplice per raccogliere input penna in WPF. Usare un <xref:System.Windows.Controls.InkCanvas> elemento per ricevere e visualizzare input penna. In genere, l'input penna viene effettuato tramite uno stilo che interagisce con un digitalizzatore per produrre i tratti. È anche possibile usare un mouse al posto dello stilo. I tratti creati sono rappresentati come <xref:System.Windows.Ink.Stroke> degli oggetti e che possono essere modificati sia a livello di codice che per l'utente di input. Il <xref:System.Windows.Controls.InkCanvas> consente agli utenti di selezionare, modificare o eliminare un oggetto esistente <xref:System.Windows.Ink.Stroke>.

Tramite XAML, è possibile impostare la raccolta dell'input penna con la stessa facilità con cui si aggiunge un **InkCanvas** elemento alla struttura ad albero. L'esempio seguente aggiunge un <xref:System.Windows.Controls.InkCanvas> a un progetto WPF predefiniti creato in Visual Studio:

[!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

Il **InkCanvas** elemento può anche contenere elementi figlio, rendendo possibile l'aggiunta di funzionalità di annotazione a penna a quasi tutti i tipi di elemento XAML. Ad esempio, per aggiungere funzionalità di input penna a un elemento di testo, è sufficiente trasformarlo in un elemento figlio di un <xref:System.Windows.Controls.InkCanvas>:

[!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

Aggiunta del supporto per contrassegnare un'immagine con input penna è altrettanto semplice:

[!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>Modalità InkCollection

Il <xref:System.Windows.Controls.InkCanvas> offre il supporto per varie modalità di input tramite relativo <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> proprietà.

### <a name="manipulate-ink"></a>Modificare l'input penna

Il <xref:System.Windows.Controls.InkCanvas> fornisce il supporto per molte operazioni di modifica di input penna. Ad esempio, <xref:System.Windows.Controls.InkCanvas> erase supporta back della penna e richiedere codice aggiuntivo non è necessario per aggiungere la funzionalità per l'elemento.

#### <a name="selection"></a>Selection

Impostazione della modalità di selezione è semplice come l'impostazione di <xref:System.Windows.Controls.InkCanvasEditingMode> proprietà **seleziona**.

Il codice seguente imposta la modalità di modifica in base al valore di un <xref:System.Windows.Forms.CheckBox>:

[!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

Usare il <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> proprietà per modificare l'aspetto dei tratti input penna. Ad esempio, il <xref:System.Windows.Ink.DrawingAttributes.Color%2A> appartenente <xref:System.Windows.Ink.DrawingAttributes> imposta il colore dell'oggetto sottoposto a rendering <xref:System.Windows.Ink.Stroke>.

Nell'esempio seguente modifica il colore dei tratti selezionati su rosso:

[!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

Il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà offre l'accesso a proprietà quali l'altezza, larghezza e colore dei tratti da creare un <xref:System.Windows.Controls.InkCanvas>. Dopo aver modificato il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, tutti i futuri tratti immessi nel <xref:System.Windows.Controls.InkCanvas> vengono sottoposti a rendering con i nuovi valori di proprietà.

Oltre a modificare la <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> nel file code-behind, è possibile usare la sintassi XAML per la specifica <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà.

L'esempio seguente viene illustrato come impostare il <xref:System.Windows.Ink.DrawingAttributes.Color%2A> proprietà. Per usare questo codice, creare un nuovo progetto WPF denominato "HelloInkCanvas" in Visual Studio. Sostituire il codice nel *MainWindow. XAML* file con il codice seguente:

[!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

Per il file code-behind, all'interno della classe MainWindow aggiungere quindi i gestori eventi dei pulsanti seguenti:

[!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

Dopo aver copiato questo codice, premere **F5** in Visual Studio per eseguire il programma nel debugger.

Si noti che il <xref:System.Windows.Controls.StackPanel> colloca i pulsanti nella parte superiore del <xref:System.Windows.Controls.InkCanvas>. Se si prova a input penna nella parte superiore dei pulsanti, il <xref:System.Windows.Controls.InkCanvas> raccoglie ed esegue il rendering dell'input penna dietro i pulsanti. Infatti, i pulsanti sono elementi di pari livello del <xref:System.Windows.Controls.InkCanvas> e non elementi figlio. Il rendering dell'input penna viene eseguito dietro i pulsanti anche perché si trovano più in alto nel z order.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
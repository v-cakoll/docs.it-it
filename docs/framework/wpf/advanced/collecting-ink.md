---
title: Raccogli input penna digitale
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
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747034"
---
# <a name="collect-ink"></a>Raccogli input penna

La raccolta di input penna è una delle funzionalità principali della piattaforma [Windows Presentation Foundation](../index.md). In questo argomento vengono illustrati i metodi per la raccolta di input penna in Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>Prerequisiti

Per usare gli esempi seguenti, è necessario innanzitutto installare Visual Studio e il Windows SDK. È inoltre necessario comprendere come scrivere applicazioni per WPF. Per ulteriori informazioni su come iniziare a usare WPF, vedere [procedura dettagliata: applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="use-the-inkcanvas-element"></a>Usare l'elemento InkCanvas

L'elemento <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> rappresenta il modo più semplice per raccogliere input penna in WPF. Usare un elemento <xref:System.Windows.Controls.InkCanvas> per ricevere e visualizzare input penna. In genere, l'input penna viene effettuato tramite uno stilo che interagisce con un digitalizzatore per produrre i tratti. È anche possibile usare un mouse al posto dello stilo. I tratti creati sono rappresentati come oggetti <xref:System.Windows.Ink.Stroke> e possono essere modificati sia a livello di codice sia in base all'input dell'utente. Il <xref:System.Windows.Controls.InkCanvas> consente agli utenti di selezionare, modificare o eliminare un <xref:System.Windows.Ink.Stroke>esistente.

Usando XAML, è possibile configurare la raccolta di input penna con la stessa facilità con cui si aggiunge un elemento **InkCanvas** all'albero. Nell'esempio seguente viene aggiunto un <xref:System.Windows.Controls.InkCanvas> a un progetto WPF predefinito creato in Visual Studio:

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

L'elemento **InkCanvas** può inoltre contenere elementi figlio, rendendo possibile l'aggiunta di funzionalità di annotazione Ink a quasi tutti i tipi di elementi XAML. Ad esempio, per aggiungere le funzionalità di Inking a un elemento di testo, è sufficiente renderlo figlio di un <xref:System.Windows.Controls.InkCanvas>:

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

L'aggiunta del supporto per contrassegnare un'immagine con input penna è semplice:

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>Modalità InkCollection

Il <xref:System.Windows.Controls.InkCanvas> fornisce supporto per varie modalità di input tramite la relativa proprietà <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>.

### <a name="manipulate-ink"></a>Modificare l'input penna

Il <xref:System.Windows.Controls.InkCanvas> fornisce il supporto per molte operazioni di modifica dell'input penna. Ad esempio, <xref:System.Windows.Controls.InkCanvas> supporta la cancellazione della penna indietro e non è necessario alcun codice aggiuntivo per aggiungere la funzionalità all'elemento.

#### <a name="selection"></a>Selection

Per impostare la modalità di selezione è sufficiente impostare la proprietà <xref:System.Windows.Controls.InkCanvasEditingMode> su **Seleziona**.

Il codice seguente imposta la modalità di modifica in base al valore di un <xref:System.Windows.Forms.CheckBox>:

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

Utilizzare la proprietà <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> per modificare l'aspetto dei tratti di input penna. Ad esempio, il membro <xref:System.Windows.Ink.DrawingAttributes.Color%2A> di <xref:System.Windows.Ink.DrawingAttributes> imposta il colore del <xref:System.Windows.Ink.Stroke>sottoposto a rendering.

Nell'esempio seguente il colore dei tratti selezionati viene modificato in rosso:

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

La proprietà <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> fornisce l'accesso a proprietà quali l'altezza, la larghezza e il colore dei tratti da creare in una <xref:System.Windows.Controls.InkCanvas>. Una volta modificato il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, viene eseguito il rendering di tutti i tratti successivi immessi nel <xref:System.Windows.Controls.InkCanvas> con i nuovi valori delle proprietà.

Oltre a modificare il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> nel file code-behind, è possibile utilizzare la sintassi XAML per specificare <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà.

Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Ink.DrawingAttributes.Color%2A>. Per usare questo codice, creare un nuovo progetto WPF denominato "HelloInkCanvas" in Visual Studio. Sostituire il codice nel file *MainWindow. XAML* con il codice seguente:

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

Successivamente, aggiungere i gestori eventi del pulsante seguenti al file code-behind, all'interno della classe MainWindow:

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

Dopo aver copiato il codice, premere **F5** in Visual Studio per eseguire il programma nel debugger.

Si noti come il <xref:System.Windows.Controls.StackPanel> posiziona i pulsanti sulla parte superiore del <xref:System.Windows.Controls.InkCanvas>. Se si tenta di eseguire l'input penna sulla parte superiore dei pulsanti, il <xref:System.Windows.Controls.InkCanvas> raccoglie ed esegue il rendering dell'input penna dietro i pulsanti. Il motivo è che i pulsanti sono elementi di pari livello del <xref:System.Windows.Controls.InkCanvas> anziché degli elementi figlio. Il rendering dell'input penna viene eseguito dietro i pulsanti anche perché si trovano più in alto nel z order.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>

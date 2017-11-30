---
title: Raccolta di input penna
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81ed657de0c0e4d07fcb10b099cbf5e5c80a71fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="collecting-ink"></a>Raccolta di input penna
La raccolta di input penna è una delle funzionalità principali della piattaforma [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md). Questo argomento illustra i metodi per la raccolta di input penna in [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per usare gli esempi seguenti, è prima necessario installare [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] e [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]. È anche necessario avere conoscenze su come scrivere applicazioni per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per ulteriori informazioni sui concetti introduttivi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [procedura dettagliata: applicazione desktop WPF prima](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="using-the-inkcanvas-element"></a>Uso dell'elemento InkCanvas  
 Il <xref:System.Windows.Controls.InkCanvas> elemento fornisce il modo più semplice per raccogliere input penna in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il <xref:System.Windows.Controls.InkCanvas> è simile all'elemento di [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) dall'oggetto di [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] e nelle versioni precedenti.  
  
 Utilizzare un <xref:System.Windows.Controls.InkCanvas> elemento per ricevere e visualizzare l'input penna. In genere, l'input penna viene effettuato tramite uno stilo che interagisce con un digitalizzatore per produrre i tratti. È anche possibile usare un mouse al posto dello stilo. I tratti creati vengono rappresentati come <xref:System.Windows.Ink.Stroke> degli oggetti e che possono essere modificati a livello di codice e di utente di input. Il <xref:System.Windows.Controls.InkCanvas> consente agli utenti di selezionare, modificare o eliminare un oggetto esistente <xref:System.Windows.Ink.Stroke>.  
  
 Con XAML è possibile configurare raccolte di input penna con la stessa facilità con cui si aggiunge un elemento `InkCanvas` alla struttura ad albero. L'esempio seguente aggiunge un <xref:System.Windows.Controls.InkCanvas> a un valore predefinito [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] progetto creato in [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].  
  
 [!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 L'elemento `InkCanvas` può anche contenere elementi figlio, rendendo possibile l'aggiunta di funzionalità di annotazione a penna a quasi tutti i tipi di elementi XAML. Ad esempio, per aggiungere funzionalità di input penna per un elemento di testo, semplicemente renderlo un elemento figlio di un <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 L'aggiunta del supporto per contrassegnare un'immagine con input penna è altrettanto semplice.  
  
 [!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### <a name="inkcollection-modes"></a>Modalità InkCollection  
 Il <xref:System.Windows.Controls.InkCanvas> fornisce supporto per varie modalità di input tramite il relativo <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> proprietà.  
  
### <a name="manipulating-ink"></a>Modifica di input penna  
 Il <xref:System.Windows.Controls.InkCanvas> fornisce supporto per molte operazioni di modifica dell'input penna. Ad esempio, <xref:System.Windows.Controls.InkCanvas> supporta back della penna erase senza codice aggiuntivo necessario per aggiungere la funzionalità per l'elemento.  
  
#### <a name="selection"></a>Selection  
 Impostazione della modalità di selezione è semplice come l'impostazione di <xref:System.Windows.Controls.InkCanvasEditingMode> proprietà **selezionare**. Il codice seguente imposta la modalità di modifica in base al valore di un <xref:System.Windows.Forms.CheckBox>:  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### <a name="drawingattributes"></a>DrawingAttributes  
 Utilizzare il <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> proprietà per modificare l'aspetto di tratti input penna. Ad esempio, il <xref:System.Windows.Ink.DrawingAttributes.Color%2A> membro di <xref:System.Windows.Ink.DrawingAttributes> imposta il colore dell'oggetto sottoposto a rendering <xref:System.Windows.Ink.Stroke>. L'esempio seguente imposta il colore dei tratti selezionati su rosso.  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes  
 Il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> fornisce l'accesso alle proprietà, ad esempio l'altezza, larghezza e colore dei tratti da creare un <xref:System.Windows.Controls.InkCanvas>. Dopo aver modificato il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, tutti i futuri tratti inseriti il <xref:System.Windows.Controls.InkCanvas> vengono sottoposti a rendering con i nuovi valori di proprietà.  
  
 Oltre a modificare il <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> nel file code-behind, è possibile utilizzare la sintassi XAML per la specifica <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà. Il codice XAML seguente viene illustrato come impostare il <xref:System.Windows.Ink.DrawingAttributes.Color%2A> proprietà. Per usare questo codice, creare un nuovo progetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] denominato "HelloInkCanvas" in Visual Studio 2005. Sostituire il codice nel file Window1.xaml con il codice seguente.  
  
 [!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 Aggiungere poi i gestori eventi di pulsanti seguenti al file code-behind, nella classe Window1.  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 Dopo aver copiato questo codice, premere **F5** in Microsoft Visual Studio 2005 per eseguire il programma nel debugger.  
  
 Si noti come <xref:System.Windows.Controls.StackPanel> colloca i pulsanti in cima il <xref:System.Windows.Controls.InkCanvas>. Se si tenta di input penna nella parte superiore dei pulsanti, il <xref:System.Windows.Controls.InkCanvas> raccoglie ed esegue il rendering dell'input penna sotto i pulsanti. Infatti, i pulsanti sono di pari livello di <xref:System.Windows.Controls.InkCanvas> anziché gli elementi figlio. Il rendering dell'input penna viene eseguito dietro i pulsanti anche perché si trovano più in alto nel z order.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Ink.DrawingAttributes>  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>  
 <xref:System.Windows.Ink>

---
title: "Procedura: Selezionare l'input penna da un controllo personalizzato"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 5c9b2f3d64e4cbb309772d6a1d9fa88f589df84c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768403"
---
# <a name="how-to-select-ink-from-a-custom-control"></a>Procedura: Selezionare l'input penna da un controllo personalizzato
Aggiungendo un <xref:System.Windows.Ink.IncrementalLassoHitTester> del controllo personalizzato, è possibile abilitare il controllo in modo che un utente può selezionare l'input penna con lo strumento, analogamente al modo in cui il <xref:System.Windows.Controls.InkCanvas> seleziona input penna con un lazo.  
  
 In questo esempio si presuppone che si ha familiarità con la creazione di un controllo personalizzato compatibile.  Per creare un controllo personalizzato che accetta l'input penna, vedere [creazione di un controllo Input penna](creating-an-ink-input-control.md).  
  
## <a name="example"></a>Esempio  
 Quando l'utente lo disegna un lazo il <xref:System.Windows.Ink.IncrementalLassoHitTester> consente di stimare quali tratti sarà all'interno dei limiti del lazo dopo che l'utente completa del lazo.  I tratti che sono determinati all'interno dei confini del lazo possono essere considerati come selezionato.  I tratti selezionati possono anche essere deselezionati.  Se l'utente cambia direzione mentre lo strumento lazo, ad esempio il <xref:System.Windows.Ink.IncrementalLassoHitTester> possibile deselezionare alcune tracce.  
  
 Il <xref:System.Windows.Ink.IncrementalLassoHitTester> genera il <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> evento, che consente il controllo personalizzato rispondere mentre l'utente è lo strumento lazo.  Ad esempio, è possibile modificare l'aspetto dei tratti come utente selezionati e deselezionati.  
  
## <a name="managing-the-ink-mode"></a>Gestione della modalità di input penna  
 È utile per l'utente se lazo viene visualizzato in modo diverso rispetto all'input penna sul controllo. A tale scopo, il controllo personalizzato deve tenere traccia della se l'utente è la scrittura o la selezione di input penna. Il modo più semplice per eseguire questa operazione consiste nel dichiarare un'enumerazione con due valori: una per indicare che l'utente scrive dell'input penna e uno per indicare che l'utente seleziona l'input penna.  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 Successivamente, aggiungere due <xref:System.Windows.Ink.DrawingAttributes> alla classe: uno da utilizzare quando l'utente scrive tramite una penna, uno da utilizzare quando l'utente seleziona l'input penna.  Nel costruttore, inizializzare il <xref:System.Windows.Ink.DrawingAttributes> allegando sia <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> eventi allo stesso gestore eventi. Impostare quindi le <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> proprietà del <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> all'input penna <xref:System.Windows.Ink.DrawingAttributes>.  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Aggiungere una proprietà che espone la modalità di selezione. Quando l'utente modifica la modalità di selezione, impostare il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> proprietà del <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> appropriato <xref:System.Windows.Ink.DrawingAttributes> dell'oggetto e quindi ricollegare il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> proprietà per il <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Esporre il <xref:System.Windows.Ink.DrawingAttributes> come proprietà in modo che le applicazioni possono determinare l'aspetto dei tratti input penna e selezione.  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Quando una proprietà di un <xref:System.Windows.Ink.DrawingAttributes> oggetto viene modificato, il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> devono essere ricollegate al <xref:System.Windows.Controls.InkPresenter>.  Nel gestore eventi per il <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> evento, ricollegare il <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> per il <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>Utilizzo di IncrementalLassoHitTester  
 Creare e inizializzare un <xref:System.Windows.Ink.StrokeCollection> che contiene i tratti selezionati.  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Quando l'utente inizia a disegnare un tratto, input penna o il lazo, deselezionare tutti i tratti selezionati. Quindi, se l'utente lo disegna un lazo, creare un <xref:System.Windows.Ink.IncrementalLassoHitTester> chiamando <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>, sottoscrivere il <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> evento, quindi chiamare <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>. Questo codice può essere un metodo separato e chiamata dal <xref:System.Windows.UIElement.OnStylusDown%2A> e <xref:System.Windows.UIElement.OnMouseDown%2A> metodi.  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Aggiungere i punti dello stilo dal <xref:System.Windows.Ink.IncrementalLassoHitTester> mentre l'utente lo disegna lazo.  Chiamare il metodo seguente dal <xref:System.Windows.UIElement.OnStylusMove%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, <xref:System.Windows.UIElement.OnMouseMove%2A>, e <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> metodi.  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Gestire il <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> evento a cui rispondere quando l'utente seleziona e deseleziona tratti.  Il <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> classe presenta la <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> e <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> proprietà che recuperano i tratti che sono state selezionate e deselezionate, rispettivamente.  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Quando l'utente termina lo strumento lazo, annullare la sottoscrizione di <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> eventi e chiamate <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>.  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>Uso combinato tutti.  
 Nell'esempio seguente è un controllo personalizzato che consente all'utente di selezionare l'input penna con un lazo.  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [Creazione di un controllo di input penna](creating-an-ink-input-control.md)

---
title: 'Procedura: Ottenere o impostare le proprietà di posizionamento delle aree di disegno'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: b7dd64959148b8c2361992fb7cd2f23073693dd6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705862"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>Procedura: Ottenere o impostare le proprietà di posizionamento delle aree di disegno
In questo esempio viene illustrato come utilizzare i metodi di posizionamento del <xref:System.Windows.Controls.Canvas> elemento per posizionare il contenuto figlio. Questo esempio viene usato il contenuto in un <xref:System.Windows.Controls.ListBoxItem> per rappresentare valori di posizionamento e converte i valori in istanze di <xref:System.Double>, che è un argomento obbligatorio per il posizionamento. I valori vengono quindi convertiti in stringhe e visualizzati come testo in un <xref:System.Windows.Controls.TextBlock> elemento usando la <xref:System.Windows.Controls.Canvas.GetLeft%2A> (metodo).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una <xref:System.Windows.Controls.ListBox> elemento che dispone di undici selezionabile <xref:System.Windows.Controls.ListBoxItem> elementi. Il <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> trigger di evento di `ChangeLeft` metodo personalizzato che definisce il blocco di codice successivo.  
  
 Ogni <xref:System.Windows.Controls.ListBoxItem> rappresenta un <xref:System.Double> valore, ovvero uno degli argomenti che le <xref:System.Windows.Controls.Canvas.SetLeft%2A> metodo <xref:System.Windows.Controls.Canvas> accetta. Per usare un <xref:System.Windows.Controls.ListBoxItem> per rappresentare un'istanza di <xref:System.Double>, è prima necessario convertire il <xref:System.Windows.Controls.ListBoxItem> al tipo di dati corretto.  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Quando un utente modifica il <xref:System.Windows.Controls.ListBox> selezione, viene richiamato il `ChangeLeft` metodo personalizzato. Questo metodo passa il <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.LengthConverter> oggetto, che converte il <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Double> (si noti che questo valore è già stato convertito in un <xref:System.String> utilizzando il <xref:System.Windows.Controls.Control.ToString%2A> metodo). Questo valore viene quindi passato al <xref:System.Windows.Controls.Canvas.SetLeft%2A> e <xref:System.Windows.Controls.Canvas.GetLeft%2A> metodi del <xref:System.Windows.Controls.Canvas> per modificare la posizione del `text1` oggetto.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)

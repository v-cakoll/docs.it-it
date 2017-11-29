---
title: "Procedura: ottenere o impostare le proprietà di posizionamento delle aree di disegno"
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
helpviewer_keywords: Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2b2f20754c8425149f73f10af773604539125adb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>Procedura: ottenere o impostare le proprietà di posizionamento delle aree di disegno
In questo esempio viene illustrato come utilizzare i metodi di posizionamento di <xref:System.Windows.Controls.Canvas> elemento per posizionare il contenuto figlio. Questo esempio viene utilizzato il contenuto in un <xref:System.Windows.Controls.ListBoxItem> per rappresentare i valori di posizionamento e converte i valori in istanze di <xref:System.Double>, che è un argomento obbligatorio per il posizionamento. I valori vengono convertiti in stringhe e visualizzati come testo in un <xref:System.Windows.Controls.TextBlock> elemento utilizzando il <xref:System.Windows.Controls.Canvas.GetLeft%2A> metodo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ListBox> elemento che dispone di undici selezionabile <xref:System.Windows.Controls.ListBoxItem> elementi. Il <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> trigger di evento di `ChangeLeft` metodo personalizzato che definisce il blocco di codice successivo.  
  
 Ogni <xref:System.Windows.Controls.ListBoxItem> rappresenta un <xref:System.Double> valore, ovvero uno degli argomenti che la <xref:System.Windows.Controls.Canvas.SetLeft%2A> metodo <xref:System.Windows.Controls.Canvas> accetta. Per utilizzare un <xref:System.Windows.Controls.ListBoxItem> per rappresentare un'istanza di <xref:System.Double>, è prima necessario convertire il <xref:System.Windows.Controls.ListBoxItem> al tipo di dati corretto.  
  
 [!code-xaml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Quando un utente modifica il <xref:System.Windows.Controls.ListBox> selezione, richiama il `ChangeLeft` metodo personalizzato. Questo metodo passa il <xref:System.Windows.Controls.ListBoxItem> per un <xref:System.Windows.LengthConverter> oggetto, che converte il <xref:System.Windows.Controls.ContentControl.Content%2A> di un <xref:System.Windows.Controls.ListBoxItem> a un'istanza di <xref:System.Double> (si noti che questo valore è già stato convertito in un <xref:System.String> utilizzando il <xref:System.Windows.Controls.Control.ToString%2A> metodo). Questo valore viene quindi passato nuovamente al <xref:System.Windows.Controls.Canvas.SetLeft%2A> e <xref:System.Windows.Controls.Canvas.GetLeft%2A> metodi di <xref:System.Windows.Controls.Canvas> per modificare la posizione del `text1` oggetto.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.ListBoxItem>  
 <xref:System.Windows.LengthConverter>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)

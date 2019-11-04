---
title: 'Procedura: creare testo sullo sfondo di un controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424378"
---
# <a name="how-to-draw-text-to-a-controls-background"></a>Procedura: creare testo sullo sfondo di un controllo
È possibile disegnare il testo direttamente sullo sfondo di un controllo convertendo una stringa di testo in un oggetto <xref:System.Windows.Media.FormattedText>, quindi disegnando l'oggetto nella <xref:System.Windows.Media.DrawingContext>del controllo. È anche possibile usare questa tecnica per disegnare sullo sfondo di oggetti derivati da <xref:System.Windows.Controls.Panel>, ad esempio <xref:System.Windows.Controls.Canvas> e <xref:System.Windows.Controls.StackPanel>.  
  
 ![Screenshot dei controlli che visualizzano testo come sfondo.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")  
Esempio di controlli con sfondi di testo personalizzati  
  
## <a name="example"></a>Esempio  
 Per creare uno sfondo di un controllo, creare un nuovo oggetto <xref:System.Windows.Media.DrawingBrush> e creare il testo convertito nel <xref:System.Windows.Media.DrawingContext>dell'oggetto. Assegnare quindi la nuova <xref:System.Windows.Media.DrawingBrush> alla proprietà background del controllo.  
  
 Nell'esempio di codice seguente viene illustrato come creare un oggetto <xref:System.Windows.Media.FormattedText> e come eseguire il progetto sullo sfondo di un oggetto <xref:System.Windows.Controls.Label> e <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.FormattedText>
- [Disegno di testo formattato](drawing-formatted-text.md)

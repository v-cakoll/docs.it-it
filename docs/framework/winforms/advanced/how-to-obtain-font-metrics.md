---
title: 'Procedura: Ottenere le misure dei tipi di carattere'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: 75177b609f14d335aa57aba77d647827f50a8692
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881887"
---
# <a name="how-to-obtain-font-metrics"></a>Procedura: Ottenere le misure dei tipi di carattere
Il <xref:System.Drawing.FontFamily> classe fornisce i metodi seguenti che recuperano diverse metriche per una particolare famiglia/combinazione stile:  
  
- <xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)  
  
- <xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)  
  
- <xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)  
  
- <xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)  
  
 I numeri restituiti da questi metodi sono in unità di progettazione del tipo di carattere, in modo che siano indipendenti dalla dimensione e le unità di un determinato <xref:System.Drawing.Font> oggetto.  
  
 La figura seguente illustra le varie metriche:
  
 ![Illustrazione delle metriche del tipo di carattere: ascent dei valori descent con e interlinea.](./media/how-to-obtain-font-metrics/various-font-metrics.png)  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra le metriche per lo stile regolare della famiglia del tipo di carattere Arial. Il codice crea inoltre una <xref:System.Drawing.Font> oggetto (in base alla famiglia Arial) con dimensioni di 16 pixel e consente di visualizzare le metriche, in pixel, per quel particolare <xref:System.Drawing.Font> oggetto.  
  
 Nella figura seguente mostra l'output del codice di esempio:
  
 ![Output di codice di esempio delle metriche del tipo di carattere Arial.](./media/how-to-obtain-font-metrics/example-output-code-arial-font.png)  
  
 Tenere presente le prime due righe di output nella figura precedente. Il <xref:System.Drawing.Font> object restituisce una dimensione pari a 16 e il <xref:System.Drawing.FontFamily> oggetto restituisce un'altezza em di 2048. Questi due numeri (16 e 2,048) sono la chiave per la conversione tra unità di progettazione del tipo di carattere e le unità (in questo caso pixel) del <xref:System.Drawing.Font> oggetto.  
  
 Ad esempio, è possibile convertire l'ascent di unità di progettazione pixel come indicato di seguito:  
  
 ![Formula che mostra la conversione da unità di progettazione per pixel](./media/how-to-obtain-font-metrics/convert-font-units-example.png)  
  
 Il codice seguente posiziona testo verticalmente impostando il <xref:System.Drawing.PointF.Y%2A> membro dati di un <xref:System.Drawing.PointF> oggetto. La coordinata y è aumentata `font.Height` per ogni nuova riga di testo. Il <xref:System.Drawing.Font.Height%2A> proprietà di un <xref:System.Drawing.Font> object restituisce l'interlinea, in pixel, per quel particolare <xref:System.Drawing.Font> oggetto. In questo esempio, il numero restituito da <xref:System.Drawing.Font.Height%2A> è 19. Si noti che questo è lo stesso come numero (arrotondato per eccesso a un numero intero) ottenuto tramite la conversione della metrica di interlinea in pixel.  
  
 Si noti che l'altezza em (denominato anche dimensioni em o dimensioni) non è la somma dell'ascent e la parte discendente. La somma dell'ascent e la parte discendente viene chiamata l'altezza della cella. L'altezza della cella meno lo spazio iniziale interno è uguale all'altezza em. L'altezza della cella più l'interlinea esterna è uguale alla distanza tra linee.  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Uso di tipi di carattere e testo](using-fonts-and-text.md)

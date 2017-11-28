---
title: 'Procedura: recuperare i criteri di misurazione dei caratteri'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5b45f3f903c02d056fc457b652b01fb7b59413a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-font-metrics"></a>Procedura: recuperare i criteri di misurazione dei caratteri
La <xref:System.Drawing.FontFamily> classe fornisce i seguenti metodi che recuperano diverse metriche per una particolare famiglia o combinazione di stile:  
  
-   <xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)  
  
-   <xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)  
  
-   <xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)  
  
-   <xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)  
  
 I numeri restituiti da questi metodi sono in unità di progettazione di tipo di carattere, in modo che siano indipendenti le dimensioni e l'unità di un particolare <xref:System.Drawing.Font> oggetto.  
  
 Nella figura seguente mostra le varie metriche.  
  
 ![Tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/fontstext7a.png "fontstext7A")  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra le metriche per lo stile normale della famiglia di caratteri Arial. Il codice crea inoltre un <xref:System.Drawing.Font> oggetto (in base alla famiglia Arial) con dimensioni 16 pixel e visualizza le metriche (in pixel) per questo specifico <xref:System.Drawing.Font> oggetto.  
  
 Nella figura seguente mostra l'output del codice di esempio.  
  
 ![Tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/csfontstext8.png "csFontsText8")  
  
 Tenere presente le prime due righe di output nell'illustrazione precedente. Il <xref:System.Drawing.Font> oggetto restituisce una dimensione di 16 e <xref:System.Drawing.FontFamily> restituisce un'altezza em pari a 2048. Questi due numeri (16 e 2.048) sono fondamentali per la conversione tra unità di progettazione caratteri e le unità (in questo caso pixel) del <xref:System.Drawing.Font> oggetto.  
  
 Ad esempio, è possibile convertire l'ascent di unità di progettazione pixel come indicato di seguito:  
  
 ![Tipi di carattere testo](../../../../docs/framework/winforms/advanced/media/fontstext9.png "FontsText9")  
  
 Il codice seguente posiziona testo verticale impostando il <xref:System.Drawing.PointF.Y%2A> membro dati di un <xref:System.Drawing.PointF> oggetto. La coordinata y viene aumentata di `font.Height` per ogni nuova riga di testo. Il <xref:System.Drawing.Font.Height%2A> proprietà di un <xref:System.Drawing.Font> object restituisce l'interlinea, in pixel, per questo specifico <xref:System.Drawing.Font> oggetto. In questo esempio, il numero restituito da <xref:System.Drawing.Font.Height%2A> è 19. Si noti che questo è lo stesso come numero (arrotondato per eccesso a un numero intero) ottenuto tramite la conversione della metrica interlinea in pixel.  
  
 Si noti che l'altezza em (detto anche dimensione o dimensione em) non è la somma della parte ascendente e la parte discendente. La somma della parte superiore e la parte discendente viene chiamata l'altezza della cella. Altezza della cella meno lo spazio iniziale interno è uguale all'altezza em. Altezza della cella più esterno iniziale è uguale all'interlinea.  
  
 [!code-csharp[System.Drawing.FontsAndText#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)

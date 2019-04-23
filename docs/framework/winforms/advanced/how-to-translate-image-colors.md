---
title: 'Procedura: Convertire i colori delle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 04e61383ef79b17ea6e1523588cd9593ec9b082c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132639"
---
# <a name="how-to-translate-image-colors"></a>Procedura: Convertire i colori delle immagini
Una traduzione aggiunge un valore a una o più di quattro componenti di colore. Le voci di matrice di colori che rappresentano le traduzioni sono indicate nella tabella seguente.  
  
|Componente da tradurre|Voce della matrice|  
|--------------------------------|------------------|  
|Rosso|[4][0]|  
|Verde|[4][1]|  
|Blu|[4][2]|  
|Alfa|[4][3]|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto ColorBars nel file. Il codice aggiunge quindi 0,75 per il componente rosso di ogni pixel nell'immagine. Accanto all'immagine trasformata viene disegnata l'immagine originale.  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine trasformato a destra:  
  
 ![Screenshot dell'immagine originale e trasformato.](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo la traduzione di colore rosso. Si noti che, poiché il valore massimo per un componente di colore è 1, non modificare il componente rossa nella seconda riga. (In modo analogo, il valore minimo per un componente di colore è 0.)  
  
|Originale|Tradotta|  
|--------------|----------------|  
|Black (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Rosso (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Green (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Blue (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>. Sostituire `ColorBars.bmp` con un nome file di immagine e il percorso che sono validi per il sistema.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](recoloring-images.md)

---
title: 'Procedura: convertire i colori delle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 48f506f76ff6e9ca648822d073b6f6a852b9ca8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-translate-image-colors"></a>Procedura: convertire i colori delle immagini
Una traduzione aggiunge un valore a una o più di quattro componenti di colore. Le voci della matrice di colori che rappresentano le traduzioni sono indicate nella tabella riportata di seguito.  
  
|Componente da convertire|Voce della matrice|  
|--------------------------------|------------------|  
|Rosso|[4][0]|  
|Verde|[4][1]|  
|Blu|[4][2]|  
|Alfa|[4][3]|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file ColorBars. Il codice aggiunge quindi 0,75 per il componente rosso di ogni pixel dell'immagine. L'immagine originale viene disegnato accanto all'immagine trasformata.  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine trasformato a destra.  
  
 ![Conversione dei colori](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")  
  
 Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo la conversione di colore rossa. Si noti che, poiché il valore massimo per un componente di colore è 1, non modificare il componente rosso nella seconda riga. (In modo analogo, il valore minimo per un componente di colore è 0.)  
  
|Originale|Tradotta|  
|--------------|----------------|  
|Nero (0, 0, 0, 1)|(0.75, 0, 0, 1)|  
|Rosso (1, 0, 0, 1)|(1, 0, 0, 1)|  
|Verde (0, 1, 0, 1)|(0.75, 1, 0, 1)|  
|Blu (0, 0, 1, 1)|(0.75, 0, 1, 1)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Sostituire `ColorBars.bmp` con un nome di file di immagine e un percorso valido per il sistema.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Ricolorazione di immagini](../../../../docs/framework/winforms/advanced/recoloring-images.md)

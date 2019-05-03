---
title: 'Procedura: Ruotare i colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 241d2824fc2d87a0505eb6e790c865bfa7d8ef90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967357"
---
# <a name="how-to-rotate-colors"></a>Procedura: Ruotare i colori
È difficile identificare la rotazione in uno spazio dei colori quadridimensionale. Abbiamo possiamo fare in modo più semplice visualizzare rotazione, supponendo di mantenere uno dei componenti di colore fisso. Si supponga di mantenere il componente alfa fissato a 1 (completamente opaco). Quindi è possibile visualizzare uno spazio tridimensionale colore degli assi del colore rosso, verde e blu come illustrato nella figura seguente.  
  
 ![Figura che illustra la rotazione con gli assi di colore rosso, verdi e blu.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 Un colore può essere considerato come un punto nello spazio 3D. Ad esempio, il punto nello spazio (1, 0, 0) rappresenta il colore rosso e il punto (0, 1, 0) nello spazio rappresenta il colore verde.  
  
 La figura seguente illustra che cosa significa ruotare i colori (1, 0, 0) di un angolo di 60 gradi nel piano di rosso-verde. Rotazione in un piano parallelo per il piano rosso-verde può essere considerata come una rotazione intorno all'asse blu.  
  
 ![Figura che illustra la rotazione intorno all'asse blu.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 Nella figura seguente viene illustrato come inizializzare una matrice di colori per eseguire le rotazioni su ciascuno dei tre assi coordinati (rosso, verde, blu):  
  
 ![Inizializzare una matrice di colori per eseguire le rotazioni sui tre assi.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente accetta un'immagine è monocromatica (1, 0, 0.6) e si applica una rotazione di 60 gradi intorno all'asse blu. L'angolo di rotazione viene effettuata su un piano parallelo per il piano rosso-verde.  
  
 La figura seguente mostra l'immagine originale sulla sinistra e l'immagine ruotata colori a destra:  
  
 ![Figura che Mostra immagine originale e l'immagine ruotata di colore.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 La figura seguente mostra una visualizzazione della rotazione colore eseguita nel codice seguente:
  
 ![Figura che mostra la visualizzazione di rotazione del colore.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>. Sostituire `RotationInput.bmp` con un nome file di immagine e un percorso valido nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](recoloring-images.md)

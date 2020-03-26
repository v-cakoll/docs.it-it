---
title: 'Procedura: ruotare i colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111335"
---
# <a name="how-to-rotate-colors"></a>Procedura: ruotare i colori
La rotazione in uno spazio colore quadridimensionale è difficile da visualizzare. Possiamo rendere più facile visualizzare la rotazione accettando di mantenere fisso uno dei componenti di colore. Supponiamo di accettare di mantenere il componente alfa fisso a 1 (completamente opaco). Quindi possiamo visualizzare uno spazio colore tridimensionale con gli assi rosso, verde e blu, come illustrato nella figura seguente.  
  
 ![Illustrazione che mostra la rotazione con assi rossi, verdi e blu.](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 Un colore può essere considerato come un punto nello spazio 3D. Ad esempio, il punto (1, 0, 0) nello spazio rappresenta il colore rosso e il punto (0, 1, 0) nello spazio rappresenta il colore verde.  
  
 La figura seguente mostra cosa significa ruotare il colore (1, 0, 0) attraverso un angolo di 60 gradi nel piano rosso-verde. La rotazione in un piano parallelo al piano rosso-verde può essere considerata come rotazione intorno all'asse blu.  
  
 ![Illustrazione che mostra la rotazione attorno all'asse blu.](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 Nella figura seguente viene illustrato come inizializzare una matrice di colori per eseguire rotazioni su ciascuno dei tre assi di coordinate (rosso, verde, blu):  
  
 ![Inizializzare una matrice di colori per eseguire rotazioni su tre assi.](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>Esempio  
 L'esempio seguente prende un'immagine che è tutto un colore (1, 0, 0,6) e applica una rotazione di 60 gradi intorno all'asse blu. L'angolo di rotazione viene spazzato via in un piano parallelo al piano rosso-verde.  
  
 La figura seguente mostra l'immagine originale a sinistra e l'immagine ruotata a colori a destra:  
  
 ![Illustrazione che mostra l'immagine originale e l'immagine ruotata a colori.](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 Nella figura seguente viene illustrata una visualizzazione della rotazione dei colori eseguita nel codice seguente:
  
 ![Illustrazione che mostra la visualizzazione della rotazione del colore.](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'utilizzo con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi. Sostituire `RotationInput.bmp` con un nome di file di immagine e un percorso validi nel sistema.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](recoloring-images.md)

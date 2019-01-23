---
title: 'Procedura: Rotazione dei colori'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 6c4f41504911e94673707d99d804fad5b228599e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503066"
---
# <a name="how-to-rotate-colors"></a>Procedura: Rotazione dei colori
È difficile identificare la rotazione in uno spazio dei colori quadridimensionale. Abbiamo possiamo fare in modo più semplice visualizzare rotazione, supponendo di mantenere uno dei componenti di colore fisso. Si supponga di mantenere il componente alfa fissato a 1 (completamente opaco). Quindi è possibile visualizzare uno spazio tridimensionale colore degli assi del colore rosso, verde e blu come illustrato nella figura seguente.  
  
 ![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")  
  
 Un colore può essere considerato come un punto nello spazio 3D. Ad esempio, il punto nello spazio (1, 0, 0) rappresenta il colore rosso e il punto (0, 1, 0) nello spazio rappresenta il colore verde.  
  
 La figura seguente illustra che cosa significa ruotare i colori (1, 0, 0) di un angolo di 60 gradi nel piano di rosso-verde. Rotazione in un piano parallelo per il piano rosso-verde può essere considerata come una rotazione intorno all'asse blu.  
  
 ![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")  
  
 Nella figura seguente viene illustrato come inizializzare una matrice di colori per eseguire le rotazioni su ciascuno dei tre assi coordinati (rosso, verde, blu).  
  
 ![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente accetta un'immagine è monocromatica (1, 0, 0.6) e si applica una rotazione di 60 gradi intorno all'asse blu. L'angolo di rotazione viene effettuata su un piano parallelo per il piano rosso-verde.  
  
 La figura seguente mostra l'immagine originale sulla sinistra e l'immagine ruotata colori a destra.  
  
 ![Ruotare i colori](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")  
  
 La figura seguente mostra una visualizzazione della rotazione colore eseguita nel codice seguente.  
  
 ![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Sostituire `RotationInput.bmp` con un nome file di immagine e un percorso valido nel sistema.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](../../../../docs/framework/winforms/advanced/recoloring-images.md)

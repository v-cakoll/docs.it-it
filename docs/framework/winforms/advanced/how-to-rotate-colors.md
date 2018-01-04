---
title: 'Procedura: ruotare i colori'
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
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81b022011bd5613b8e956aa83482d2836508a4f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-colors"></a>Procedura: ruotare i colori
Rotazione in uno spazio colore quadridimensionale è difficile da visualizzare. È possibile rendere più semplice per visualizzare la rotazione, supponendo di mantenere uno dei componenti di colore predefiniti. Si supponga di mantenere il componente alfa pari a 1 (completamente opaco). È quindi possibile visualizzare uno spazio tridimensionale colore degli assi del rosso, verde e blu come illustrato nella figura seguente.  
  
 ![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")  
  
 Un colore può essere considerato come un punto nello spazio 3D. Ad esempio, il punto in uno spazio (1, 0, 0) rappresenta il colore rosso e il punto in uno spazio (0, 1, 0) rappresenta il colore verde.  
  
 Nell'illustrazione seguente significato ruotare il colore (1, 0, 0) di un angolo di 60 gradi nel piano verde a rosso. Rotazione in un piano parallelo al piano verde a rosso può essere considerata come la rotazione intorno all'asse blu.  
  
 ![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")  
  
 Nella figura seguente viene illustrato come inizializzare una matrice di colori per eseguire rotazioni su ciascuno dei tre assi delle coordinate (rosso, verde e blu).  
  
 ![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente accetta un'immagine è monocromatica (1, 0, 0,6) e applica una rotazione di 60 gradi sull'asse del blu. Angolo di rotazione viene effettuata su un piano parallelo al piano verde a rosso.  
  
 Nella figura seguente mostra l'immagine originale sulla sinistra e l'immagine ruotata colore a destra.  
  
 ![Rotazione dei colori](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")  
  
 Nella figura seguente mostra una visualizzazione della rotazione colore eseguita nel codice seguente.  
  
 ![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Sostituire `RotationInput.bmp` con un nome di file di immagine e un percorso valido per il sistema.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Ricolorazione di immagini](../../../../docs/framework/winforms/advanced/recoloring-images.md)

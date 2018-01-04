---
title: 'Procedura: utilizzare una matrice di colori per impostare i valori alfa nelle immagini'
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
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dde9417782e4404237a995364d65058f023c3e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Procedura: utilizzare una matrice di colori per impostare i valori alfa nelle immagini
Il <xref:System.Drawing.Bitmap> classe (che eredita dalla classe di <xref:System.Drawing.Image> classe) e <xref:System.Drawing.Imaging.ImageAttributes> classe fornisce la funzionalità per ottenere e impostare i valori pixel. È possibile utilizzare il <xref:System.Drawing.Imaging.ImageAttributes> i valori di classe per modificare il canale alfa per un'intera immagine, oppure è possibile chiamare il <xref:System.Drawing.Bitmap.SetPixel%2A> metodo la <xref:System.Drawing.Bitmap> classe per modificare i valori dei singoli pixel.  
  
## <a name="example"></a>Esempio  
 La <xref:System.Drawing.Imaging.ImageAttributes> classe dispone di molte proprietà che è possibile utilizzare per modificare le immagini durante il rendering. Nell'esempio seguente, un <xref:System.Drawing.Imaging.ImageAttributes> oggetto utilizzato per impostare tutti i valori alfa all'80% del valore precedente. Questa operazione viene eseguita l'inizializzazione di una matrice di colori e impostando il valore della matrice su 0,8 di adattamento alfa. L'indirizzo della matrice di colori viene passato per il <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo il <xref:System.Drawing.Imaging.ImageAttributes> oggetto e <xref:System.Drawing.Imaging.ImageAttributes> oggetto viene passato al <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> oggetto.  
  
 Durante il rendering, i valori alfa nella mappa di bit vengono convertiti all'80% del valore precedente. Il risultato di un'immagine che viene sfumata con lo sfondo. Come mostrato nella figura seguente, l'immagine bitmap è trasparente; è possibile visualizzare la riga di colore nera a tinta unita attraverso di esso.  
  
 ![Fusione alfa con una matrice](../../../../docs/framework/winforms/advanced/media/image2.png "immagine2")  
  
 In cui l'immagine sulla parte dello sfondo bianca, l'immagine viene sfumata con il colore bianco. In cui l'immagine incroci la linea di colore nera, l'immagine viene sfumato con il colore nero.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Linee e riempimenti con fusione alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)

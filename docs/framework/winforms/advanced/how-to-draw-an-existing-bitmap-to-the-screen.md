---
title: 'Procedura: disegnare una bitmap esistente sullo schermo'
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
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f435c397832e8f64b2bf911a59aae7578ffd3bdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Procedura: disegnare una bitmap esistente sullo schermo
Nella schermata, è possibile creare facilmente un'immagine esistente. È necessario innanzitutto creare un <xref:System.Drawing.Bitmap> oggetto utilizzando il costruttore di bitmap che accetta un nome file, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>. Questo costruttore accetta immagini con vari formati di file, tra cui BMP, GIF, JPEG, PNG e TIFF. Dopo aver creato il <xref:System.Drawing.Bitmap> dell'oggetto, quindi passare tale <xref:System.Drawing.Bitmap> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene creato un <xref:System.Drawing.Bitmap> oggetto da un file JPEG, quindi viene disegnata la bitmap con il relativo angolo superiore sinistro a (60, 10).  
  
 Nella figura seguente mostra la bitmap disegnata in corrispondenza della posizione specificata.  
  
 ![Immagine di posizione](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

---
title: 'Procedura: Carico e visualizzare metafile'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: d0835d7f2c5ffea44f22661a765ab16b1d0130c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619558"
---
# <a name="how-to-load-and-display-metafiles"></a>Procedura: Carico e visualizzare metafile
Il <xref:System.Drawing.Imaging.Metafile> classe che eredita dal <xref:System.Drawing.Image> classe, fornisce i metodi per la registrazione, la visualizzazione e analisi di immagini vettoriali.  
  
## <a name="example"></a>Esempio  
 Per visualizzare un'immagine di vettoriali (metafile) sullo schermo, è necessario un <xref:System.Drawing.Imaging.Metafile> oggetto e un <xref:System.Drawing.Graphics> oggetto. Passare il nome di un file (o un flusso) per un <xref:System.Drawing.Imaging.Metafile> costruttore. Dopo aver creato un <xref:System.Drawing.Imaging.Metafile> dell'oggetto, quindi passare tale <xref:System.Drawing.Imaging.Metafile> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
 Nell'esempio viene creato un <xref:System.Drawing.Imaging.Metafile> oggetto da un file EMF (metafile avanzato), quindi viene disegnata l'immagine con relativo angolo superiore sinistro a (60, 10).  
  
 La figura seguente mostra il metafile disegnato in corrispondenza della posizione specificata.  
  
 ![Posizione di immagine](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche
- [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

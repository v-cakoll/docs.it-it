---
title: 'Procedura: Caricare e visualizzare metafile'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 39b7251b2789c7410e1d59b4aa7990a2f73055fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229355"
---
# <a name="how-to-load-and-display-metafiles"></a>Procedura: Caricare e visualizzare metafile
Il <xref:System.Drawing.Imaging.Metafile> classe che eredita dal <xref:System.Drawing.Image> classe, fornisce i metodi per la registrazione, la visualizzazione e analisi di immagini vettoriali.  
  
## <a name="example"></a>Esempio  
 Per visualizzare un'immagine di vettoriali (metafile) sullo schermo, è necessario un <xref:System.Drawing.Imaging.Metafile> oggetto e un <xref:System.Drawing.Graphics> oggetto. Passare il nome di un file (o un flusso) per un <xref:System.Drawing.Imaging.Metafile> costruttore. Dopo aver creato un <xref:System.Drawing.Imaging.Metafile> dell'oggetto, quindi passare tale <xref:System.Drawing.Imaging.Metafile> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
 Nell'esempio viene creato un <xref:System.Drawing.Imaging.Metafile> oggetto da un file EMF (metafile avanzato), quindi viene disegnata l'immagine con relativo angolo superiore sinistro a (60, 10).  
  
 La figura seguente mostra il metafile disegnato in corrispondenza della posizione specificata.  
  
 ![Posizione di immagine](./media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)

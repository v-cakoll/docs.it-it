---
title: 'Procedura: caricare e visualizzare metafile'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424806"
---
# <a name="how-to-load-and-display-metafiles"></a>Procedura: caricare e visualizzare metafile
La classe <xref:System.Drawing.Imaging.Metafile>, che eredita dalla classe <xref:System.Drawing.Image>, fornisce metodi per la registrazione, la visualizzazione e l'analisi di immagini vettoriali.  
  
## <a name="example"></a>Esempio  
 Per visualizzare un'immagine vettoriale (Metafile) sullo schermo, è necessario un oggetto <xref:System.Drawing.Imaging.Metafile> e un oggetto <xref:System.Drawing.Graphics>. Passare il nome di un file (o di un flusso) a un costruttore <xref:System.Drawing.Imaging.Metafile>. Dopo aver creato un oggetto <xref:System.Drawing.Imaging.Metafile>, passare l'oggetto <xref:System.Drawing.Imaging.Metafile> al metodo <xref:System.Drawing.Graphics.DrawImage%2A> di un oggetto <xref:System.Drawing.Graphics>.  
  
 Nell'esempio viene creato un oggetto <xref:System.Drawing.Imaging.Metafile> da un file EMF (Enhanced Metafile), quindi viene disegnata l'immagine con l'angolo superiore sinistro in (60, 10).  
  
 Nella figura seguente viene illustrato il metafile disegnato nella posizione specificata.  
  
 ![Screenshot che mostra la posizione dell'immagine.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del gestore dell'evento <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)

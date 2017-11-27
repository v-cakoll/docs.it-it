---
title: 'Procedura: caricare e visualizzare metafile'
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
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 722b6d36801c69e500535a32e952ef8f45634d03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-load-and-display-metafiles"></a>Procedura: caricare e visualizzare metafile
Il <xref:System.Drawing.Imaging.Metafile> classe che eredita la <xref:System.Drawing.Image> classe, fornisce metodi per la registrazione, la visualizzazione e l'esame di immagini vettoriali.  
  
## <a name="example"></a>Esempio  
 Per visualizzare un'immagine di vettoriali (metafile) sullo schermo, è necessario un <xref:System.Drawing.Imaging.Metafile> oggetto e un <xref:System.Drawing.Graphics> oggetto. Passare il nome di un file (o un flusso) a un <xref:System.Drawing.Imaging.Metafile> costruttore. Dopo aver creato un <xref:System.Drawing.Imaging.Metafile> dell'oggetto, quindi passare tale <xref:System.Drawing.Imaging.Metafile> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
 Nell'esempio viene creato un <xref:System.Drawing.Imaging.Metafile> oggetto da un file EMF (enhanced metafile, metafile) e quindi disegna l'immagine con il relativo angolo superiore sinistro a (60, 10).  
  
 Nella figura seguente viene illustrato il metafile disegnato nella posizione specificata.  
  
 ![Immagine di posizione](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

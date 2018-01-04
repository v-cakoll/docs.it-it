---
title: 'Procedura: ritagliare e adattare immagini'
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
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de905cf70013098a4282e3f4af092ccbea16ccfd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-crop-and-scale-images"></a>Procedura: ritagliare e adattare immagini
Il <xref:System.Drawing.Graphics> classe sono disponibili numerosi <xref:System.Drawing.Graphics.DrawImage%2A> metodi, alcuni dei quali dispongono di parametri dei rettangoli di origine e di destinazione che è possibile usare per ritagliare e adattare le immagini.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file di disco Apple. Il codice disegna l'immagine intera apple nelle dimensioni originali. Il codice chiama quindi il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto su cui disegnare una parte dell'immagine di apple in un rettangolo di destinazione che è maggiore dell'immagine originale.  
  
 Il <xref:System.Drawing.Graphics.DrawImage%2A> metodo determina la porzione di apple per disegnare esaminando il rettangolo di origine, specificato dal terzo, quarto, quinto e sesto argomento. In questo caso, la mela verrà ridotta al 75% della larghezza e il 75% dell'altezza.  
  
 Il <xref:System.Drawing.Graphics.DrawImage%2A> metodo consente di determinare la posizione in cui disegnare la mela e quali dimensioni ritagliata esaminando il rettangolo di destinazione, specificato dal secondo argomento. In questo caso, il rettangolo di destinazione è maggiore del 30% e il 30% più alto rispetto all'originale.  
  
 Nella figura seguente viene illustrato l'originale e l'immagine adattata, ritagliata.  
  
 ![Ritaglio e adattamento](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>. Assicurarsi di sostituire `Apple.gif` con un nome di file di immagine e un percorso valido per il sistema.  
  
## <a name="see-also"></a>Vedere anche  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

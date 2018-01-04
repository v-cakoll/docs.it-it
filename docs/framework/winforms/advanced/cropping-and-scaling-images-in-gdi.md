---
title: Ritaglio e ridimensionamento di immagini in GDI+
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
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0bbe7ac4b8c541ea76392f94f538e41816cf5c3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a>Ritaglio e ridimensionamento di immagini in GDI+
È possibile utilizzare il <xref:System.Drawing.Graphics.DrawImage%2A> metodo la <xref:System.Drawing.Graphics> classe per creare e posizionare immagini vettoriali e raster immagini. <xref:System.Drawing.Graphics.DrawImage%2A>è un metodo di overload, pertanto vi sono diversi modi, è possibile fornire argomenti.  
  
## <a name="drawimage-variations"></a>DrawImage varianti  
 Una variazione del <xref:System.Drawing.Graphics.DrawImage%2A> metodo riceve un <xref:System.Drawing.Bitmap> e <xref:System.Drawing.Rectangle>. Il rettangolo specifica la destinazione per l'operazione di disegno. specifica, ovvero il rettangolo in cui disegnare l'immagine. Se le dimensioni del rettangolo di destinazione sono diversa dalla dimensione dell'immagine originale, l'immagine viene adattata al rettangolo di destinazione. Esempio di codice seguente viene illustrato come disegnare l'immagine stessa tre volte: una volta senza ridimensionamento, una volta con un'espansione e una volta con compressione:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 Nella figura seguente mostra le tre immagini.  
  
 ![Scalabilità](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 Alcune varianti del <xref:System.Drawing.Graphics.DrawImage%2A> metodo dispone di un parametro del rettangolo di origine, nonché un parametro del rettangolo di destinazione. Il parametro del rettangolo di origine specifica la parte dell'immagine originale da disegnare. Il rettangolo di destinazione specifica il rettangolo in cui disegnare la parte dell'immagine. Se le dimensioni del rettangolo di destinazione sono diversa dalla dimensione del rettangolo di origine, l'immagine viene adattata al rettangolo di destinazione.  
  
 Esempio di codice seguente viene illustrato come costruire un <xref:System.Drawing.Bitmap> dal file Runner. Senza ridimensionamento in cui viene disegnata l'immagine intera (0, 0). Una piccola parte dell'immagine viene disegnato due volte: una volta con una compressione e una volta con un'espansione.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 Nella figura seguente mostra l'immagine non in scala e le parti di immagine espanso e compresso.  
  
 ![Ritaglio e ridimensionamento](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>Vedere anche  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

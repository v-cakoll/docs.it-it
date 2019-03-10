---
title: "Procedura: Usare la modalità di interpolazione per controllare la qualità dell'immagine durante il ridimensionamento"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 83f1e569f1fb1ae49143f4ed11837759df29fe79
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721957"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>Procedura: Usare la modalità di interpolazione per controllare la qualità dell'immagine durante il ridimensionamento
La modalità di interpolazione di un' <xref:System.Drawing.Graphics> oggetto influenza il modo [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] immagini (vengono adattati). Il <xref:System.Drawing.Drawing2D.InterpolationMode> enumerazione definisce diverse modalità di interpolazione, alcuni dei quali vengono visualizzati nell'elenco seguente:  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 Per estendere un'immagine, ogni pixel dell'immagine originale deve essere mappato a un gruppo di pixel dell'immagine più grande. Per compattare un'immagine, i gruppi di pixel dell'immagine originale devono essere mappati a singolo pixel dell'immagine più piccola. L'efficacia degli algoritmi di eseguire questi mapping determina la qualità delle immagini ridimensionate. Gli algoritmi che producono le immagini in scala di qualità superiore tendono a richiedere più tempo di elaborazione. Nell'elenco precedente, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> è la modalità di qualità più bassa e <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> è la modalità di qualità elevata.  
  
 Per impostare la modalità di interpolazione, assegnare uno dei membri del <xref:System.Drawing.Drawing2D.InterpolationMode> enumerazione per il <xref:System.Drawing.Graphics.InterpolationMode%2A> proprietà di un <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente disegna un'immagine e quindi Compatta l'immagine con tre diverse modalità di interpolazione.  
  
 La figura seguente mostra l'immagine originale e le tre immagini più piccole.  
  
 ![Immagine con varie impostazioni di interpolazione](./media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche
- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)

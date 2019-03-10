---
title: 'Procedura: Disegnare una Bitmap esistente sullo schermo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
ms.openlocfilehash: a23026e0ac377294e3e4356d341c45d31b4ecd79
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724440"
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Procedura: Disegnare una Bitmap esistente sullo schermo
È possibile creare facilmente un'immagine esistente sullo schermo. Prima di tutto è necessario creare un <xref:System.Drawing.Bitmap> utilizzando il costruttore di mappa di bit che accetta un nome file, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>. Questo costruttore accetta le immagini con diversi formati di file diversi, tra cui BMP, GIF, JPEG, PNG e TIFF. Dopo aver creato il <xref:System.Drawing.Bitmap> dell'oggetto, quindi passare tale <xref:System.Drawing.Bitmap> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="example"></a>Esempio  
 Questo esempio viene creato un <xref:System.Drawing.Bitmap> oggetto da un file JPEG e quindi consente di disegnare la bitmap con relativo angolo superiore sinistro a (60, 10).  
  
 La figura seguente mostra la bitmap disegnata in corrispondenza della posizione specificata.  
  
 ![Posizione di immagine](./media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Utilizzo di immagini, bitmap, icone e metafile](working-with-images-bitmaps-icons-and-metafiles.md)

---
title: 'Procedura: Ruotare, riflettere e inclinare immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 2150e7797095b88227b499ec5481a3ce521270e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54667911"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Procedura: Ruotare, riflettere e inclinare immagini
È possibile ruotare, riflettere e inclinare un'immagine specificando i punti di destinazione per gli angoli superiore sinistro, superiore destro e inferiore sinistro dell'immagine originale. I tre punti di destinazione determinano una trasformazione affine che esegue il mapping dell'immagine rettangolare originale in un parallelogramma.  
  
## <a name="example"></a>Esempio  
 Ad esempio, si supponga che l'immagine originale è un rettangolo con angoli superiore sinistro (0, 0), nell'angolo superiore destro a (100, 0) e nell'angolo inferiore sinistro a (0, 50). Ora si supponga che si esegue il mapping di questi tre punti per i punti di destinazione come indicato di seguito.  
  
|Punto originale|Punto di destinazione|  
|--------------------|-----------------------|  
|Angolo superiore sinistro (0, 0)|(200, 20)|  
|Angolo superiore destro (100, 0)|(110, 100)|  
|Basso-sinistra (0, 50)|(250, 30)|  
  
 Nella figura seguente mostra l'immagine originale e l'immagine associata nel parallelogramma. L'immagine originale è stato asimmetriche, riflessa, ruotata e convertito. L'asse x lungo il bordo superiore dell'immagine originale viene eseguito il mapping alla riga che viene eseguito tramite (200, 20) e (110, 100). L'asse y lungo il bordo sinistro dell'immagine originale viene eseguito il mapping alla riga che viene eseguito tramite (200, 20) e (250, 30).  
  
 ![Strisce](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 Nella figura seguente mostra una trasformazione simile applicata a un'immagine fotografica.  
  
 ![Trasformate scalatore](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 Nella figura seguente mostra una trasformazione simile applicata a un metafile.  
  
 ![Trasformate Metafile](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 L'esempio seguente produce le immagini mostrate nella prima figura.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento. Assicurarsi di sostituire `Stripes.bmp` con il percorso di un'immagine valida nel sistema.  
  
## <a name="see-also"></a>Vedere anche
- [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

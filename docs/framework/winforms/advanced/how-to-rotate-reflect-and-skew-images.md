---
title: 'Procedura: ruotare, riflettere e inclinare immagini'
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
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eaa6286731d196dad387e1648644ca3e8103da03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-rotate-reflect-and-skew-images"></a>Procedura: ruotare, riflettere e inclinare immagini
È possibile ruotare, riflettere e inclinare un'immagine, specificando i punti di destinazione per gli angoli superiore sinistro, superiore destro e inferiore sinistro dell'immagine originale. I punti di tre destinazione determinano una trasformazione affine che esegue il mapping dell'immagine rettangolare originale in un parallelogramma.  
  
## <a name="example"></a>Esempio  
 Ad esempio, si supponga che l'immagine originale è un rettangolo con angoli superiore sinistro (0, 0), nell'angolo superiore destro in (100, 0) e nell'angolo inferiore sinistro a (0, 50). Ora si supponga che si esegue il mapping di quelli di tre punti ai punti di destinazione come indicato di seguito.  
  
|Punto originale|Punto di destinazione|  
|--------------------|-----------------------|  
|Alto-sinistra (0, 0)|(200, 20)|  
|Alto-destra (100, 0)|(110, 100)|  
|Basso-sinistra (0, 50)|(250, 30)|  
  
 Nella figura seguente mostra l'immagine originale e l'immagine associata al parallelogramma. L'immagine originale è stata inclinata, riflessa, ruotata e convertito. L'asse x lungo il bordo superiore dell'immagine originale viene eseguito il mapping alla riga in cui viene eseguito tramite (200, 20) e (110, 100). L'asse y lungo il bordo sinistro dell'immagine originale viene eseguito il mapping alla riga in cui viene eseguito tramite (200, 20) e (250, 30).  
  
 ![Strisce](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")  
  
 Nella figura seguente mostra una trasformazione analoga applicata a un'immagine fotografica.  
  
 ![Aumento trasformato](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")  
  
 Nella figura seguente mostra una trasformazione analoga applicata a un metafile.  
  
 ![Trasformato Metafile](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")  
  
 Nell'esempio seguente genera le immagini mostrate nella prima figura.  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>. Assicurarsi di sostituire `Stripes.bmp` con il percorso di un'immagine che è valido per il sistema.  
  
## <a name="see-also"></a>Vedere anche  
 [Utilizzo di immagini, bitmap, icone e metafile](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)

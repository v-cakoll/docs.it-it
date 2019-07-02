---
title: Linee e riempimenti con fusione alfa
ms.date: 03/30/2017
helpviewer_keywords:
- lines [Windows Forms], adding transparency
- examples [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with lines
- alpha blending
- lines [Windows Forms], alpha blending
- fills [Windows Forms], alpha blending
- alpha blending [Windows Forms], using with fills
- shapes [Windows Forms], adding transparency
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
ms.openlocfilehash: 66061341ee6539e2172c537a0b2a6ec9ff87565c
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506115"
---
# <a name="alpha-blending-lines-and-fills"></a>Linee e riempimenti con fusione alfa
In GDI+, un colore è un valore a 32 bit con 8 bit per ciascun alfa, rosso, verde e blu. Il valore alfa indica la trasparenza del colore, ovvero l'entità a cui il colore viene sfumato con il colore di sfondo. I valori alfa sono compresi tra 0 e 255 e 255, dove 0 rappresenta un colore completamente trasparente, rappresenta un colore completamente opaco.  
  
 Fusione alfa è una fusione pixel per pixel di dati di colori di origine e di sfondo. Ognuno dei tre componenti (rosso, verde, blu) di un colore di origine specificato viene sfumato con il componente corrispondente del colore di sfondo in base alla formula seguente:  
  
 Colore_di_visualizzazione = Colore_di_origine × alfa / 255 + backgroundColor × (255-alfa) / 255  
  
 Si supponga, ad esempio, il componente rossa del colore di origine è 150 e il componente rossa del colore di sfondo è 100. Se il valore alfa è 200, il componente rossa del colore risultante viene calcolato come segue:  
  
 150 × 200 / 255 + 100 × (255 – 200) / 255 = 139  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Disegnare linee opache e semitrasparenti](how-to-draw-opaque-and-semitransparent-lines.md)  
 Illustra come disegnare linee con fusione alfa.  
  
 [Procedura: Disegnare con pennelli opachi e semitrasparenti](how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 Viene illustrato come la fusione alfa con pennelli.  
  
 [Procedura: Usare la modalità di composizione per controllare la fusione alfa](how-to-use-compositing-mode-to-control-alpha-blending.md)  
 Viene descritto come controllare la fusione alfa utilizzando <xref:System.Drawing.Drawing2D.CompositingMode>.  
  
 [Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini](how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 Viene illustrato come utilizzare un <xref:System.Drawing.Imaging.ColorMatrix> oggetto da controllare la fusione alfa.

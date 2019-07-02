---
title: Utilizzo delle trasformazioni per scalare i colori
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504958"
---
# <a name="using-transformations-to-scale-colors"></a>Utilizzo delle trasformazioni per scalare i colori
Una trasformazione di ridimensionamento Moltiplica uno o più di quattro componenti di colore da un numero. Le voci di matrice di colore che rappresentano la scalabilità sono indicate nella tabella seguente.  
  
|Componente di scalabilità|Voce della matrice|  
|----------------------------|------------------|  
|Rosso|[0][0]|  
|Verde|[1][1]|  
|Blu|[2][2]|  
|Alfa|[3][3]|  
  
## <a name="scaling-one-color"></a>Adattamento di un colore  
 Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars2 nel file. Il codice quindi ridimensiona il componente blu di ciascun pixel nell'immagine di un fattore pari a 2. Accanto all'immagine trasformata viene disegnata l'immagine originale.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra:  
  
 ![Screenshot che confronta i colori originali e in scala.](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo il ridimensionamento blu. Si noti che il componente blu nella barra dei colori quarto passato da 0,8 a 0,6. Ciò avviene perché GDI+ mantiene solo la parte frazionaria del risultato. Ad esempio, (2)(0.8) Version=1.6, e la parte frazionaria di 1.6 è 0,6. Mantenendo solo la parte frazionaria garantisce che il risultato è sempre nell'intervallo [0, 1].  
  
|Originale|Scalabilità|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>Adattamento dei colori più  
 Nell'esempio seguente si costruisce un <xref:System.Drawing.Image> oggetto Colorbars2 nel file. Il codice quindi ridimensiona i componenti rossi, verdi e blu di ogni pixel nell'immagine. I componenti rosso sono stati ridotti del 25%, i componenti verdi sono stati ridotti del 35% e i componenti blu sono stati ridotti al 50%.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra:  
  
 ![Screenshot che confronta i colori originali e in scala.](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 La tabella seguente elenca i vettori di colore per le quattro barre prima e dopo il ridimensionamento rosso, verde e blu.  
  
|Originale|Scalabilità|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Ricolorazione di immagini](recoloring-images.md)

---
title: Utilizzo delle trasformazioni per scalare i colori
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
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7515f34858ef6f4b0495ac6fc545ae498d45c7f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-transformations-to-scale-colors"></a>Utilizzo delle trasformazioni per scalare i colori
Una trasformazione di ridimensionamento Moltiplica uno o più di quattro componenti di colore da un numero. Le voci della matrice di colori che rappresentano l'adattamento sono indicate nella tabella riportata di seguito.  
  
|Componente scalabilità|Voce della matrice|  
|----------------------------|------------------|  
|Rosso|[0][0]|  
|Verde|[1][1]|  
|Blu|[2][2]|  
|Alfa|[3][3]|  
  
## <a name="scaling-one-color"></a>Adattamento di un colore  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file Colorbars2. Il codice quindi ridimensiona il componente blu di ciascun pixel nell'immagine di un fattore pari a 2. L'immagine originale viene disegnato accanto all'immagine trasformata.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra.  
  
 ![Scalare i colori](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo il ridimensionamento blu. Si noti che il componente blu nella quarta barra di colore è passato da 0,8 a 0,6. Ciò accade perché [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] mantiene solo la parte frazionaria del risultato. Ad esempio, (2)(0.8) = 1.6, e la parte frazionaria 1.6 è 0,6. Mantenendo solo la parte frazionaria assicura che il risultato è sempre nell'intervallo [0, 1].  
  
|Originale|Scala|  
|--------------|------------|  
|(0.4, 0.4, 0.4, 1)|(0.4, 0.4, 0.8, 1)|  
|(0.4, 0.2, 0.2, 1)|(0.4, 0.2, 0.4, 1)|  
|(0.2, 0.4, 0.2, 1)|(0.2, 0.4, 0.4, 1)|  
|(0.4, 0.4, 0.8, 1)|(0.4, 0.4, 0.6, 1)|  
  
## <a name="scaling-multiple-colors"></a>Adattamento dei colori più  
 Nell'esempio seguente viene costruito un <xref:System.Drawing.Image> oggetto dal file Colorbars2. Il codice quindi ridimensiona i componenti rossi, verde e blu di ciascun pixel dell'immagine. I componenti rossi sono ridotte del 25% e vengono ridimensionati i componenti di colore verde del 35% vengono ridimensionati i componenti di colore blu del 50%.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine adattata a destra.  
  
 ![Scalare i colori](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 Nella tabella seguente sono elencati i vettori di colore per le quattro barre prima e dopo il ridimensionamento rosso, verde e blu.  
  
|Originale|Scala|  
|--------------|------------|  
|(0.6, 0.6, 0.6, 1)|(0.45, 0.39, 0.3, 1)|  
|(0, 1, 1, 1)|(0, 0.65, 0.5, 1)|  
|(1, 1, 0, 1)|(0.75, 0.65, 0, 1)|  
|(1, 0, 1, 1)|(0.75, 0, 0.5, 1)|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Ricolorazione di immagini](../../../../docs/framework/winforms/advanced/recoloring-images.md)

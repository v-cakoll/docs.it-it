---
title: Utilizzo della trasformazione di tipo World
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: 6a029e17096222d7ed80dea16f91b83a813039f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-world-transformation"></a>Utilizzo della trasformazione di tipo World
La trasformazione globale è una proprietà del <xref:System.Drawing.Graphics> classe. I numeri che specificano la trasformazione globale vengono archiviati un <xref:System.Drawing.Drawing2D.Matrix> oggetto che rappresenta una matrice 3x3. Il <xref:System.Drawing.Drawing2D.Matrix> e <xref:System.Drawing.Graphics> classi dispongono di diversi metodi per l'impostazione dei numeri nella matrice di trasformazione globale.  
  
## <a name="different-types-of-transformations"></a>Diversi tipi di trasformazioni  
 Nell'esempio seguente, il codice prima creazione di un rettangolo di 50 × 50 e collocato in corrispondenza dell'origine (0, 0). L'origine si trova nell'angolo superiore sinistro dell'area client.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 Il codice seguente si applica una trasformazione di ridimensionamento che si espande il rettangolo di un fattore di 1,75 nella direzione x e riduce il rettangolo di un fattore pari a 0,5 nella direzione y:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 Il risultato è un rettangolo che è più lungo l'asse x e più breve nella direzione y rispetto all'originale.  
  
 Per ruotare il rettangolo anziché scalabilità, utilizzare il codice seguente:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 Per convertire il rettangolo, utilizzare il codice seguente:  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [Sistemi di coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Uso di trasformazioni nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)

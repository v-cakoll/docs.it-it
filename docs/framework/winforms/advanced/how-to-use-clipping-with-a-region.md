---
title: "Procedura: definire l'area di visualizzazione utilizzando una regione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regions [Windows Forms], clipping
- regions [Windows Forms], restricting drawing surface
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
ms.openlocfilehash: bfc40d985ec12a30b73935ace7ef034aadbd5385
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522096"
---
# <a name="how-to-use-clipping-with-a-region"></a>Procedura: definire l'area di visualizzazione utilizzando una regione
Una delle proprietà del <xref:System.Drawing.Graphics> classe è l'area di ritaglio. Tutti i disegni effettuati un determinato <xref:System.Drawing.Graphics> è limitato per l'area di ritaglio di tale oggetto <xref:System.Drawing.Graphics> oggetto. È possibile impostare l'area di ritaglio chiamando il <xref:System.Drawing.Graphics.SetClip%2A> metodo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente crea un percorso costituito da un singolo poligono. Nel codice viene quindi creata un'area, in base a tale percorso. L'area viene passata per il <xref:System.Drawing.Graphics.SetClip%2A> metodo di un <xref:System.Drawing.Graphics> oggetto e quindi due stringhe vengono disegnati.  
  
 Nella figura seguente mostra le stringhe tagliate.  
  
 ![Clip](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Regioni in GDI+](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)  
 [Uso delle regioni](../../../../docs/framework/winforms/advanced/using-regions.md)

---
title: Utilizzo di contenitori di grafica annidati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], nested containers
- graphics [Windows Forms], clipping
- graphics [Windows Forms], transformations in nested objects
ms.assetid: a0d9f178-43a4-4323-bb5a-d3e3f77ae6c1
ms.openlocfilehash: ba6bba84100a0ddcc87894710a6d3099ab0ccff5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529061"
---
# <a name="using-nested-graphics-containers"></a>Utilizzo di contenitori di grafica annidati
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce contenitori che è possibile utilizzare per sostituire temporaneamente o per migliorare parte dello stato in un <xref:System.Drawing.Graphics> oggetto. Per creare un contenitore, chiamare il <xref:System.Drawing.Graphics.BeginContainer%2A> metodo di un <xref:System.Drawing.Graphics> oggetto. È possibile chiamare <xref:System.Drawing.Graphics.BeginContainer%2A> ripetutamente per creare contenitori annidati. Ogni chiamata a <xref:System.Drawing.Graphics.BeginContainer%2A> deve essere abbinato a una chiamata a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## <a name="transformations-in-nested-containers"></a>Trasformazioni in contenitori annidati  
 Nell'esempio seguente viene creato un <xref:System.Drawing.Graphics> oggetto e un contenitore all'interno che <xref:System.Drawing.Graphics> oggetto. La trasformazione globale del <xref:System.Drawing.Graphics> oggetto è un'unità di conversione 100 nella direzione x e di 80 nella direzione y. La trasformazione globale del contenitore è una rotazione di 30 gradi. Il codice viene eseguita la chiamata `DrawRectangle(pen, -60, -30, 120, 60)` due volte. La prima chiamata a <xref:System.Drawing.Graphics.DrawRectangle%2A> si trova all'interno del contenitore; la chiamata è tra le chiamate a <xref:System.Drawing.Graphics.BeginContainer%2A> e <xref:System.Drawing.Graphics.EndContainer%2A>. La seconda chiamata a <xref:System.Drawing.Graphics.DrawRectangle%2A> dopo la chiamata a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 Nel codice precedente, il rettangolo disegnato dall'interno del contenitore viene applicato prima per la trasformazione globale di contenitore (rotazione) e quindi per la trasformazione globale del <xref:System.Drawing.Graphics> oggetto (conversione). Rettangolo disegnato dall'esterno del contenitore viene applicato tramite la trasformazione globale del <xref:System.Drawing.Graphics> oggetto (conversione). Nella figura seguente mostra i due rettangoli.  
  
 ![Contenitori annidati](../../../../docs/framework/winforms/advanced/media/csnestedcontainers1.png "csnestedcontainers1")  
  
## <a name="clipping-in-nested-containers"></a>Ritaglio di contenitori annidati  
 L'esempio seguente illustra i contenitori nidificati come gestire le aree di ritaglio. Il codice crea un <xref:System.Drawing.Graphics> oggetto e un contenitore all'interno che <xref:System.Drawing.Graphics> oggetto. L'area di visualizzazione di <xref:System.Drawing.Graphics> oggetto è un rettangolo e l'area di visualizzazione del contenitore è un'ellisse. Il codice di due chiamate al <xref:System.Drawing.Graphics.DrawLine%2A> metodo. La prima chiamata a <xref:System.Drawing.Graphics.DrawLine%2A> si trova all'interno del contenitore e la seconda chiamata a <xref:System.Drawing.Graphics.DrawLine%2A> è di fuori del contenitore (dopo la chiamata a <xref:System.Drawing.Graphics.EndContainer%2A>). La prima riga viene tagliata dall'intersezione delle due aree di ridimensionamento. La seconda riga viene tagliata solo dall'area di visualizzazione rettangolare del <xref:System.Drawing.Graphics> oggetto.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 Nella figura seguente mostra le due linee tagliate.  
  
 ![Contenitore annidato](../../../../docs/framework/winforms/advanced/media/nestedcontainers2.png "nestedcontainers2")  
  
 Come nei due esempi precedenti, trasformazioni e aree di visualizzazione sono cumulative nei contenitori annidati. Se si impostano le trasformazioni world del contenitore e <xref:System.Drawing.Graphics> dell'oggetto, entrambe le trasformazioni verranno applicate agli elementi disegnati dall'interno del contenitore. La trasformazione del contenitore sarà applicata per prima e la trasformazione del <xref:System.Drawing.Graphics> verrà applicato secondo oggetto. Se si impostano le aree di visualizzazione del contenitore e <xref:System.Drawing.Graphics> dell'oggetto, gli elementi disegnati dall'interno del contenitore saranno tagliati dall'intersezione delle due aree di ridimensionamento.  
  
## <a name="quality-settings-in-nested-containers"></a>Impostazioni di qualità in contenitori annidati  
 Le impostazioni di qualità (<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A>e così via) in contenitori nidificati non sono cumulativi, invece, le impostazioni di qualità del contenitore sostituiscono temporaneamente le impostazioni di qualità di un <xref:System.Drawing.Graphics> oggetto. Quando si crea un nuovo contenitore, le impostazioni di qualità per tale contenitore sono impostate sui valori predefiniti. Si supponga, ad esempio, un <xref:System.Drawing.Graphics> oggetto con una modalità di smussatura <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Quando si crea un contenitore, la modalità di arrotondamento all'interno del contenitore è quella predefinita. Si possono impostare la modalità di arrotondamento del contenitore e qualsiasi elemento disegnato dall'interno del contenitore verrà disegnato secondo la modalità che è impostata. Gli elementi disegnati dopo la chiamata a <xref:System.Drawing.Graphics.EndContainer%2A> verrà disegnato in base alla modalità di arrotondamento (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>) che nel sistema prima della chiamata a <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## <a name="several-layers-of-nested-containers"></a>Diversi livelli di contenitori annidati  
 Non si è limitati a un contenitore in un <xref:System.Drawing.Graphics> oggetto. È possibile creare una sequenza di contenitori, ognuna nidificata nel passaggio precedente ed è possibile specificare la trasformazione globale, l'area di visualizzazione e le impostazioni di qualità di ciascuno di tali contenitori annidati. Se si chiama un metodo di creazione all'interno del contenitore più interno, le trasformazioni verranno applicate nell'ordine, iniziando con il contenitore più interno e terminando con il contenitore più esterno. Elementi disegnati dall'interno del contenitore più interno verranno ritagliati dal punto di intersezione tra tutte le aree di ridimensionamento.  
  
 Nell'esempio seguente viene creato un <xref:System.Drawing.Graphics> dell'oggetto e imposta l'hint di rendering relativo testo <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Il codice crea due contenitori, uno annidato all'interno di altra. Il testo del contenitore esterno è impostato su <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>, e l'hint per il rendering di testo del contenitore interno è impostato su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Vengono create tre stringhe: uno dal contenitore interno, uno dal contenitore esterno e uno dal <xref:System.Drawing.Graphics> oggetto stesso.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 Nella figura seguente mostra le tre stringhe. Le stringhe tracciate dal contenitore interno il <xref:System.Drawing.Graphics> oggetto vengono smussate tramite anti-aliasing. La stringa creata dal contenitore esterno non è smussata tramite anti-aliasing perché il <xref:System.Drawing.Graphics.TextRenderingHint%2A> è impostata su <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>.  
  
 ![Contenitori annidati](../../../../docs/framework/winforms/advanced/media/nestedcontainers3.png "nestedcontainers3")  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Graphics>  
 [Gestione dello stato di un oggetto Graphics](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)

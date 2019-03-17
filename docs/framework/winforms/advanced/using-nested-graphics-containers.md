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
ms.openlocfilehash: a66edd0297b723b81c31675c9b0e6b6def9ed10a
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2019
ms.locfileid: "58125863"
---
# <a name="using-nested-graphics-containers"></a>Utilizzo di contenitori di grafica annidati
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Fornisce i contenitori che è possibile utilizzare per sostituire temporaneamente o per migliorare parte dello stato in un <xref:System.Drawing.Graphics> oggetto. Creare un contenitore, chiamare il <xref:System.Drawing.Graphics.BeginContainer%2A> metodo di un <xref:System.Drawing.Graphics> oggetto. È possibile chiamare <xref:System.Drawing.Graphics.BeginContainer%2A> ripetutamente per creare contenitori nidificati. Ogni chiamata a <xref:System.Drawing.Graphics.BeginContainer%2A> deve essere associato a una chiamata a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## <a name="transformations-in-nested-containers"></a>Trasformazioni nei contenitori annidati  
 L'esempio seguente crea una <xref:System.Drawing.Graphics> oggetto e un contenitore all'interno che <xref:System.Drawing.Graphics> oggetto. La trasformazione globale del <xref:System.Drawing.Graphics> oggetto è un'unità di conversione 100 nella direzione x e 80 unità nella direzione y. La trasformazione globale del contenitore è una rotazione di 30 gradi. Il codice effettua la chiamata `DrawRectangle(pen, -60, -30, 120, 60)` due volte. La prima chiamata a <xref:System.Drawing.Graphics.DrawRectangle%2A> si trova all'interno del contenitore; la chiamata è tra le chiamate a <xref:System.Drawing.Graphics.BeginContainer%2A> e <xref:System.Drawing.Graphics.EndContainer%2A>. La seconda chiamata a <xref:System.Drawing.Graphics.DrawRectangle%2A> dopo la chiamata a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 Nel codice precedente, il rettangolo disegnato all'interno del contenitore viene applicata innanzitutto per la trasformazione globale del contenitore (rotazione) e quindi per la trasformazione globale del <xref:System.Drawing.Graphics> oggetto (conversione). Viene trasformato il rettangolo disegnato dall'esterno del contenitore solo per la trasformazione globale del <xref:System.Drawing.Graphics> oggetto (conversione). La figura seguente mostra i due rettangoli: 
  
 ![Figura che mostra i contenitori nidificati.](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>Area di visualizzazione in contenitori annidati  
 L'esempio seguente illustra i contenitori nidificati come gestire aree di visualizzazione. Il codice crea un <xref:System.Drawing.Graphics> oggetto e un contenitore all'interno che <xref:System.Drawing.Graphics> oggetto. L'area di visualizzazione del <xref:System.Drawing.Graphics> oggetto è un rettangolo e l'area di visualizzazione del contenitore è un'ellisse. Il codice effettua due chiamate al <xref:System.Drawing.Graphics.DrawLine%2A> (metodo). La prima chiamata a <xref:System.Drawing.Graphics.DrawLine%2A> si trova all'interno del contenitore e la seconda chiamata a <xref:System.Drawing.Graphics.DrawLine%2A> è all'esterno del contenitore (dopo la chiamata a <xref:System.Drawing.Graphics.EndContainer%2A>). La prima riga viene tagliata dall'intersezione delle due aree di ridimensionamento. La seconda riga viene troncata solo per l'area rettangolare di ritaglio del <xref:System.Drawing.Graphics> oggetto.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 La figura seguente mostra le due righe abbreviate:
  
 ![Figura che mostra un contenitore annidato con righe tagliati.](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 Come nei due esempi precedenti, le trasformazioni e aree di visualizzazione sono cumulative in contenitori nidificati. Se si impostano le trasformazioni mondo del contenitore e <xref:System.Drawing.Graphics> dell'oggetto, entrambe le trasformazioni verranno applicata agli elementi da disegnare all'interno del contenitore. La trasformazione del contenitore sarà applicata per prima e la trasformazione del <xref:System.Drawing.Graphics> verrà applicato secondo oggetto. Se si impostano le aree di visualizzazione del contenitore e <xref:System.Drawing.Graphics> dell'oggetto, gli elementi da disegnare all'interno del contenitore verranno ritagliati dal punto di intersezione tra due aree di ridimensionamento.  
  
## <a name="quality-settings-in-nested-containers"></a>Impostazioni relative alla qualità nei contenitori annidati  
 Le impostazioni di qualità (<xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.TextRenderingHint%2A>e così via) in contenitori nidificati non sono cumulativi; piuttosto, le impostazioni di qualità del contenitore di sostituiscano temporaneamente le impostazioni di qualità di un <xref:System.Drawing.Graphics> oggetto. Quando si crea un nuovo contenitore, le impostazioni di qualità per tale contenitore sono impostate sui valori predefiniti. Ad esempio, si supponga di avere una <xref:System.Drawing.Graphics> oggetto con una modalità di smussatura <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Quando si crea un contenitore, la modalità di arrotondamento all'interno del contenitore è quella predefinita. Si è liberi di impostare la modalità di smussamento del contenitore e tutti gli elementi da disegnare all'interno del contenitore verranno disegnati secondo la modalità che è impostata. Elementi disegnati dopo la chiamata a <xref:System.Drawing.Graphics.EndContainer%2A> verranno disegnati in base alla modalità di arrotondamento (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>) che è stato posto prima della chiamata a <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## <a name="several-layers-of-nested-containers"></a>Diversi livelli di contenitori nidificati  
 Non si è limitati a un contenitore in un <xref:System.Drawing.Graphics> oggetto. È possibile creare una sequenza di contenitori, ognuno annidati nel precedente ed è possibile specificare la trasformazione globale, area di ritaglio e impostazioni relative alla qualità della ognuno di questi contenitori nidificati. Se si chiama un metodo di creazione all'interno del contenitore più interno, le trasformazioni verranno applicate in ordine, a partire con il contenitore più interno e terminando con il contenitore più esterno. Gli elementi da disegnare all'interno del contenitore più interno verranno ritagliati dall'intersezione di tutte le aree di ritaglio.  
  
 L'esempio seguente crea una <xref:System.Drawing.Graphics> dell'oggetto e imposta l'hint di rendering relativo testo <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Il codice crea due contenitori, uno annidato all'interno di altra. L'hint per il rendering di testo del contenitore esterno è impostato su <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>, e l'hint per il rendering di testo del contenitore interno è impostato su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>. Il codice crea tre stringhe: uno dal contenitore interno, uno dal contenitore esterno e uno dal <xref:System.Drawing.Graphics> oggetto stesso.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 La figura seguente illustra le tre stringhe. Le stringhe disegnate dal contenitore interno e verso il <xref:System.Drawing.Graphics> oggetto vengono livellati dall'anti-aliasing. La stringa creata dal contenitore esterno non è smussata da anti-aliasing perché il <xref:System.Drawing.Graphics.TextRenderingHint%2A> è impostata su <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>.  
  
 ![Figura che mostra le stringhe ricavate dal contenitori nidificati.](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Graphics>
- [Gestione dello stato di un oggetto Graphics](managing-the-state-of-a-graphics-object.md)

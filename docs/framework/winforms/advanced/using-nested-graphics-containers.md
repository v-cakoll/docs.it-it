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
ms.openlocfilehash: 460ebb37ee62691a1e282f756840121fd378ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182470"
---
# <a name="using-nested-graphics-containers"></a>Utilizzo di contenitori di grafica annidati
In GDIè sono disponibili contenitori che è possibile utilizzare <xref:System.Drawing.Graphics> per sostituire temporaneamente o aumentare parte dello stato in un oggetto. Per creare un contenitore, chiamare il <xref:System.Drawing.Graphics.BeginContainer%2A> metodo di un <xref:System.Drawing.Graphics> oggetto . È possibile <xref:System.Drawing.Graphics.BeginContainer%2A> chiamare ripetutamente per formare contenitori annidati. Ogni chiamata <xref:System.Drawing.Graphics.BeginContainer%2A> a deve essere associata a una chiamata a <xref:System.Drawing.Graphics.EndContainer%2A>.  
  
## <a name="transformations-in-nested-containers"></a>Trasformazioni nei contenitori annidati  
 Nell'esempio seguente <xref:System.Drawing.Graphics> vengono creati un <xref:System.Drawing.Graphics> oggetto e un contenitore all'interno di tale oggetto. La trasformazione <xref:System.Drawing.Graphics> globale dell'oggetto è una traslazione di 100 unità nella direzione x e 80 unità nella direzione y. La trasformazione globale del contenitore è una rotazione di 30 gradi. Il codice effettua `DrawRectangle(pen, -60, -30, 120, 60)` la chiamata due volte. La prima <xref:System.Drawing.Graphics.DrawRectangle%2A> chiamata a è all'interno del contenitore; ovvero, la chiamata si trova <xref:System.Drawing.Graphics.BeginContainer%2A> tra <xref:System.Drawing.Graphics.EndContainer%2A>le chiamate a e . La seconda <xref:System.Drawing.Graphics.DrawRectangle%2A> chiamata a è <xref:System.Drawing.Graphics.EndContainer%2A>dopo la chiamata a .  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.MiscLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#61)]  
  
 Nel codice precedente, il rettangolo disegnato dall'interno del contenitore viene trasformato prima dalla trasformazione globale <xref:System.Drawing.Graphics> del contenitore (rotazione) e quindi dalla trasformazione globale dell'oggetto (traslazione). Il rettangolo disegnato dall'esterno del contenitore viene <xref:System.Drawing.Graphics> trasformato solo dalla trasformazione globale dell'oggetto (traduzione). La figura seguente mostra i due rettangoli:
  
 ![Illustrazione che mostra i contenitori annidati.](./media/using-nested-graphics-containers/nested-containers-illustration.png)  
  
## <a name="clipping-in-nested-containers"></a>Ritaglio in contenitori nidificati  
 Nell'esempio seguente viene illustrato come i contenitori annidati gestiscono le aree di ritaglio. Il codice <xref:System.Drawing.Graphics> crea un oggetto <xref:System.Drawing.Graphics> e un contenitore all'interno di tale oggetto. L'area di <xref:System.Drawing.Graphics> ritaglio dell'oggetto è un rettangolo e l'area di ritaglio del contenitore è un'ellisse. Il codice effettua due <xref:System.Drawing.Graphics.DrawLine%2A> chiamate al metodo. La prima <xref:System.Drawing.Graphics.DrawLine%2A> chiamata a si trova all'interno del contenitore e la seconda chiamata a <xref:System.Drawing.Graphics.DrawLine%2A> è all'esterno del contenitore (dopo la chiamata a <xref:System.Drawing.Graphics.EndContainer%2A>). La prima riga viene ritagliata dall'intersezione delle due aree di ritaglio. La seconda riga viene ritagliata solo dall'area di ritaglio rettangolare dell'oggetto. <xref:System.Drawing.Graphics>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#62)]
 [!code-vb[System.Drawing.MiscLegacyTopics#62](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#62)]  
  
 La figura seguente mostra le due linee ritagliate:
  
 ![Illustrazione che mostra un contenitore nidificato con linee ritagliate.](./media/using-nested-graphics-containers/nested-container-clipped-lines.png)  
  
 Come illustrato nei due esempi precedenti, le trasformazioni e le aree di ritaglio sono cumulative nei contenitori annidati. Se si impostano le trasformazioni <xref:System.Drawing.Graphics> mondiali del contenitore e dell'oggetto, entrambe le trasformazioni verranno applicate agli elementi disegnati dall'interno del contenitore. La trasformazione del contenitore verrà applicata <xref:System.Drawing.Graphics> per prima e la trasformazione dell'oggetto verrà applicata per seconda. Se si impostano le aree <xref:System.Drawing.Graphics> di ritaglio del contenitore e dell'oggetto, gli elementi disegnati dall'interno del contenitore verranno ritagliati dall'intersezione delle due aree di ritaglio.  
  
## <a name="quality-settings-in-nested-containers"></a>Impostazioni di qualità nei contenitori annidatiQuality Settings in Nested Containers  
 Le impostazioni<xref:System.Drawing.Graphics.SmoothingMode%2A> <xref:System.Drawing.Graphics.TextRenderingHint%2A>di qualità ( , , e così come) nei contenitori nidificati non sono cumulative; piuttosto, le impostazioni di qualità del contenitore <xref:System.Drawing.Graphics> sostituiscono temporaneamente le impostazioni di qualità di un oggetto. Quando si crea un nuovo contenitore, le impostazioni di qualità per tale contenitore vengono impostate sui valori predefiniti. Si supponga, ad <xref:System.Drawing.Graphics> esempio, di disporre <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>di un oggetto con una modalità di arrotondamento di . Quando si crea un contenitore, la modalità di arrotondamento all'interno del contenitore è la modalità di arrotondamento predefinita. È possibile impostare la modalità di arrotondamento del contenitore e tutti gli elementi disegnati dall'interno del contenitore verranno disegnati in base alla modalità impostata. Gli elementi disegnati <xref:System.Drawing.Graphics.EndContainer%2A> dopo la chiamata a verranno disegnati in base alla modalità di arrotondamento (<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>) presente prima della chiamata a <xref:System.Drawing.Graphics.BeginContainer%2A>.  
  
## <a name="several-layers-of-nested-containers"></a>Diversi livelli di contenitori nidificati  
 Non si è limitati a <xref:System.Drawing.Graphics> un contenitore in un oggetto. È possibile creare una sequenza di contenitori, ognuno annidato nel precedente, ed è possibile specificare la trasformazione globale, l'area di ritaglio e le impostazioni di qualità di ognuno di questi contenitori annidati. Se si chiama un metodo di disegno dall'interno del contenitore più interno, le trasformazioni verranno applicate nell'ordine, a partire dal contenitore più interno e terminando con il contenitore più esterno. Gli elementi disegnati dall'interno del contenitore più interno verranno ritagliati dall'intersezione di tutte le aree di ritaglio.  
  
 Nell'esempio seguente <xref:System.Drawing.Graphics> viene creato un oggetto <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>e viene impostato il relativo hint per il rendering del testo su . Il codice crea due contenitori, uno annidato all'interno dell'altro. L'hint per il rendering del <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>testo del contenitore esterno è impostato <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>su e l'hint di rendering del testo del contenitore interno è impostato su . Il codice disegna tre stringhe: una dal contenitore interno, <xref:System.Drawing.Graphics> una dal contenitore esterno e una dall'oggetto stesso.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#63)]
 [!code-vb[System.Drawing.MiscLegacyTopics#63](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#63)]  
  
 Nella figura seguente vengono illustrate le tre stringhe. Le stringhe disegnate dal contenitore interno e dall'oggetto <xref:System.Drawing.Graphics> vengono levigate mediante l'antialiasing. La stringa disegnata dal contenitore esterno non viene <xref:System.Drawing.Graphics.TextRenderingHint%2A> smussata dall'antialiasing perché la proprietà è impostata su <xref:System.Drawing.Text.TextRenderingHint.SingleBitPerPixel>.  
  
 ![Illustrazione che mostra le stringhe disegnate da contenitori annidati.](./media/using-nested-graphics-containers/nested-containers-three-strings.png)  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Graphics>
- [Gestione dello stato di un oggetto Graphics](managing-the-state-of-a-graphics-object.md)

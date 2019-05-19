---
title: 'Procedura: Creare una sfumatura lineare'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
ms.openlocfilehash: e55d27b454579268658192ae56daa52e0b28bb83
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876064"
---
# <a name="how-to-create-a-linear-gradient"></a>Procedura: Creare una sfumatura lineare
GDI+ fornisce orizzontali, verticali e diagonali sfumature lineari. Per impostazione predefinita, il colore in una sfumatura lineare viene modificato in modo uniforme. Tuttavia, è possibile personalizzare una sfumatura lineare in modo che il colore viene modificato in modo non uniforme.  

> [!NOTE]
> Gli esempi in questo articolo sono i metodi chiamati da un controllo <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  

Nell'esempio seguente inserisce una riga, un'ellisse e un rettangolo con un pennello sfumatura lineare orizzontale.  
  
Il <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore riceve quattro argomenti: due punti e due colori. Il primo punto (0, 10) è associato il primo colore (rosso) e il secondo punto (200, 10) è associato il secondo colore (blu). Come si può immaginare, la riga disegnata dal punto (0, 10) a (200, 10) cambia gradualmente da rosso a blu.  
  
 Il numero 10 in quanto (0, 10) e (200, 10) non sono importanti. È importante che i due punti abbiano la stessa coordinata secondo, ovvero la linea di connessione è orizzontale. I puntini di sospensione e il rettangolo inoltre modificare gradualmente da rosso a blu come la coordinata orizzontale va da 0 a 200.  
  
 La figura seguente mostra la riga, i puntini di sospensione e il rettangolo. Si noti che la sfumatura di colore viene ripetuto man mano che aumenta la coordinata orizzontale a oltre 200.  
  
 ![Una riga, un'ellisse e un rettangolo riempito con una sfumatura di colore.](./media/how-to-create-a-linear-gradient/gradient-line-ellipse-rectangle.png)  
  
## <a name="to-use-horizontal-linear-gradients"></a>Per utilizzare sfumature lineari orizzontali  
  
- Passare blu rosso ed è opaco opaco come il terzo e quarto argomento, rispettivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 Nell'esempio precedente, i componenti di colore modificare in modo lineare come si spostano da una coordinata orizzontale pari a 0 a una coordinata orizzontale pari a 200. Ad esempio, un punto di cui prima coordinata è compreso tra 0 e 200 avrà un componente blu che è compreso tra 0 e 255.  
  
 GDI + consente di regolare la modalità di che un colore varia da un bordo di una sfumatura a altro. Si supponga di che voler creare un pennello a sfumatura che le modifiche apportate dal nero al rosso in base alla tabella riportata di seguito.  
  
|Coordinata orizzontale|Componenti RGB|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 Si noti che il componente rossa intensità media quando la coordinata orizzontale corrisponde solo il 20% del modo in cui da 0 a 200.  
  
 L'esempio seguente imposta il <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A?displayProperty=nameWithType> proprietà da associare tre intensità relative tre posizioni relative. Come indicato nella tabella precedente, è associata a una posizione relativa di 0.2 un'intensità di 0,5. Il codice viene compilato un rettangolo con il pennello a sfumatura e un'ellisse.  
  
 La figura seguente mostra l'ellisse risultante e il rettangolo.  
  
 ![Un'ellisse e un rettangolo riempito con una sfumatura di colore orizzontale.](./media/how-to-create-a-linear-gradient/gradient-ellipse-rectangle.png)  

## <a name="to-customize-linear-gradients"></a>Per personalizzare le sfumature lineari  
  
- Passare il rosso opaco e nero opaco come il terzo e quarto argomento, rispettivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 Le sfumature negli esempi precedenti sono state orizzontale; vale a dire il colore cambia gradualmente quando si sposta lungo una linea orizzontale. È anche possibile definire le sfumature verticali e diagonali.  
  
 L'esempio seguente passa i punti (0, 0) e (200, 100) per un <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore. È associato il colore blu (0, 0), ed è associato il colore verde (200, 100). Una riga (con la larghezza della penna 10) e un elemento ellipse vengono riempiti con il pennello sfumato lineare.  
  
 La figura seguente mostra la riga e l'ellisse. Si noti che il colore in ellisse cambia gradualmente quando si sposta lungo una riga che sono parallelo a quella che passa attraverso (0, 0) e (200, 100).  
  
 ![Una riga e un elemento ellipse riempito con una sfumatura di colore diagonale.](./media/how-to-create-a-linear-gradient/gradient-line-ellipse.png)  
  
## <a name="to-create-diagonal-linear-gradients"></a>Per creare diagonale sfumature lineari  
  
- Passare l'opaco blu e verde opaco come il terzo e quarto argomento, rispettivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un pennello a sfumatura per il riempimento di forme](using-a-gradient-brush-to-fill-shapes.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)

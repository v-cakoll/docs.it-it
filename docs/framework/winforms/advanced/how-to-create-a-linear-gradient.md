---
title: 'Procedura: creare una sfumatura lineare'
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
- linear gradients [Windows Forms], creating
- gradients [Windows Forms], creating linear
- colors [Windows Forms], creating linear gradients
- gradients
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bbf3b1657a5a6b91ba88a0968b6b92d4e4bdbf0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-linear-gradient"></a>Procedura: creare una sfumatura lineare
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]fornisce orizzontali, verticali e diagonali gradienti lineari. Per impostazione predefinita, il colore in una sfumatura lineare cambia in modo uniforme. Tuttavia, è possibile personalizzare una sfumatura lineare in modo che il colore cambia in modo non uniformi.  
  
 Nell'esempio seguente inserisce una riga di un'ellisse e un rettangolo con un pennello sfumato lineare orizzontale.  
  
 Il <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore riceve quattro argomenti: due punti e due colori. Il primo punto (0, 10) è associato al primo colore (rosso) e il secondo punto (200, 10) è associato il secondo colore (blu). Come prevedibile, la riga disegnata da (0, 10) a (200, 10) cambia gradualmente da rosso a blu.  
  
 Il numero 10 punti (50, 10) e (200, 10) non sono importanti. L'aspetto importante è che i due punti hanno stessa coordinata secondo, ovvero la riga che li connettono è orizzontale. I puntini di sospensione e il rettangolo inoltre modificare gradualmente da rosso a blu come coordinata orizzontale va da 0 a 200.  
  
 Nella figura seguente mostra la riga, i puntini di sospensione e il rettangolo. Si noti che la sfumatura di colore si ripete per la coordinata orizzontale aumenta oltre 200.  
  
 ![Sfumatura lineare](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")  
  
### <a name="to-use-horizontal-linear-gradients"></a>Per utilizzare sfumature lineare orizzontale  
  
-   Passare l'opaco rosso e blu opaco come terzo e quarto argomento, rispettivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 Nell'esempio precedente, i componenti di colore modificare in modo lineare si sposta da una coordinata orizzontale pari a 0 per una coordinata orizzontale 200. Ad esempio, un punto in cui la coordinata è compreso tra 0 e 200 disporrà di un componente blu che si trova a metà tra 0 e 255.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]Consente di modificare il modo in cui che un colore varia da un bordo di una sfumatura a altro. Si supponga di che voler creare un pennello sfumato cambia da nero in rosso in base alla tabella seguente.  
  
|Coordinata orizzontale|Componenti RGB|  
|---------------------------|--------------------|  
|0|(0, 0, 0)|  
|40|(128, 0, 0)|  
|200|(255, 0, 0)|  
  
 Si noti che il componente rosso intensità media quando la coordinata orizzontale corrisponde solo il 20% del modo in cui da 0 a 200.  
  
 L'esempio seguente imposta il <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> proprietà di un <xref:System.Drawing.Drawing2D.LinearGradientBrush> oggetto da associare tre intensità relative a tre posizioni relative. Come indicato nella tabella precedente, un'intensità pari a 0,5 è associata a una posizione relativa di 0,2. Il codice verrà inserito un'ellisse e un rettangolo con pennello sfumato.  
  
 Nella figura seguente viene illustrato il rettangolo e l'ellisse risultante.  
  
 ![Sfumatura lineare](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")  
  
### <a name="to-customize-linear-gradients"></a>Per personalizzare i gradienti lineari  
  
-   Passare l'opaco nero e rosso opaco come terzo e quarto argomento, rispettivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 Le sfumature negli esempi precedenti sono state orizzontale; vale a dire il colore cambia gradualmente mentre si sposta lungo una linea orizzontale. È inoltre possibile definire sfumature verticali e diagonali.  
  
 Nell'esempio seguente passa i punti (0, 0) e (200, 100) a un <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> costruttore. Il colore blu è associato a (0, 0), ed è associato il colore verde (200, 100). Una riga (con la larghezza della penna 10) e un'ellisse vengono riempiti con pennello sfumato lineare.  
  
 Nella figura seguente mostra la riga e l'ellisse. Si noti che il colore in ellisse cambia gradualmente mentre si sposta lungo una riga che sono parallelo a quella che passa attraverso (0, 0) e (200, 100).  
  
 ![Sfumatura lineare](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")  
  
### <a name="to-create-diagonal-linear-gradients"></a>Per creare diagonale gradienti lineari  
  
-   Passare l'opaco blu e verde opaco come terzo e quarto argomento, rispettivamente.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di un pennello a sfumatura per il riempimento di forme](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)

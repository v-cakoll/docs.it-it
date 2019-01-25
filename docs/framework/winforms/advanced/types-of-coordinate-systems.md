---
title: Tipi di sistemi di coordinate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], page
- unit of measure
- world coordinate system
- page coordinate system
- page transformation
- device coordinate system
- world transformation
- coordinate systems
- transformations [Windows Forms], world
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
ms.openlocfilehash: 783e258f64633a4ddf7f3bbad858d6633256b97e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590378"
---
# <a name="types-of-coordinate-systems"></a>Tipi di sistemi di coordinate
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Usa tre spazi di coordinate: world, pagina e dispositivo. Coordinate internazionali sono le coordinate usate per modellare un mondo grafico specifico e le coordinate passate ai metodi in .NET Framework. Le coordinate di pagina può fare riferimento al sistema di coordinate utilizzato da una superficie di disegno, ad esempio un form o controllo. Le coordinate di periferica vengono usate dal dispositivo fisico da disegnare, ad esempio una schermata o un foglio di carta. Quando si effettua la chiamata `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, i punti che si passano al <xref:System.Drawing.Graphics.DrawLine%2A> metodo, ovvero`(0, 0)` e `(160, 80)`, ovvero sono nello spazio delle coordinate world. Prima di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] possibile tracciare le linee sullo schermo, le coordinate passano attraverso una sequenza di trasformazioni. Una trasformazione, ossia la trasformazione globale, converte le coordinate complessive in coordinate di pagina e un'altra trasformazione, ossia la trasformazione della pagina, converte le coordinate di pagina in coordinate del dispositivo.  
  
## <a name="transforms-and-coordinate-systems"></a>Sistemi di Coordinate e trasformazioni  
 Si supponga che si desidera utilizzare un sistema di coordinate che ha origine nel corpo dell'area client anziché l'angolo superiore sinistro. Si supponga, ad esempio, che si desidera che l'origine sia uguale a 100 pixel dal bordo sinistro dell'area client e 50 pixel dalla parte superiore dell'area client. La figura seguente mostra un sistema di coordinate.  
  
 ![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 Quando si effettua una chiamata `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, otterrai la riga mostrata nella figura seguente.  
  
 ![Sistema di coordinate](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Le coordinate dei punti finali della linea in tre spazi di coordinate sono i seguenti:  
  
|||  
|-|-|  
|World|(0, 0) a (160, 80)|  
|Pagina|(100, 50) a (260, 130)|  
|Dispositivo|(100, 50) a (260, 130)|  
  
 Si noti che lo spazio delle coordinate pagina ha la sua origine nell'angolo superiore sinistro dell'area client. Questo sarà sempre il caso. Si noti anche che dato l'unità di misura è il pixel, di coordinate del dispositivo sono le stesse le coordinate di pagina. Se si imposta l'unità di misura su un valore diverso da pixel (ad esempio, pollici), le coordinate del dispositivo sarà diverse dalle coordinate di pagina.  
  
 La trasformazione globale, che esegue il mapping di coordinate complessive in coordinate di pagina, viene mantenuta nella <xref:System.Drawing.Graphics.Transform%2A> proprietà del <xref:System.Drawing.Graphics> classe. Nell'esempio precedente, la trasformazione globale è un'unità di 100 traslazione sull'asse x e 50 unità nella direzione y. L'esempio seguente imposta la trasformazione globale di una <xref:System.Drawing.Graphics> dell'oggetto e quindi utilizza tale <xref:System.Drawing.Graphics> oggetto su cui disegnare la riga mostrata nella figura precedente:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 La trasformazione della pagina viene eseguito il mapping delle coordinate di pagina a coordinate del dispositivo. Il <xref:System.Drawing.Graphics> classe fornisce il <xref:System.Drawing.Graphics.PageUnit%2A> e <xref:System.Drawing.Graphics.PageScale%2A> proprietà per la modifica della trasformazione di pagina. Il <xref:System.Drawing.Graphics> classe fornisce anche due proprietà di sola lettura, <xref:System.Drawing.Graphics.DpiX%2A> e <xref:System.Drawing.Graphics.DpiY%2A>, per esaminare i punti per pollice della periferica di visualizzazione in orizzontali e verticali.  
  
 È possibile usare la <xref:System.Drawing.Graphics.PageUnit%2A> proprietà del <xref:System.Drawing.Graphics> classe per specificare un'unità di misura diversa da pixel.  
  
> [!NOTE]
>  Non è possibile impostare il <xref:System.Drawing.Graphics.PageUnit%2A> proprietà <xref:System.Drawing.GraphicsUnit.World>, perché non è un'unità fisica e genererà un'eccezione.  
  
 L'esempio seguente disegna una linea tra (0, 0) a (2, 1), in cui il punto (2, 1) è di 2 pollici a destra e 1 pollice verso il basso dal punto (0, 0):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  Se non si specifica una larghezza di penna quando si costruisce la penna, nell'esempio precedente verrà disegnare una linea che un pollice. È possibile specificare la larghezza della penna nel secondo argomento per il <xref:System.Drawing.Pen> costruttore:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Se si presume che il dispositivo di visualizzazione è di 96 punti per pollice nella direzione orizzontale e 96 punti per pollice nella direzione verticale, l'endpoint della linea dell'esempio precedente hanno le coordinate seguente in tre spazi di coordinate:  
  
|||  
|-|-|  
|World|(0, 0) a (2, 1)|  
|Pagina|(0, 0) a (2, 1)|  
|Dispositivo|(0, 0, a (192, 96)|  
  
 Si noti che poiché l'origine di spazio delle coordinate world è nell'angolo superiore sinistro dell'area client, le coordinate di pagina sono le stesse coordinate globali.  
  
 È possibile combinare le trasformazioni globali e di pagina per ottenere un'ampia gamma di effetti. Si supponga, ad esempio, che si desidera utilizzare pollici come unità di misura e si vuole che l'origine del sistema di coordinate sarà di 2 pollici dal bordo sinistro dell'area client e 1/2 pollice dalla parte superiore dell'area client. L'esempio seguente imposta le trasformazioni globali e di pagina di un <xref:System.Drawing.Graphics> dell'oggetto e quindi disegna una linea tra (0, 0) a (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 La figura seguente mostra la riga e il sistema di coordinate.  
  
 ![Coordinate System](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Se si presume che il dispositivo di visualizzazione è di 96 punti per pollice nella direzione orizzontale e 96 punti per pollice nella direzione verticale, l'endpoint della linea dell'esempio precedente hanno le coordinate seguente in tre spazi di coordinate:  
  
|||  
|-|-|  
|World|(0, 0) a (2, 1)|  
|Pagina|(2, 0,5) a (4, 1,5)|  
|Dispositivo|(192, 48) a (384, 144)|  
  
## <a name="see-also"></a>Vedere anche
- [Sistemi di coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
- [Rappresentazione tramite matrici delle trasformazioni](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)

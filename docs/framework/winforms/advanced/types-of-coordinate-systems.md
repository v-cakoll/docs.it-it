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
ms.openlocfilehash: bbb0d4908d4a281499336d262c653d7b72f3ccdc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159806"
---
# <a name="types-of-coordinate-systems"></a>Tipi di sistemi di coordinate
GDI+ utilizza tre spazi delle coordinate: mondo, pagina e dispositivo. Le coordinate globali sono le coordinate usate per modellare un particolare ambiente grafico e sono le coordinate passate ai metodi nel .NET Framework. Le coordinate della pagina fanno riferimento al sistema di coordinate utilizzato da una superficie di disegno, ad esempio un form o un controllo. Le coordinate del dispositivo sono le coordinate usate dal dispositivo fisico disegnato, ad esempio uno schermo o un foglio di carta. Quando si effettua la chiamata `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, i punti passati al metodo <xref:System.Drawing.Graphics.DrawLine%2A>,`(0, 0)` e `(160, 80)`, si trovano nello spazio delle coordinate internazionali. Prima che GDI+ possa creare la riga sullo schermo, le coordinate passano attraverso una sequenza di trasformazioni. Una trasformazione, denominata trasformazione globale, converte le coordinate internazionali in coordinate di pagina e un'altra trasformazione, denominata trasformazione pagina, converte le coordinate della pagina in coordinate del dispositivo.  
  
## <a name="transforms-and-coordinate-systems"></a>Trasformazioni e sistemi di coordinate  
 Si supponga di voler usare un sistema di coordinate con la relativa origine nel corpo dell'area client anziché nell'angolo superiore sinistro. Supponiamo, ad esempio, che si desideri che l'origine sia 100 pixel dal bordo sinistro dell'area client e 50 pixel dalla parte superiore dell'area client. Nella figura seguente viene illustrato un sistema di coordinate di questo tipo.  
  
 ![Sistema di coordinate](./media/aboutgdip05-art01.gif "AboutGdip05_art01")  
  
 Quando si effettua la chiamata `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`, si ottiene la riga illustrata nella figura seguente.  
  
 ![Sistema di coordinate](./media/aboutgdip05-art02.gif "AboutGdip05_art02")  
  
 Le coordinate degli endpoint della linea nei tre spazi delle coordinate sono le seguenti:  
  
|||  
|-|-|  
|Mondo|(0, 0) a (160, 80)|  
|Pagina|(100, 50) a (260, 130)|  
|Dispositivo|(100, 50) a (260, 130)|  
  
 Si noti che lo spazio delle coordinate della pagina ha origine nell'angolo superiore sinistro dell'area client. Questo sarà sempre il caso. Si noti inoltre che, poiché l'unità di misura è il pixel, le coordinate del dispositivo corrispondono alle coordinate della pagina. Se si imposta l'unità di misura su un valore diverso da pixel (ad esempio, pollici), le coordinate del dispositivo saranno diverse dalle coordinate della pagina.  
  
 La trasformazione globale, che esegue il mapping delle coordinate internazionali alle coordinate di pagina, viene mantenuta nella proprietà <xref:System.Drawing.Graphics.Transform%2A> della classe <xref:System.Drawing.Graphics>. Nell'esempio precedente la trasformazione globale è una conversione di unità 100 nella direzione x e 50 unità nella direzione y. Nell'esempio seguente viene impostata la trasformazione globale di un oggetto <xref:System.Drawing.Graphics> e quindi viene utilizzato tale oggetto <xref:System.Drawing.Graphics> per creare la riga illustrata nella figura precedente:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 La trasformazione pagina mappa le coordinate della pagina alle coordinate del dispositivo. La classe <xref:System.Drawing.Graphics> fornisce le proprietà <xref:System.Drawing.Graphics.PageUnit%2A> e <xref:System.Drawing.Graphics.PageScale%2A> per modificare la trasformazione della pagina. La classe <xref:System.Drawing.Graphics> fornisce anche due proprietà di sola lettura, <xref:System.Drawing.Graphics.DpiX%2A> e <xref:System.Drawing.Graphics.DpiY%2A>, per esaminare i punti orizzontali e verticali per pollice del dispositivo di visualizzazione.  
  
 È possibile utilizzare la proprietà <xref:System.Drawing.Graphics.PageUnit%2A> della classe <xref:System.Drawing.Graphics> per specificare un'unità di misura diversa dal pixel.  
  
> [!NOTE]
> Non è possibile impostare la proprietà <xref:System.Drawing.Graphics.PageUnit%2A> su <xref:System.Drawing.GraphicsUnit.World>, poiché non si tratta di un'unità fisica e verrà generata un'eccezione.  
  
 Nell'esempio seguente viene disegnata una riga da (0,0) a (2, 1), in cui il punto (2, 1) è di 2 centimetri a destra e 1 pollice verso il basso dal punto (0,0):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
> Se non si specifica una larghezza della penna quando si costruisce la penna, nell'esempio precedente verrà disegnato un valore di una linea di un pollice. È possibile specificare la larghezza della penna nel secondo argomento per il costruttore <xref:System.Drawing.Pen>:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 Se si presuppone che il dispositivo di visualizzazione includa 96 punti per pollice nella direzione orizzontale e 96 punti per pollice nella direzione verticale, gli endpoint della riga nell'esempio precedente hanno le coordinate seguenti nei tre spazi delle coordinate:  
  
|||  
|-|-|  
|Mondo|(0, 0) in (2, 1)|  
|Pagina|(0, 0) in (2, 1)|  
|Dispositivo|(0, 0) a (192, 96)|  
  
 Si noti che poiché l'origine dello spazio delle coordinate globali si trova nell'angolo superiore sinistro dell'area client, le coordinate della pagina sono le stesse delle coordinate internazionali.  
  
 È possibile combinare le trasformazioni del mondo e della pagina per ottenere una varietà di effetti. Si supponga, ad esempio, di voler usare i pollici come unità di misura e che l'origine del sistema di coordinate sia 2 centimetri dal bordo sinistro dell'area client e 1/2 di pollice dalla parte superiore dell'area client. Nell'esempio seguente vengono impostate le trasformazioni globali e di pagina di un oggetto <xref:System.Drawing.Graphics>, quindi viene disegnata una riga da (0,0) a (2, 1):  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 Nella figura seguente viene illustrato il sistema di coordinate e linee.  
  
 ![Sistema di coordinate](./media/aboutgdip05-art03.gif "AboutGdip05_art03")  
  
 Se si presuppone che il dispositivo di visualizzazione includa 96 punti per pollice nella direzione orizzontale e 96 punti per pollice nella direzione verticale, gli endpoint della riga nell'esempio precedente hanno le coordinate seguenti nei tre spazi delle coordinate:  
  
|||  
|-|-|  
|Mondo|(0, 0) in (2, 1)|  
|Pagina|(da 2 a 0,5) a (4, 1,5)|  
|Dispositivo|(192, 48) a (384, 144)|  
  
## <a name="see-also"></a>Vedere anche

- [Sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md)
- [Rappresentazione tramite matrici delle trasformazioni](matrix-representation-of-transformations.md)

---
title: Rappresentazione tramite matrici delle trasformazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- composite transformations
- transformations [Windows Forms], linear
- matrices
- translations in matrix representation
- transformations [Windows Forms], composite
- vectors
- linear transformations
- transformations [Windows Forms], matrix representation of
- transformations [Windows Forms], translation
- affine transformations
ms.assetid: 0659fe00-9e0c-41c4-9118-016f2404c905
ms.openlocfilehash: 24da407de24a924a68466e4301cc3f4a74cb2e94
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044243"
---
# <a name="matrix-representation-of-transformations"></a>Rappresentazione tramite matrici delle trasformazioni
Una matrice m × n è un set di numeri disposti in m righe e n colonne. Nella figura seguente sono illustrate diverse matrici.  
  
 ![] Trasformazioni (./media/aboutgdip05-art04.gif "AboutGdip05_art04")  
  
 È possibile aggiungere due matrici con le stesse dimensioni aggiungendo singoli elementi. Nella figura seguente sono illustrati due esempi di aggiunta di matrici.  
  
 ![Transformations](./media/aboutgdip05-art05.gif "AboutGdip05_art05")  
  
 Una matrice m × n può essere moltiplicata per una matrice n × p e il risultato è una matrice m × p. Il numero di colonne nella prima matrice deve corrispondere al numero di righe della seconda matrice. Ad esempio, una matrice di 4 × 2 può essere moltiplicata per una matrice 2 × 3 per produrre una matrice 4 × 3.  
  
 I punti del piano e delle righe e delle colonne di una matrice possono essere considerati vettori. Ad esempio, (2, 5) è un vettore con due componenti e (3, 7, 1) è un vettore con tre componenti. Il prodotto punto di due vettori viene definito come segue:  
  
 (a, b) • (c, d) = AC + BD  
  
 (a, b, c) • (d, e, f) = ad + be + CF  
  
 Ad esempio, il prodotto punto di (2, 3) e (5, 4) è (2) (5) + (3) (4) = 22. Il prodotto punto di (2, 5, 1) e (4, 3, 1) è (2) (4) + (5) (3) + (1) (1) = 24. Si noti che il prodotto punto di due vettori è un numero, non un altro vettore. Si noti anche che è possibile calcolare il prodotto punto solo se i due vettori hanno lo stesso numero di componenti.  
  
 Lasciare a (i, j) la voce della matrice a nella riga Ith e la colonna JTH. Ad esempio a (3, 2) è la voce nella matrice a nella terza riga e nella seconda colonna. Si supponga che A, B e C siano matrici e AB = C. Le voci di C vengono calcolate come segue:  
  
 C (i, j) = (riga i di A) • (colonna j di B)  
  
 Nella figura seguente vengono illustrati alcuni esempi di moltiplicazione di matrici.  
  
 ![] Trasformazioni (./media/aboutgdip05-art06.gif "AboutGdip05_art06")  
  
 Se si pensa a un punto in un piano come una matrice da 1 × 2, è possibile trasformare tale punto moltiplicando per una matrice 2 × 2. Nella figura seguente sono illustrate diverse trasformazioni applicate al punto (2, 1).  
  
 ![] Trasformazioni (./media/aboutgdip05-art07.gif "AboutGdip05_art07")  
  
 Tutte le trasformazioni mostrate nella figura precedente sono trasformazioni lineari. Alcune altre trasformazioni, ad esempio la traduzione, non sono lineari e non possono essere espresse come moltiplicazione da una matrice 2 × 2. Si supponga di voler iniziare con il punto (2, 1), ruotarlo 90 gradi, tradurlo 3 unità nella direzione x e tradurlo 4 unità nella direzione y. A tale scopo, è possibile usare una moltiplicazione di matrici seguita da un'aggiunta di matrici.  
  
 ![] Trasformazioni (./media/aboutgdip05-art08.gif "AboutGdip05_art08")  
  
 Una trasformazione lineare (moltiplicazione per una matrice 2 × 2) seguita da una traduzione (aggiunta di una matrice 1 × 2) viene definita trasformazione affine. Un'alternativa all'archiviazione di una trasformazione affine in una coppia di matrici (una per la parte lineare e una per la traduzione) consiste nell'archiviare l'intera trasformazione in una matrice di 3 × 3. Per eseguire questa operazione, un punto nel piano deve essere archiviato in una matrice da 1 × 3 con una terza coordinata fittizia. La tecnica usuale consiste nel rendere tutte le 3 Coordinate uguali a 1. Il punto (2, 1), ad esempio, è rappresentato dalla matrice [2 1 1]. Nella figura seguente viene illustrata una trasformazione affine (ruota 90 gradi; trasla 3 unità nella direzione x, 4 unità nella direzione y) espresse come moltiplicazione da una singola matrice 3 × 3.  
  
 ![] Trasformazioni (./media/aboutgdip05-art09.gif "AboutGdip05_art09")  
  
 Nell'esempio precedente, il punto (2, 1) viene mappato al punto (2, 6). Si noti che la terza colonna della matrice 3 × 3 contiene i numeri 0, 0, 1. Questo sarà sempre il caso della matrice 3 × 3 di una trasformazione affine. I numeri importanti sono i sei numeri nelle colonne 1 e 2. La parte superiore sinistra 2 × 2 della matrice rappresenta la parte lineare della trasformazione e le prime due voci della terza riga rappresentano la traduzione.  
  
 ![] Trasformazioni (./media/aboutgdip05-art10.gif "AboutGdip05_art10")  
  
 In GDI+ è possibile archiviare una trasformazione affine in un <xref:System.Drawing.Drawing2D.Matrix> oggetto. Poiché la terza colonna di una matrice che rappresenta una trasformazione affine è sempre (0, 0, 1), è necessario specificare solo i sei numeri nelle prime due colonne quando si costruisce un <xref:System.Drawing.Drawing2D.Matrix> oggetto. L'istruzione `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` costruisce la matrice illustrata nella figura precedente.  
  
## <a name="composite-transformations"></a>Trasformazioni composite  
 Una trasformazione composita è una sequenza di trasformazioni, una seguita dall'altra. Prendere in considerazione le matrici e le trasformazioni nell'elenco seguente:  
  
|||  
|-|-|  
|Matrice A|Ruota di 90 gradi|  
|Matrice B|Ridimensionare in base a un fattore 2 nella direzione x|  
|Matrice C|Tradurre 3 unità nella direzione y|  
  
 Se si inizia con il punto (2, 1), rappresentato dalla matrice [2 1 1], e si moltiplica per A, quindi B, C, il punto (2, 1) subirà le tre trasformazioni nell'ordine indicato.  
  
 [2 1 1]ABC = [-2 5 1]  
  
 Anziché archiviare le tre parti della trasformazione composita in tre matrici separate, è possibile moltiplicare a, B e C per ottenere una singola matrice da 3 × 3 che archivia l'intera trasformazione composita. Si supponga ABC = D. Un punto moltiplicato per D restituisce lo stesso risultato di un punto moltiplicato per A, quindi B, quindi C.  
  
 [2 1 1]D = [-2 5 1]  
  
 Nella figura seguente sono illustrate le matrici A, B, C e D.  
  
 ![] Trasformazioni (./media/aboutgdip05-art12.gif "AboutGdip05_art12")  
  
 Il fatto che la matrice di una trasformazione composita possa essere formata moltiplicando le singole matrici di trasformazione significa che qualsiasi sequenza di trasformazioni affini può essere archiviata in <xref:System.Drawing.Drawing2D.Matrix> un singolo oggetto.  
  
> [!CAUTION]
> L'ordine di una trasformazione composita è importante. In generale, ruotare, quindi ridimensionare, quindi tradurre non corrisponde a scala, quindi ruotare e quindi traslare. Analogamente, l'ordine di moltiplicazione della matrice è importante. In generale, ABC non corrisponde a BAC.  
  
 La <xref:System.Drawing.Drawing2D.Matrix> classe fornisce diversi metodi per la compilazione di una trasformazione <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>composita <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>: <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A> <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>,, <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>, e. Nell'esempio seguente viene creata la matrice di una trasformazione composita che ruota per prima 30 gradi, quindi viene ridimensionata in base a un fattore 2 nella direzione y e quindi si traduce 5 unità nella direzione x:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 Nella figura seguente viene illustrata la matrice.  
  
 ![] Trasformazioni (./media/aboutgdip05-art13.gif "AboutGdip05_art13")  
  
## <a name="see-also"></a>Vedere anche

- [Sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md)
- [Uso di trasformazioni nel codice gestito GDI+](using-transformations-in-managed-gdi.md)

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
ms.openlocfilehash: ec1feda5547a96a0deac6f9d2e6ba1139e3fa73f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732089"
---
# <a name="matrix-representation-of-transformations"></a>Rappresentazione tramite matrici delle trasformazioni
Una matrice di n × m è un set di numeri disposti in righe di m e n colonne. La figura seguente mostra le matrici di diverse.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art04.gif "AboutGdip05_art04")  
  
 È possibile aggiungere due matrici di uguale dimensione mediante l'aggiunta di singoli elementi. La figura seguente mostra due esempi della somma di matrice.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art05.gif "AboutGdip05_art05")  
  
 Una matrice di n × m possa essere moltiplicata con una matrice di p × n, e il risultato è una matrice di p × m. Il numero di colonne nella prima matrice deve essere lo stesso come il numero di righe della seconda matrice. Ad esempio, una matrice 4 × 2 può essere moltiplicata con una matrice di 3 × 2 per generare una matrice 4 × 3.  
  
 I punti nel piano e le righe e colonne di una matrice possono essere considerati come vettori. Ad esempio, (2, 5) è un vettore con due componenti e (3, 7, 1) è un vettore con tre componenti. Il prodotto scalare di due vettori viene definito come segue:  
  
 (a, b) • (c, d) = ac + bd  
  
 (a, b, c) • (d, e, f) = ad essere + + cloud Foundry  
  
 Ad esempio, il prodotto scalare di (2, 3) e (5, 4) è (2)(5) + (3)(4) = 22. Il prodotto scalare di (2, 5, 1) e (4, 3, 1) è (2)(4) + (5)(3) + (1)(1) = 24. Si noti che il prodotto scalare di due vettori è un numero, non un altro vettore. Si noti inoltre che è possibile calcolare il prodotto scalare solo se i due vettori hanno lo stesso numero di componenti.  
  
 Let A(i, j) essere la voce nella matrice a nella riga e colonna jma. Ad esempio (3, 2) è la voce nella matrice a nella riga 3 e la colonna 2. Si supponga che A, B e C sono matrici e AB = C. Le voci di C vengono calcolate come indicato di seguito:  
  
 C (i, j) = (riga i dell'oggetto) • (colonna j di B)  
  
 La figura seguente mostra alcuni esempi di moltiplicazione di matrici.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art06.gif "AboutGdip05_art06")  
  
 Se si ritiene che un punto del piano come una matrice × 2 1, è possibile trasformare tale punto, moltiplicandolo per una matrice 2x2. La figura seguente mostra diverse trasformazioni applicate al punto di (2, 1).  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art07.gif "AboutGdip05_art07")  
  
 Tutte le trasformazioni illustrate nella figura precedente sono trasformazioni lineari. Altre trasformazioni, ad esempio la traduzione, non lineari e non possono essere espresse come moltiplicazione per una matrice 2x2. Si supponga che si desidera iniziare con il punto (2, 1), ruota di 90 gradi, convertirlo nella direzione x 3 unità e 4 unità nella direzione y. È possibile farlo tramite una moltiplicazione di matrici seguita da una somma di matrici.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art08.gif "AboutGdip05_art08")  
  
 Una trasformazione lineare (moltiplicazione per una matrice 2x2) seguita da una traduzione (aggiunta di una matrice × 2 1) viene chiamata una trasformazione affine. Un'alternativa all'archiviazione di una trasformazione affine in una coppia di matrici (uno per la parte lineare) e uno per la traduzione consiste nell'archiviare l'intera trasformazione in una matrice 3x3. Per eseguire questa operazione, un punto del piano deve essere archiviato in una matrice di 1 × 3 con una coordinata 3rd fittizia. La tecnica normale consiste nell'apportare tutte le coordinate 3rd uguale a 1. Ad esempio, il punto (2, 1) è rappresentato dalla matrice [1 di 1 di 2]. La figura seguente mostra una trasformazione affine (Ruota di 90 gradi; tradurre 3 unità sull'asse x, 4 unità nella direzione y) espresse come moltiplicazione per un singolo 3x3.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art09.gif "AboutGdip05_art09")  
  
 Nell'esempio precedente, il punto (2, 1) viene mappato al punto di (2, 6). Si noti che la terza colonna della matrice 3x3 contiene i numeri da 0, 0, 1. Questo sarà sempre il caso per la matrice 3x3 di trasformazione affine. I numeri più importanti sono i numeri delle sei colonne 1 e 2. L'angolo superiore sinistro porzione 2x2 della matrice rappresenta la parte della trasformazione lineare e le prime due voci nella riga 3 ° rappresentano la traduzione.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art10.gif "AboutGdip05_art10")  
  
 Nelle [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] è possibile archiviare una trasformazione affine in un <xref:System.Drawing.Drawing2D.Matrix> oggetto. Perché è sempre la terza colonna di una matrice che rappresenta una trasformazione affine o meno (0, 0, 1), quando costruisce è necessario specificare solo i numeri di sei nelle prime due colonne un <xref:System.Drawing.Drawing2D.Matrix> oggetto. L'istruzione `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` costruisce la matrice illustrata nella figura precedente.  
  
## <a name="composite-transformations"></a>Trasformazioni composte  
 Una trasformazione composita è una sequenza di trasformazioni, uno seguita da altro. Prendere in considerazione le matrici e le trasformazioni elencate di seguito:  
  
|||  
|-|-|  
|Matrice di oggetto|Ruota di 90 gradi|  
|Matrice di B|Ridimensionamento di un fattore pari a 2 nella direzione x|  
|Matrice di C|Tradurre 3 unità nella direzione y|  
  
 Se si inizia con il punto (2, 1), rappresentato dalla matrice [1 di 1 di 2] e moltiplicare per A, B, quindi quindi C, il punto (2, 1) subirà le tre trasformazioni nell'ordine elencato.  
  
 [2 1 1]ABC = [-2 5 1]  
  
 Anziché archiviare le tre parti della trasformazione composito in tre matrici distinte, è possibile moltiplicare A, B e C insieme per ottenere un singolo 3x3 che archivia l'intera trasformazione composta. Si supponga che ABC = D. Quindi un punto moltiplicato D assegna lo stesso risultato di un punto moltiplicato per A, B quindi quindi C.  
  
 [2 1 1]D = [-2 5 1]  
  
 La figura seguente mostra le matrici A, B, C e D.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art12.gif "AboutGdip05_art12")  
  
 Il fatto che la matrice di una trasformazione composita può essere formata dalla moltiplicazione di matrici di trasformazione individuali significa che qualsiasi sequenza di trasformazioni affini può essere archiviato in una singola <xref:System.Drawing.Drawing2D.Matrix> oggetto.  
  
> [!CAUTION]
>  È importante l'ordine di una trasformazione composita. In generale, ruotare, ridimensionare e quindi convertire è diverso da come scala, rotazione e quindi convertire. Analogamente, l'ordine della moltiplicazione di matrici è importante. In generale, ABC non è lo stesso come sfondo.  
  
 Il <xref:System.Drawing.Drawing2D.Matrix> classe fornisce diversi metodi per la creazione di una trasformazione composita: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, e <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>. L'esempio seguente crea la matrice di una trasformazione composita che prima di tutto ruota di 30 gradi, quindi ridimensiona in base a un fattore pari a 2 nella direzione y e quindi converte di 5 unità nella direzione x:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 Nella figura seguente viene illustrata la matrice.  
  
 ![Transformations](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art13.gif "AboutGdip05_art13")  
  
## <a name="see-also"></a>Vedere anche
- [Sistemi di coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
- [Uso di trasformazioni nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)

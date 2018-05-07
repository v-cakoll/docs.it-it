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
ms.openlocfilehash: 4c840d8a5abc89493bc684526ce76d34307f4ba1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="matrix-representation-of-transformations"></a>Rappresentazione tramite matrici delle trasformazioni
Una matrice di n × m è un set di numeri disposti in righe m e n colonne. Nella figura seguente mostra alcune matrici.  
  
 ![Le trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art04.gif "AboutGdip05_art04")  
  
 È possibile aggiungere due matrici delle stesse dimensioni mediante l'aggiunta di singoli elementi. Nella figura seguente mostra due esempi di aggiunta di una matrice.  
  
 ![Le trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art05.gif "AboutGdip05_art05")  
  
 Una matrice di n × m può essere moltiplicata per una matrice di p × n, e il risultato è una matrice di p × m. Il numero di colonne nella prima matrice deve essere lo stesso come il numero di righe della seconda matrice. Ad esempio, una matrice 4 × 2 può essere moltiplicata per una matrice 2 × 3 per produrre una matrice 4 × 3.  
  
 Punti nel piano e le righe e colonne di una matrice possono essere considerati come vettori. Ad esempio, (2, 5) è un vettore con due componenti e (3, 7, 1) è un vettore con tre componenti. Il prodotto scalare di due vettori viene definito come segue:  
  
 (a, b) • (c, d) = ac + bd  
  
 (a, b, c) • (d, e, f) = ad essere + + cf  
  
 Ad esempio, il prodotto scalare di (2, 3) e (5, 4) è (2)(5) + (3)(4) = 22. Il prodotto scalare di (2, 5, 1) e (4, 3, 1) è (2)(4) + (5)(3) + (1)(1) = 24. Si noti che il prodotto scalare di due vettori è un numero, non un altro vettore. Si noti inoltre che è possibile calcolare il prodotto scalare solo se i due vettori hanno lo stesso numero di componenti.  
  
 Consentire A(i, j) essere la voce nella matrice a nella riga e colonna jma. Ad esempio (3, 2) è la voce della matrice nella riga 3 e nella colonna 2. Si supponga che A, B e C sono matrici e AB = C. Le voci di C vengono calcolate come segue:  
  
 C (i, j) = • (riga i di a) (colonna j di B)  
  
 Nella figura seguente mostra alcuni esempi di moltiplicazione.  
  
 ![Le trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art06.gif "AboutGdip05_art06")  
  
 Se si ritiene di un punto in un piano come 1 matrice × 2, è possibile trasformare tale punto moltiplicandolo per una matrice 2x2. Nella figura seguente mostra diverse trasformazioni applicate al punto di (2, 1).  
  
 ![Le trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art07.gif "AboutGdip05_art07")  
  
 Tutte le trasformazioni illustrate nella figura precedente sono trasformazioni lineari. Altre trasformazioni, ad esempio di conversione, non sono lineari e non possono essere espressa come moltiplicazione per una matrice 2x2. Si supponga che si desidera iniziare con il punto (2, 1), ruotare di 90 gradi, convertirlo 3 unità nella direzione x e 4 unità nella direzione y. Questo scopo, è possibile tramite una moltiplicazione seguita dall'aggiunta di una matrice.  
  
 ![Le trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art08.gif "AboutGdip05_art08")  
  
 Una trasformazione lineare (moltiplicazione per una matrice 2x2) seguita da una traduzione (aggiunta di una matrice di × 2 1) viene chiamata una trasformazione affine. Un'alternativa all'archiviazione in una coppia di matrici (uno per la parte lineare) e uno per la traduzione di trasformazione affine consiste nell'archiviare l'intera trasformazione in una matrice 3x3. Per utilizzare questo un punto del piano deve essere archiviato in una matrice di 1 × 3 con una coordinata 3rd fittizia. La tecnica consueto consiste nell'apportare tutte le coordinate 3 uguale a 1. Ad esempio, il punto (2, 1) è rappresentato dalla matrice [2 1 1]. La figura seguente mostra una trasformazione affine (Ruota di 90 gradi; traslazione 3 unità nella direzione x e 4 unità nella direzione y) espressa come moltiplicazione per un singolo 3x3.  
  
 ![Le trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art09.gif "AboutGdip05_art09")  
  
 Nell'esempio precedente, il punto (2, 1) viene eseguito il mapping per il punto (2, 6). Si noti che la terza colonna della matrice 3x3 contiene i numeri da 0, 0, 1. Questo sarà sempre nel caso per la matrice 3x3 di trasformazione affine. I numeri più importanti sono i sei numeri nelle colonne 1 e 2. L'angolo superiore sinistro porzione 2x2 della matrice rappresenta la parte della trasformazione lineare e le prime due voci nella riga 3 rappresentano la traduzione.  
  
 ![Le trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art10.gif "AboutGdip05_art10")  
  
 In [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] è possibile archiviare una trasformazione affine in un <xref:System.Drawing.Drawing2D.Matrix> oggetto. Poiché la terza colonna di una matrice che rappresenta una trasformazione affine è sempre (0, 0, 1), quando costruisce è necessario specificare solo i numeri di sei nelle prime due colonne un <xref:System.Drawing.Drawing2D.Matrix> oggetto. L'istruzione `Matrix myMatrix = new Matrix(0, 1, -1, 0, 3, 4)` costruisce la matrice mostrata nella figura precedente.  
  
## <a name="composite-transformations"></a>Trasformazioni composte  
 Una trasformazione composita è una sequenza di trasformazioni, un seguito dagli altri. Considerare le matrici e le trasformazioni nell'elenco seguente:  
  
|||  
|-|-|  
|Matrice|Ruotare di 90 gradi|  
|Matrice B|Scala per un fattore pari a 2 nella direzione x|  
|Matrice di C|Tradurre 3 unità nella direzione y|  
  
 Se si inizia con il punto (2, 1), rappresentato dalla matrice [1 1 2]: e moltiplicare A, B, quindi quindi C, il punto (2, 1) subirà le tre trasformazioni nell'ordine elencato.  
  
 [2 1 1]ABC = [-2 5 1]  
  
 Anziché memorizzare le tre parti della trasformazione composita in tre matrici distinte, è possibile moltiplicare A, B e C insieme per ottenere un singolo 3x3 che archivia l'intera trasformazione composta. Si supponga che ABC = D. Quindi un punto moltiplicato per D offre lo stesso risultato di un punto moltiplicato per A, quindi B, quindi C.  
  
 [2 1 1]D = [-2 5 1]  
  
 La figura seguente mostra le matrici A, B, C e D.  
  
 ![Le trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art12.gif "AboutGdip05_art12")  
  
 Il fatto che la matrice di una trasformazione composta può essere formata dalla moltiplicazione di matrici di trasformazione individuali significa che qualsiasi sequenza di trasformazioni affini può essere archiviato in una singola <xref:System.Drawing.Drawing2D.Matrix> oggetto.  
  
> [!CAUTION]
>  L'ordine di una trasformazione composta è importante. In generale, ruotare, ridimensionare e quindi convertire non è la stessa scala, rotazione e quindi convertire. Analogamente, l'ordine di moltiplicazione è importante. In generale, ABC non è uguale a BAC.  
  
 Il <xref:System.Drawing.Drawing2D.Matrix> classe fornisce numerosi metodi per la creazione di una trasformazione composta: <xref:System.Drawing.Drawing2D.Matrix.Multiply%2A>, <xref:System.Drawing.Drawing2D.Matrix.Rotate%2A>, <xref:System.Drawing.Drawing2D.Matrix.RotateAt%2A>, <xref:System.Drawing.Drawing2D.Matrix.Scale%2A>, <xref:System.Drawing.Drawing2D.Matrix.Shear%2A>, e <xref:System.Drawing.Drawing2D.Matrix.Translate%2A>. L'esempio seguente crea la matrice di trasformazione composita prima ruotata di 30 gradi, quindi ridimensiona di un fattore pari a 2 nella direzione y, quindi converte di 5 unità nella direzione x:  
  
 [!code-csharp[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.CoordinateSystems#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#11)]  
  
 Nella figura seguente viene illustrata la matrice.  
  
 ![Le trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art13.gif "AboutGdip05_art13")  
  
## <a name="see-also"></a>Vedere anche  
 [Sistemi di coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Uso di trasformazioni nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)

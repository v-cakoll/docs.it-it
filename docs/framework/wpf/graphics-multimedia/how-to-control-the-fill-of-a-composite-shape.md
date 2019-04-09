---
title: 'Procedura: Controllare il riempimento di una forma composta'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], composite [WPF], controlling fill
- composite shapes [WPF], controlling fill
- graphics [WPF], composite shapes
- fill [WPF], controlling
ms.assetid: c1c94575-9eca-48a5-a49a-2ec65259f229
ms.openlocfilehash: 9b3ab1f7b81c296aa1ee766136b6c95b82cab105
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084050"
---
# <a name="how-to-control-the-fill-of-a-composite-shape"></a>Procedura: Controllare il riempimento di una forma composta
Il <xref:System.Windows.Media.GeometryGroup.FillRule%2A> proprietà di un <xref:System.Windows.Media.GeometryGroup> o un <xref:System.Windows.Media.PathGeometry>, specifica una "regola" usata dalla forma composta per determinare se un determinato punto fa parte della geometria. Esistono due possibili valori per <xref:System.Windows.Media.FillRule>: <xref:System.Windows.Media.FillRule.EvenOdd> e <xref:System.Windows.Media.FillRule.Nonzero>. Le sezioni seguenti descrivono come usare queste due regole.  
  
 **EvenOdd:** Questa regola determina se un punto si trova nell'area di riempimento tracciando un raggio da tale punto verso l'infinito in qualsiasi direzione e contando il numero di segmenti di percorso all'interno della forma interseca il raggio. Se questo numero è dispari, il punto è all'interno. Se invece è pari, il punto è all'esterno.  
  
 Ad esempio, il XAML seguente crea una forma composta costituita da una serie di anelli concentrici (destinazione) con un <xref:System.Windows.Media.GeometryGroup.FillRule%2A> impostato su <xref:System.Windows.Media.FillRule.EvenOdd>.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleEvenOddValue](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillruleevenoddvalue)]  
  
 La figura seguente mostra la forma creata nell'esempio precedente.  
  
 ![Schermata: Proprietà FillRule di EvenOdd](./media/fillruleevenoddfirstone.png "FillRuleEvenOddFirstOne")  
  
 Nell'illustrazione precedente, si noti che il centro e il terzo anello non sono riempiti, poiché un raggio tracciato da qualsiasi punto all'interno di uno di questi due anelli passa attraverso un numero pari di segmenti. Vedere la figura seguente:  
  
 ![Diagramma: Valore della proprietà FillRule di EvenOdd](./media/fillruleevenodd2.png "FillRuleEvenOdd2")  
  
 **Diverso da zero:** Questa regola determina se un punto si trova nell'area di riempimento del percorso tracciando un raggio da tale punto verso l'infinito in qualsiasi direzione ed esaminando i punti in cui un segmento della forma interseca il raggio. Partendo da zero, aggiungere uno ogni volta che un segmento interseca il raggio da sinistra a destra e sottrarre uno ogni volta che un segmento del tracciato interseca il raggio da destra a sinistra. Contare le intersezioni. Se il risultato è zero, il punto è all'esterno del percorso. In caso contrario, è all'interno.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValueEllipseGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovalueellipsegeometry)]  
  
 Nell'esempio precedente, un valore di <xref:System.Windows.Media.FillRule.Nonzero> per <xref:System.Windows.Media.GeometryGroup.FillRule%2A> restituisce come risultato la figura seguente:  
  
 ![Schermata: Valore FillRule di NonZero](./media/fillrulenonzero1.png "FillRuleNonZero1")  
  
 Come si può notare, tutti gli anelli sono riempiti, poiché tutti i segmenti scorrono nella stessa direzione, quindi un raggio tracciato da qualsiasi punto attraverserà uno o più segmenti e la somma delle intersecazioni non sarà uguale a zero. Ad esempio, nell'illustrazione seguente, le frecce rosse rappresentano la direzione in cui vengono tracciati i segmenti e la freccia bianca rappresenta un raggio qualsiasi da un punto dell'anello più interno. A partire da un valore pari a zero, per ogni segmento intersecato dal raggio viene aggiunto un valore di uno, poiché il segmento interseca il raggio da sinistra a destra.  
  
 ![Diagramma: Valore della proprietà FillRule uguale a NonZero](./media/fillrulenonzero2.png "FillRuleNonZero2")  
  
 Per illustrare meglio il comportamento di <xref:System.Windows.Media.FillRule.Nonzero> è necessaria una forma più complessa con segmenti di esecuzione in diverse direzioni di regola. Il codice XAML seguente crea una forma simile all'esempio precedente, ad eccezione del fatto che venga creata con una <xref:System.Windows.Media.PathGeometry> anziché un <xref:System.Windows.Media.EllipseGeometry> che crea quattro archi concentrici completamente chiusi cerchi concentrici.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#FillRuleNonZeroValuePathGeometry](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/FillRuleExample.xaml#fillrulenonzerovaluepathgeometry)]  
  
 La figura seguente mostra la forma creata nell'esempio precedente.  
  
 ![Schermata: Valore della proprietà FillRule di NonZero](./media/fillrulenonzero3.png "FillRuleNonZero3")  
  
 Si noti che il terzo arco dal centro non viene riempito. La figura seguente spiega per quale motivo. Nella figura le frecce rosse rappresentano la direzione in cui vengono tracciati i segmenti. Le due frecce bianche rappresentano due raggi qualsiasi che partono da un punto nell'area "non riempita". Come si può notare dalla figura, la somma dei valori da un raggio specificato che interseca i segmenti nel suo tracciato è pari a zero. Come definito in precedenza, una somma pari a zero indica che il punto non fa parte della geometria (non fa parte del riempimento), mentre una somma *diversa* da zero, compresi i valori negativi, fa parte della geometria.  
  
 ![Diagramma: Valore della proprietà FillRule di NonZero](./media/fillrulenonzero4.png "FillRuleNonZero4")  
  
 **Nota:** Ai fini di <xref:System.Windows.Media.FillRule>, tutte le forme sono considerate chiuse. Se è presente una distanza in un segmento, disegnare una linea immaginaria per chiuderla. Nell'esempio precedente sono presenti piccole distanze negli anelli. In questo caso si potrebbe prevedere un raggio che attraversa la distanza per produrre un risultato diverso da un raggio in un'altra direzione. Di seguito è riportata un'immagine ingrandita di una di queste distanze e il "segmento immaginario" (tracciato allo scopo di applicare il <xref:System.Windows.Media.FillRule>) che lo chiude.  
  
 ![Diagramma: Per FillRule i segmenti sono sempre chiusi](./media/fillruleclosedshapes.png "FillRuleClosedShapes")  
  
## <a name="example"></a>Esempio  
  
## <a name="see-also"></a>Vedere anche

- [Creare una forma composta](how-to-create-a-composite-shape.md)
- [Cenni preliminari sulle classi Geometry](geometry-overview.md)

---
title: Dimensioni di matrice
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: f971f0c3693177adbcb8869d487e3ad41d49ddc2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413104"
---
# <a name="array-dimensions-in-visual-basic"></a>Dimensioni di matrice in Visual Basic

Una *dimensione* rappresenta una direzione in cui è possibile variare la specifica degli elementi di una matrice. Una matrice che contiene il totale delle vendite per ogni giorno del mese ha una dimensione (il giorno del mese). Una matrice che contiene il totale delle vendite per reparto per ogni giorno del mese ha due dimensioni, ovvero il numero del reparto e il giorno del mese. Il numero di dimensioni di una matrice è denominato *rango*.

> [!NOTE]
> È possibile usare la <xref:System.Array.Rank%2A> proprietà per determinare il numero di dimensioni di una matrice.

## <a name="working-with-dimensions"></a>Utilizzo delle dimensioni

Per specificare un elemento di una matrice, è necessario specificare un indice *o un* *Indice* per ogni dimensione. Gli elementi sono contigui lungo ogni dimensione dall'indice 0 all'indice più alto per tale dimensione.

Nelle illustrazioni seguenti viene illustrata la struttura concettuale di matrici con diverse classificazioni. Ogni elemento nelle illustrazioni mostra i valori di indice che vi accedono. Ad esempio, è possibile accedere al primo elemento della seconda riga della matrice bidimensionale specificando gli indici `(1, 0)` .

![Diagramma che mostra una matrice unidimensionale.](./media/array-dimensions/one-dimensional-array.gif)

![Diagramma che mostra una matrice bidimensionale.](./media/array-dimensions/two-dimensional-array.gif)

![Diagramma che mostra una matrice tridimensionale.](./media/array-dimensions/three-dimensional-array.gif)

### <a name="one-dimension"></a>Una dimensione

Molte matrici hanno solo una dimensione, ad esempio il numero di persone di ogni età. L'unico requisito per specificare un elemento è l'età per cui l'elemento include il conteggio. Pertanto, una matrice di questo tipo utilizza un solo indice. Nell'esempio seguente viene dichiarata una variabile per includere una *matrice unidimensionale* di età compresa tra 0 e 120.

```vb
Dim ageCounts(120) As UInteger
```

### <a name="two-dimensions"></a>Due dimensioni

Alcune matrici hanno due dimensioni, ad esempio il numero di uffici in ogni piano di ogni edificio in un campus. La specifica di un elemento richiede il numero di edificio e il piano e ogni elemento include il conteggio per la combinazione di compilazione e piano. Pertanto, una matrice di questo tipo utilizza due indici. Nell'esempio seguente viene dichiarata una variabile in cui è contenuta una *matrice bidimensionale* di conteggi di Office, per edifici da 0 a 40 e da piani 0 a 5.

```vb
Dim officeCounts(40, 5) As Byte
```

Una matrice bidimensionale viene definita anche *matrice rettangolare*.

### <a name="three-dimensions"></a>Tre dimensioni

Alcune matrici hanno tre dimensioni, ad esempio valori nello spazio tridimensionale. Tale matrice utilizza tre indici, che in questo caso rappresentano le coordinate x, y e z dello spazio fisico. Nell'esempio seguente viene dichiarata una variabile in cui è contenuta una *matrice tridimensionale* di temperature aeree in vari punti in un volume tridimensionale.

```vb
Dim airTemperatures(99, 99, 24) As Single
```

### <a name="more-than-three-dimensions"></a>Più di tre dimensioni

Sebbene una matrice possa avere un numero di dimensioni pari a 32, è raro avere più di tre dimensioni.

> [!NOTE]
> Quando si aggiungono dimensioni a una matrice, lo spazio di archiviazione totale necessario per l'array aumenta considerevolmente, pertanto è opportuno utilizzare matrici multidimensionali con cautela.

## <a name="using-different-dimensions"></a>Utilizzo di dimensioni diverse

Si supponga di voler tenere traccia degli importi delle vendite per ogni giorno del mese corrente. È possibile dichiarare una matrice unidimensionale con 31 elementi, uno per ogni giorno del mese, come illustrato nell'esempio riportato di seguito.

```vb
Dim salesAmounts(30) As Double
```

Si supponga ora di voler tenere traccia delle stesse informazioni non solo per ogni giorno del mese, ma anche per ogni mese dell'anno. È possibile dichiarare una matrice bidimensionale con 12 righe (per i mesi) e 31 colonne (per i giorni), come illustrato nell'esempio riportato di seguito.

```vb
Dim salesAmounts(11, 30) As Double
```

Si supponga ora di decidere se la matrice contiene informazioni per più di un anno. Se si desidera tenere traccia degli importi delle vendite per 5 anni, è possibile dichiarare una matrice tridimensionale con 5 livelli, 12 righe e 31 colonne, come illustrato nell'esempio riportato di seguito.

```vb
Dim salesAmounts(4, 11, 30) As Double
```

Si noti che, poiché ogni indice varia da 0 al massimo, ogni dimensione di `salesAmounts` viene dichiarata come una minore della lunghezza richiesta per tale dimensione. Si noti inoltre che le dimensioni della matrice aumentano con ogni nuova dimensione. Le tre dimensioni degli esempi precedenti sono rispettivamente 31, 372 e 1.860.

> [!NOTE]
> È possibile creare una matrice senza utilizzare l' `Dim` istruzione o la `New` clausola. Ad esempio, è possibile chiamare il <xref:System.Array.CreateInstance%2A> metodo oppure un altro componente può passare il codice a una matrice creata in questo modo. Una matrice di questo tipo può avere un limite inferiore diverso da 0. È sempre possibile verificare il limite inferiore di una dimensione tramite il <xref:System.Array.GetLowerBound%2A> metodo o la `LBound` funzione.

## <a name="see-also"></a>Vedere anche

- [Matrici](index.md)
- [Risoluzione dei problemi relativi alle matrici](troubleshooting-arrays.md)

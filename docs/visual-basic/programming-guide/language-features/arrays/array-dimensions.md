---
title: Dimensioni di matrice in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 0b4e7c9e253f94e1e28700c8669d28799ab69d91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053717"
---
# <a name="array-dimensions-in-visual-basic"></a>Dimensioni di matrice in Visual Basic
Oggetto *dimensione* è una direzione in cui è possibile modificare la specifica di elementi della matrice. Matrice contenente le vendite totali per ogni giorno del mese ha una dimensione (il giorno del mese). Matrice contenente le vendite totali per reparto per ciascun giorno del mese ha due dimensioni (il numero di reparto e il giorno del mese). Il numero di dimensioni è una matrice viene chiamato relativa *rank*.  
  
> [!NOTE]
>  È possibile usare il <xref:System.Array.Rank%2A> proprietà per determinare il numero di dimensioni di una matrice.  
  
## <a name="working-with-dimensions"></a>Utilizzo delle dimensioni  
 È possibile specificare un elemento della matrice fornendo un' *indice* oppure *pedice* per ognuna delle relative dimensioni. Gli elementi sono contigui in ogni dimensione dall'indice 0 dell'indice più alto per tale dimensione.  
  
 Le illustrazioni seguenti mostrano la struttura concettuale di matrici con intervalli diversi. Ogni elemento nelle figure Mostra i valori di indice che vi accedono. Ad esempio, è possibile accedere il primo elemento della seconda riga della matrice bidimensionale specificando gli indici `(1, 0)`.  
  
 ![Diagramma che mostra una matrice unidimensionale.](./media/array-dimensions/one-dimensional-array.gif)  
  
 ![Diagramma che mostra una matrice bidimensionale.](./media/array-dimensions/two-dimensional-array.gif)  
  
 ![Diagramma che mostra una matrice tridimensionale.](./media/array-dimensions/three-dimensional-array.gif)  
  
### <a name="one-dimension"></a>Una dimensione  
 Le matrici molti hanno solo una dimensione, ad esempio il numero di persone di ogni età. L'unico requisito per specificare un elemento è il periodo di validità per il quale questo elemento contiene il conteggio. Pertanto, ad esempio una matrice Usa un solo indice. L'esempio seguente dichiara una variabile per contenere una *matrice unidimensionale* di età conta rivolto a 0 e 120.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a>Due dimensioni  
 Alcuni array di avere due dimensioni, ad esempio il numero di uffici in ogni parte intera di ogni compilazione in un campus. La specifica di un elemento richiede che il numero di compilazione e la parte intera e ogni elemento contiene il conteggio per la combinazione di edificio e piano. Pertanto, ad esempio una matrice usa due indici non cluster. L'esempio seguente dichiara una variabile per contenere una *matrice bidimensionale* dei conteggi di office, per gli edifici 0 e 40 e piani compresi tra 0 a 5.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 Una matrice bidimensionale viene anche chiamata un' *matrice rettangolare*.  
  
### <a name="three-dimensions"></a>Tre dimensioni  
 Le matrici alcuni hanno tre dimensioni, ad esempio i valori nello spazio tridimensionale. Ad esempio una matrice Usa tre indici, che in questo caso rappresentano x, y e le coordinate z spazio fisico. L'esempio seguente dichiara una variabile per contenere una *matrice tridimensionale* della temperatura dell'aria in momenti diversi in un volume tridimensionale.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a>Più di tre dimensioni  
 Anche se una matrice può avere un massimo di 32 dimensioni, è raro che ne abbia più di tre.  
  
> [!NOTE]
>  Quando si aggiungono le dimensioni a una matrice, l'archiviazione totale necessario per la matrice aumenta notevolmente, pertanto si consiglia di utilizzare le matrici multidimensionali con cautela.  
  
## <a name="using-different-dimensions"></a>Utilizzo di dimensioni diverse  
 Si supponga che si desidera rilevare gli importi delle vendite per ogni giorno del mese attuale. È possibile dichiarare una matrice unidimensionale con gli 31 elementi, uno per ogni giorno del mese, come illustrato nell'esempio seguente viene illustrato.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 Ora si supponga che si desidera rilevare le stesse informazioni non solo per tutti i giorni del mese, ma anche per ogni mese dell'anno. È possibile dichiarare una matrice bidimensionale di 12 righe (per i mesi) e 31 colonne (per i giorni), come illustrato nell'esempio seguente.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 Ora si supponga che si decide di avere la matrice contengono informazioni per più di un anno. Se si vuole tenere traccia di importi delle vendite per 5 anni, è possibile dichiarare una matrice tridimensionale con livelli di 5, 12 righe e 31 colonne, come illustrato nell'esempio seguente.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 Si noti che, poiché ogni indice varia da 0 al valore massimo, ciascuna dimensione del `salesAmounts` viene dichiarata come uno in meno rispetto alla lunghezza desiderata per la dimensione. Si noti inoltre che le dimensioni della matrice aumentano con ogni nuova dimensione. Le tre dimensioni negli esempi precedenti sono 1860 elementi, 372 e 31.  
  
> [!NOTE]
>  È possibile creare una matrice senza utilizzare il `Dim` istruzione o il `New` clausola. Ad esempio, è possibile chiamare il <xref:System.Array.CreateInstance%2A> metodo o un altro componente può passare al codice una matrice creata in questo modo. Ad esempio una matrice può avere un limite inferiore diverso da 0. È sempre possibile verificare il limite inferiore di una dimensione utilizzando la <xref:System.Array.GetLowerBound%2A> metodo o il `LBound` (funzione).  
  
## <a name="see-also"></a>Vedere anche

- [Matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Risoluzione dei problemi relativi alle matrici](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)

---
title: Dimensioni di matrice in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21e170ca5942862a26e05428fffaea7d1e875e19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="array-dimensions-in-visual-basic"></a>Dimensioni di matrice in Visual Basic
Oggetto *dimensione* indica una direzione in cui è possibile variare la specifica di elementi della matrice. Matrice contenente le vendite totali per ogni giorno del mese ha una dimensione (giorno del mese). Matrice contenente le vendite totali per reparto per ogni giorno del mese ha due dimensioni (il numero di reparto e il giorno del mese). Il numero di dimensioni è una matrice viene chiamato il relativo *rank*.  
  
> [!NOTE]
>  È possibile utilizzare il <xref:System.Array.Rank%2A> proprietà per determinare il numero di dimensioni di una matrice.  
  
## <a name="working-with-dimensions"></a>Utilizzo delle dimensioni  
 È possibile specificare un elemento di una matrice fornendo un *indice* o *pedice* per ciascuna delle relative dimensioni. Gli elementi sono contigui lungo ciascuna dimensione dall'indice 0 dell'indice più alto per tale dimensione.  
  
 Le illustrazioni seguenti mostrano la struttura concettuale di matrici con intervalli diversi. Ogni elemento illustrato nelle figure vengono illustrati i valori di indice di diritti di accesso. Ad esempio, si può accedere al primo elemento della seconda riga della matrice bidimensionale specificando gli indici `(1, 0)`.  
  
 ![Diagramma grafico di una finestra di &#45; matrice dimensionale](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")  
Matrice unidimensionale  
  
 ![Diagramma grafico di due &#45; matrice dimensionale](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")  
matrice bidimensionale  
  
 ![Diagramma grafico di tre &#45; matrice dimensionale](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")  
Matrice tridimensionale  
  
### <a name="one-dimension"></a>Una dimensione  
 Molte matrici hanno una sola dimensione, ad esempio il numero di persone di ciascuna età. L'unico requisito per specificare un elemento è la durata per cui tale elemento contiene il conteggio. Tale matrice utilizza pertanto un solo indice. Nell'esempio seguente viene dichiarata una variabile per contenere un *unidimensionale* di età i conteggi per età compresi tra 0 e 120.  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a>Due dimensioni  
 Alcune matrici hanno due dimensioni, ad esempio il numero di uffici in ogni piano di ogni compilazione in una struttura. La specifica di un elemento richiede che il numero di compilazione e la base e ogni elemento contiene il numero per la combinazione di edificio e piano. Di conseguenza, tale matrice usa due indici. Nell'esempio seguente viene dichiarata una variabile per contenere un *matrice bidimensionale* dei conteggi di office, per edifici 0 e 40 e piani compresi tra 0 e 5.  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 Una matrice bidimensionale viene inoltre chiamata un *matrice rettangolare*.  
  
### <a name="three-dimensions"></a>Tre dimensioni  
 Alcune matrici hanno tre dimensioni, ad esempio i valori in uno spazio tridimensionale. Tale matrice utilizza tre indici, che in questo caso rappresentano le coordinate z di spazio fisico, x e y. Nell'esempio seguente viene dichiarata una variabile per contenere un *matrice tridimensionale* delle temperature aria in vari punti in un volume tridimensionale.  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a>Più di tre dimensioni  
 Anche se una matrice può avere un massimo di 32 dimensioni, è raro che ne abbia più di tre.  
  
> [!NOTE]
>  Quando si aggiungono dimensioni a una matrice, l'archiviazione totale necessaria per la matrice aumenta notevolmente, pertanto si consiglia di utilizzare le matrici multidimensionali con cautela.  
  
## <a name="using-different-dimensions"></a>Utilizzo di dimensioni diverse  
 Si supponga che si desidera rilevare gli importi delle vendite per ogni giorno del mese corrente. È possibile dichiarare una matrice unidimensionale con 31 elementi, uno per ogni giorno del mese, come nell'esempio seguente viene illustrato.  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 Ora si supponga che si desidera rilevare le stesse informazioni non solo per ogni giorno del mese, ma anche per ogni mese dell'anno. È possibile dichiarare una matrice bidimensionale con 12 righe (per i mesi) e 31 colonne (per i giorni), come illustrato nell'esempio seguente.  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 Ora si supponga che si sceglie la matrice contengono informazioni per più di un anno. Se si desidera rilevare gli importi delle vendite per 5 anni, è possibile dichiarare una matrice tridimensionale con 5 livelli, 12 righe e 31 colonne, come illustrato nell'esempio seguente.  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 Si noti che, poiché ogni indice varia da 0 al valore massimo, ogni dimensione di `salesAmounts` è dichiarato come una minore della lunghezza necessari per la dimensione. Si noti inoltre che le dimensioni della matrice aumentano con ogni nuova dimensione. Le tre dimensioni negli esempi precedenti sono 31, 372 e 1860 elementi.  
  
> [!NOTE]
>  È possibile creare una matrice senza utilizzare il `Dim` istruzione o `New` clausola. Ad esempio, è possibile chiamare il <xref:System.Array.CreateInstance%2A> metodo o un altro componente può passare al codice una matrice creata in questo modo. Tale matrice può avere un limite inferiore diverso da 0. È sempre possibile verificare il limite inferiore di una dimensione utilizzando il <xref:System.Array.GetLowerBound%2A> metodo o `LBound` (funzione).  
  
## <a name="see-also"></a>Vedere anche  
 [Array](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Risoluzione dei problemi relativi alle matrici](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)

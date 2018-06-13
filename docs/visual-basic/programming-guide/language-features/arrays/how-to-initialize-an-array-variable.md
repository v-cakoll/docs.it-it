---
title: 'Procedura: inizializzare una variabile di matrice in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: ee8cb91fd2fae9637a0d0e33fca63a4cdb9d2fce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651570"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>Procedura: inizializzare una variabile di matrice in Visual Basic
Inizializzare una variabile di matrice includendo una matrice di valori letterale in una `New` clausola e specificando i valori iniziali della matrice. È possibile specificare il tipo o consentire che possa essere dedotto dai valori nel valore letterale di matrice. Per ulteriori informazioni su come viene dedotto il tipo, vedere "Compilazione di una matrice con i valori iniziali" in [matrici](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>Per inizializzare una variabile di matrice con un valore letterale di matrice  
  
-   Nel `New` clausola, o quando si assegna il valore di matrice, specificare i valori degli elementi tra parentesi graffe (`{}`). L'esempio seguente mostra i diversi modi per dichiarare, creare e inizializzare una variabile per contenere una matrice che contiene elementi di tipo `Char`.  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     Dopo l'esecuzione di ogni istruzione, la matrice che viene creata avrà una lunghezza pari a 3, con gli elementi in corrispondenza dell'indice 0 e l'indice 2 contenente i valori iniziali. Se si specificano sia il limite superiore che i valori, è necessario includere un valore per ogni elemento dall'indice 0 al limite superiore.  
  
     Si noti che non è necessario specificare il limite superiore dell'indice, se si specificano valori di elemento in un valore letterale della matrice. Se non viene specificato alcun limite superiore, le dimensioni della matrice viene dedotto in base al numero di valori nel valore letterale di matrice.  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>Per inizializzare una variabile di matrice multidimensionale tramite valori letterali di matrice  
  
-   Annidare i valori tra parentesi graffe (`{}`) all'interno delle parentesi graffe. Verificare che i valori letterali di matrice annidati che tutti dedotti come matrici dello stesso tipo e lunghezza. Esempio di codice seguente mostra alcuni esempi di inizializzazione di matrici multidimensionali.  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   In modo esplicito, è possibile specificare i limiti della matrice o lasciarli e che il compilatore di dedurre il tipo di matrice in base ai valori nel valore letterale di matrice. Se si fornisce i valori e i limiti superiori, è necessario includere un valore per ogni elemento dall'indice 0 al limite superiore di ogni dimensione. Nell'esempio seguente vengono illustrati vari modi per dichiarare, creare e inizializzare una variabile per contenere una matrice bidimensionale con elementi di tipo `Short`  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     Dopo l'esecuzione di ogni istruzione, la matrice creata contiene sei elementi inizializzati con gli indici `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, e `(1,2)`. Ogni posizione della matrice contiene il valore `10`.  
  
-   Nell'esempio seguente viene eseguito lo scorrimento di una matrice multidimensionale. In un'applicazione console di Windows che viene scritto in Visual Basic, incollare il codice all'interno di `Sub Main()` metodo. I commenti ultimo mostrano l'output.  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>Per inizializzare una variabile di matrice di matrici mediante valori letterali di matrice  
  
-   Annidare i valori di oggetto tra parentesi graffe (`{}`). Anche se è inoltre possibile annidare i valori letterali di matrice che specificano matrici di lunghezza diversa, nel caso di una matrice di matrici, assicurarsi che i valori letterali di matrice annidati vengono racchiusi tra parentesi (`()`). Le parentesi forzano la valutazione dei valori letterali di matrice annidati e le matrici risultanti vengono utilizzate come i valori iniziali della matrice di matrici. Esempio di codice seguente mostra due esempi di inizializzazione di matrice di matrici.  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   Nell'esempio seguente viene eseguito lo scorrimento di una matrice di matrici. In un'applicazione console di Windows che viene scritto in Visual Basic, incollare il codice all'interno di `Sub Main()` metodo.  L'ultimo commenti nel codice viene illustrato l'output.  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Array](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Risoluzione dei problemi relativi alle matrici](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)

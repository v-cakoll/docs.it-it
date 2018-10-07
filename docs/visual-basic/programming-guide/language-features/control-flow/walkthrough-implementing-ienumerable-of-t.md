---
title: Implementazione di IEnumerable in Visual Basic
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: be2eefdc52d38df3071d457b7a71dbac6eaa2657
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836998"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Procedura dettagliata: implementazione di IEnumerable(Of T) in Visual Basic
Il <xref:System.Collections.Generic.IEnumerable%601> interfaccia è implementata da classi che possono restituire una sequenza di valori di un elemento alla volta. Il vantaggio di restituzione di dati è un elemento in un momento non è necessario caricare il set completo di dati in memoria sul relativo utilizzo. È sufficiente usare quantità di memoria sufficiente per caricare un singolo elemento dai dati. Le classi che implementano il `IEnumerable(T)` interfaccia può essere usata con `For Each` cicli o query LINQ.  
  
 Ad esempio, si consideri un'applicazione che deve leggere un file di testo di grandi dimensioni e restituire ogni riga del file che corrisponde ai criteri di ricerca specifico. L'applicazione usa una query LINQ per restituire le righe dal file che corrispondono ai criteri specificati. Per eseguire query sul contenuto del file usando una query LINQ, l'applicazione è stato possibile caricare il contenuto del file in una matrice o una raccolta. Tuttavia, il caricamento dell'intero file in una matrice o raccolta richiederebbe più memoria rispetto a quelli necessari. La query LINQ può invece eseguire una query il contenuto del file usando una classe enumerable, che restituisce solo i valori che corrispondono ai criteri di ricerca. Le query che restituiscono solo alcuni valori corrispondenti richiederebbe molto meno memoria.  
  
 È possibile creare una classe che implementa il <xref:System.Collections.Generic.IEnumerable%601> interfaccia da esporre dati di origine dati enumerabili. Classe che implementa il `IEnumerable(T)` interfaccia richiederà un'altra classe che implementa il <xref:System.Collections.Generic.IEnumerator%601> interfaccia per scorrere i dati di origine. Queste due classi consentono di restituire gli elementi di dati in sequenza come un tipo specifico.  
  
 In questa procedura dettagliata, si creerà una classe che implementa il `IEnumerable(Of String)` interfaccia e una classe che implementa il `IEnumerator(Of String)` interfaccia per leggere un file di testo una riga alla volta.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Creazione della classe Enumerable  
  
**Creare il progetto della classe enumerable**

1.  In Visual Basic nel **File** dal menu **New** e quindi fare clic su **progetto**.

1.  Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**. Selezionare **Libreria di classi** nel riquadro **Modelli**. Nella casella **Nome** digitare `StreamReaderEnumerable` e quindi fare clic su **OK**. Viene visualizzato il nuovo progetto.

1.  Nelle **Esplora soluzioni**, fare doppio clic su file Class1.vb e fare clic su **rinominare**. Rinominare il file `StreamReaderEnumerable.vb` e premere INVIO. Modificando il nome del file, anche la classe verrà rinominata `StreamReaderEnumerable`. Questa classe implementerà l'interfaccia `IEnumerable(Of String)`.

1.  Pulsante destro del mouse sul progetto StreamReaderEnumerable, scegliere **Add**, quindi fare clic su **nuovo elemento**. Selezionare il **classe** modello. Nel **Name** , digitare `StreamReaderEnumerator.vb` e fare clic su **OK**.

 La prima classe nel progetto è la classe enumerable e verrà implementata il `IEnumerable(Of String)` interfaccia. Questa interfaccia generica implementa il <xref:System.Collections.IEnumerable> interfaccia e fa in modo che i consumer di questa classe possono accedere a valori tipizzati come `String`.  
  
**Aggiungere il codice per implementare IEnumerable**

1. Aprire il file StreamReaderEnumerable.

2. Nella riga successiva `Public Class StreamReaderEnumerable`, digitare il comando seguente e premere INVIO.

   [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]

   Visual Basic popola automaticamente la classe con i membri necessari per il `IEnumerable(Of String)` interfaccia.
  
3. Questa classe enumerable leggerà le righe da un file di testo una riga alla volta. Aggiungere il codice seguente alla classe per esporre un costruttore pubblico che accetta un percorso di file come parametro di input.

   [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]

4. L'implementazione del <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> metodo per il `IEnumerable(Of String)` interfaccia restituirà una nuova istanza del `StreamReaderEnumerator` classe. L'implementazione del `GetEnumerator` metodo per il `IEnumerable` interfaccia può essere reso `Private`, in quanto è necessario esporre solo i membri del `IEnumerable(Of String)` interfaccia. Sostituire il codice Visual Basic generato per il `GetEnumerator` metodi con il codice seguente.

   [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]  
  
**Aggiungere il codice per l'implementazione di IEnumerator**

1. Aprire il file StreamReaderEnumerator.

2. Nella riga successiva `Public Class StreamReaderEnumerator`, digitare il comando seguente e premere INVIO.

   [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]

   Visual Basic popola automaticamente la classe con i membri necessari per il `IEnumerator(Of String)` interfaccia.

3. La classe dell'enumeratore consente di aprire il file di testo ed esegue il file dei / o per leggere le righe dal file. Aggiungere il codice seguente alla classe per esporre un costruttore pubblico che accetta un percorso di file come parametro di input e aprire il file di testo per la lettura.

   [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]

4. Il `Current` delle proprietà per entrambi i `IEnumerator(Of String)` e `IEnumerator` interfacce restituiscono l'elemento corrente dal file di testo come un `String`. L'implementazione del `Current` proprietà del `IEnumerator` interfaccia può essere reso `Private`, in quanto è necessario esporre solo i membri del `IEnumerator(Of String)` interfaccia. Sostituire il codice Visual Basic generato per il `Current` proprietà con il codice seguente.

   [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]

5. Il `MoveNext` metodo per il `IEnumerator` interfaccia passa all'elemento successivo nel file di testo e aggiorna il valore restituito dal `Current` proprietà. Se non esistono nessun ulteriore elemento da leggere, il `MoveNext` restituzione del metodo `False`; in caso contrario, il `MoveNext` restituzione del metodo `True`. Aggiungere al metodo `MoveNext` il seguente codice.

   [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]

6. Il `Reset` metodo di `IEnumerator` interfaccia indirizza l'iteratore in modo che punti all'inizio del file di testo e cancella il valore dell'elemento corrente. Aggiungere al metodo `Reset` il seguente codice.

   [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]

7. Il `Dispose` metodo di `IEnumerator` interfaccia garantisce che tutte le risorse non gestite vengono rilasciate prima dell'eliminazione permanente dell'iteratore. L'handle di file che viene usato per il `StreamReader` oggetto è una risorsa non gestita e deve essere chiuso prima che l'istanza dell'iteratore viene eliminato definitivamente. Sostituire il codice Visual Basic generato per il `Dispose` metodo con il codice seguente.

   [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)] 
  
## <a name="using-the-sample-iterator"></a>Usando l'iteratore di esempio

 È possibile usare una classe enumerable nel codice insieme alle strutture di controllo che richiedono un oggetto che implementa `IEnumerable`, ad esempio un `For Next` ciclo o una query LINQ. L'esempio seguente illustra il `StreamReaderEnumerable` in una query LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Istruzione For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

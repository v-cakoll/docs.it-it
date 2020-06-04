---
title: Implementazione di IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 582957c91eac63cf7f72dd2f6c0cf40e627be686
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402031"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Procedura dettagliata: implementazione di IEnumerable(Of T) in Visual Basic
L' <xref:System.Collections.Generic.IEnumerable%601> interfaccia viene implementata da classi che possono restituire una sequenza di valori un elemento alla volta. Il vantaggio di restituire dati un elemento alla volta è che non è necessario caricare il set completo di dati in memoria per utilizzarlo. È sufficiente utilizzare memoria sufficiente per caricare un singolo elemento dai dati. Le classi che implementano l' `IEnumerable(T)` interfaccia possono essere utilizzate con i `For Each` cicli o le query LINQ.  
  
 Si consideri, ad esempio, un'applicazione che deve leggere un file di testo di grandi dimensioni e restituire ogni riga del file che corrisponde a criteri di ricerca specifici. L'applicazione usa una query LINQ per restituire le righe del file che corrispondono ai criteri specificati. Per eseguire una query sul contenuto del file utilizzando una query LINQ, l'applicazione potrebbe caricare il contenuto del file in una matrice o in una raccolta. Tuttavia, il caricamento dell'intero file in una matrice o in una raccolta utilizzerebbe una quantità di memoria maggiore di quella richiesta. La query LINQ può invece eseguire una query sul contenuto del file usando una classe Enumerable, restituendo solo i valori che corrispondono ai criteri di ricerca. Le query che restituiscono solo pochi valori corrispondenti utilizzeranno una quantità di memoria molto inferiore.  
  
 È possibile creare una classe che implementi l' <xref:System.Collections.Generic.IEnumerable%601> interfaccia per esporre i dati di origine come dati enumerabili. La classe che implementa l' `IEnumerable(T)` interfaccia richiede un'altra classe che implementa l' <xref:System.Collections.Generic.IEnumerator%601> interfaccia per eseguire l'iterazione dei dati di origine. Queste due classi consentono di restituire elementi di dati in sequenza come un tipo specifico.  
  
 In questa procedura dettagliata verrà creata una classe che implementa l' `IEnumerable(Of String)` interfaccia e una classe che implementa l' `IEnumerator(Of String)` interfaccia per leggere un file di testo una riga alla volta.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Creazione della classe Enumerable  
  
**Creare il progetto di classe Enumerable**

1. In Visual Basic scegliere **nuovo** dal menu **file** , quindi fare clic su **progetto**.

1. Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**. Selezionare **Libreria di classi** nel riquadro **Modelli**. Nella casella **Nome** digitare `StreamReaderEnumerable`, quindi fare clic su **OK**. Verrà visualizzato il nuovo progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul file Class1. vb e scegliere **Rinomina**. Rinominare il file `StreamReaderEnumerable.vb` e premere INVIO. Modificando il nome del file, anche la classe verrà rinominata `StreamReaderEnumerable`. Questa classe implementerà l'interfaccia `IEnumerable(Of String)`.

1. Fare clic con il pulsante destro del mouse sul progetto StreamReaderEnumerable, scegliere **Aggiungi**, quindi fare clic su **nuovo elemento**. Selezionare il modello di **classe** . Digitare `StreamReaderEnumerator.vb` nella casella **Nome** e quindi fare clic su **OK**.

 La prima classe in questo progetto è la classe Enumerable e implementa l' `IEnumerable(Of String)` interfaccia. Questa interfaccia generica implementa l' <xref:System.Collections.IEnumerable> interfaccia e garantisce che gli utenti di questa classe possano accedere ai valori tipizzati come `String` .  
  
**Aggiungere il codice per implementare IEnumerable**

1. Aprire il file StreamReaderEnumerable. vb.

2. Nella riga dopo `Public Class StreamReaderEnumerable` digitare il comando seguente e premere INVIO.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic popola automaticamente la classe con i membri richiesti dall' `IEnumerable(Of String)` interfaccia.
  
3. Questa classe enumerabile leggerà le righe da un file di testo una riga alla volta. Aggiungere il codice seguente alla classe per esporre un costruttore pubblico che accetta un percorso di file come parametro di input.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. L'implementazione del <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> metodo dell' `IEnumerable(Of String)` interfaccia restituirà una nuova istanza della `StreamReaderEnumerator` classe. L'implementazione del `GetEnumerator` metodo dell' `IEnumerable` interfaccia può essere eseguita `Private` , perché è necessario esporre solo i membri dell' `IEnumerable(Of String)` interfaccia. Sostituire il codice generato Visual Basic per i `GetEnumerator` metodi con il codice seguente.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**Aggiungere il codice per implementare IEnumerator**

1. Aprire il file StreamReaderEnumerator. vb.

2. Nella riga dopo `Public Class StreamReaderEnumerator` digitare il comando seguente e premere INVIO.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic popola automaticamente la classe con i membri richiesti dall' `IEnumerator(Of String)` interfaccia.

3. La classe Enumerator apre il file di testo ed esegue l'I/O del file per leggere le righe dal file. Aggiungere il codice seguente alla classe per esporre un costruttore pubblico che accetta un percorso di file come parametro di input e aprire il file di testo per la lettura.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. Le `Current` proprietà per entrambe le `IEnumerator(Of String)` `IEnumerator` interfacce e restituiscono l'elemento corrente dal file di testo come `String` . L'implementazione della `Current` proprietà dell' `IEnumerator` interfaccia può essere eseguita `Private` , perché è necessario esporre solo i membri dell' `IEnumerator(Of String)` interfaccia. Sostituire il codice generato Visual Basic per le `Current` proprietà con il codice seguente.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. Il `MoveNext` metodo dell' `IEnumerator` interfaccia passa all'elemento successivo nel file di testo e aggiorna il valore restituito dalla `Current` Proprietà. Se non sono presenti altri elementi da leggere, il `MoveNext` metodo restituisce `False` ; in caso contrario, il `MoveNext` metodo restituisce `True` . Aggiungere il codice seguente al metodo `MoveNext` .

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. Il `Reset` metodo dell' `IEnumerator` interfaccia indirizza l'iteratore in modo che punti all'inizio del file di testo e cancella il valore dell'elemento corrente. Aggiungere il codice seguente al metodo `Reset` .

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. Il `Dispose` metodo dell' `IEnumerator` interfaccia garantisce che tutte le risorse non gestite vengano rilasciate prima che l'iteratore venga eliminato definitivamente. L'handle di file usato dall' `StreamReader` oggetto è una risorsa non gestita e deve essere chiuso prima che venga distrutta l'istanza dell'iteratore. Sostituire il codice generato Visual Basic per il `Dispose` metodo con il codice seguente.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>Uso dell'iteratore di esempio

 È possibile usare una classe Enumerable nel codice insieme a strutture di controllo che richiedono un oggetto che implementa `IEnumerable` , ad esempio un `For Next` ciclo o una query LINQ. Nell'esempio seguente viene illustrato l'oggetto `StreamReaderEnumerable` in una query LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../linq/introduction-to-linq.md)
- [Flusso di controllo](index.md)
- [Strutture di ciclo](loop-structures.md)
- [Istruzione For Each...Next](../../../language-reference/statements/for-each-next-statement.md)

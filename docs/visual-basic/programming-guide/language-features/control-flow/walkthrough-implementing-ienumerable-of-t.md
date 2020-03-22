---
title: Implementazione di IEnumerableImplementing IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 4151a680050f234d450d8de5e67a767c54e8df68
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266911"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Procedura dettagliata: implementazione di IEnumerable(Of T) in Visual Basic
L'interfaccia <xref:System.Collections.Generic.IEnumerable%601> viene implementata dalle classi che possono restituire una sequenza di valori un elemento alla volta. Il vantaggio di restituire i dati un elemento alla volta è che non è necessario caricare il set completo di dati in memoria per utilizzarlo. È sufficiente utilizzare memoria sufficiente per caricare un singolo elemento dai dati. Le classi `IEnumerable(T)` che implementano `For Each` l'interfaccia possono essere utilizzate con cicli o query LINQ.  
  
 Si consideri, ad esempio, un'applicazione che deve leggere un file di testo di grandi dimensioni e restituire ogni riga dal file che corrisponde a criteri di ricerca specifici. L'applicazione utilizza una query LINQ per restituire righe dal file che corrispondono ai criteri specificati. Per eseguire una query sul contenuto del file utilizzando una query LINQ, l'applicazione potrebbe caricare il contenuto del file in una matrice o in una raccolta. Tuttavia, il caricamento dell'intero file in una matrice o raccolta consumerebbe molta più memoria di quanto richiesto. La query LINQ potrebbe invece eseguire una query sul contenuto del file utilizzando una classe enumerabile, restituendo solo i valori che corrispondono ai criteri di ricerca. Le query che restituiscono solo alcuni valori corrispondenti consumano molta meno memoria.  
  
 È possibile creare una <xref:System.Collections.Generic.IEnumerable%601> classe che implementa l'interfaccia per esporre i dati di origine come dati enumerabili. La classe che `IEnumerable(T)` implementa l'interfaccia richiederà un'altra classe che implementa l'interfaccia <xref:System.Collections.Generic.IEnumerator%601> per scorrere i dati di origine. Queste due classi consentono di restituire gli elementi di dati in sequenza come un tipo specifico.  
  
 In questa procedura dettagliata verrà creata `IEnumerable(Of String)` una classe che implementa `IEnumerator(Of String)` l'interfaccia e una classe che implementa l'interfaccia per leggere un file di testo una riga alla volta.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Creazione della classe EnumerableCreating the Enumerable Class  
  
**Creare il progetto di classe enumerabileCreate the enumerable class project**

1. In Visual Basic scegliere **Nuovo** dal menu **File,** quindi fare clic su **Progetto**.

1. Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**. Selezionare **Libreria di classi** nel riquadro **Modelli**. Nella casella **Nome** digitare `StreamReaderEnumerable`, quindi fare clic su **OK**. Viene visualizzato il nuovo progetto.

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul file Class1.vb e **scegliere Rinomina**. Rinominare il file `StreamReaderEnumerable.vb` e premere INVIO. Modificando il nome del file, anche la classe verrà rinominata `StreamReaderEnumerable`. Questa classe implementerà l'interfaccia `IEnumerable(Of String)`.

1. Fare clic con il pulsante destro del mouse sul progetto StreamReaderEnumerable , **scegliere Aggiungi**, quindi fare clic su **Nuovo elemento**. Selezionare il modello **Classe.Select** the Class template. Digitare `StreamReaderEnumerator.vb` nella casella **Nome** e quindi fare clic su **OK**.

 La prima classe in questo progetto è `IEnumerable(Of String)` la classe enumerabile e implementerà l'interfaccia. Questa interfaccia generica implementa l'interfaccia <xref:System.Collections.IEnumerable> e garantisce che `String`i consumer di questa classe possano accedere ai valori tipizzati come .  
  
**Aggiungere il codice per implementare IEnumerableAdd the code to implement IEnumerable**

1. Aprire il file StreamReaderEnumerable.vb.

2. Nella riga `Public Class StreamReaderEnumerable`successiva digitare quanto segue e premere INVIO.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic popola automaticamente la classe con `IEnumerable(Of String)` i membri richiesti dall'interfaccia.
  
3. Questa classe enumerabile leggerà le righe da un file di testo una riga alla volta. Aggiungere il codice seguente alla classe per esporre un costruttore pubblico che accetta un percorso di file come parametro di input.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. L'implementazione <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> del `IEnumerable(Of String)` metodo dell'interfaccia restituirà `StreamReaderEnumerator` una nuova istanza della classe. L'implementazione `GetEnumerator` del `IEnumerable` metodo dell'interfaccia può essere effettuata, `Private` `IEnumerable(Of String)` perché è necessario esporre solo i membri dell'interfaccia. Sostituire il codice generato da `GetEnumerator` Visual Basic per i metodi con il codice seguente.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**Aggiungere il codice per implementare IEnumerator**

1. Aprire il file StreamReaderEnumerator.vb.

2. Nella riga `Public Class StreamReaderEnumerator`successiva digitare quanto segue e premere INVIO.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic popola automaticamente la classe con `IEnumerator(Of String)` i membri richiesti dall'interfaccia.

3. La classe enumeratore apre il file di testo ed esegue l'I/O del file per leggere le righe dal file. Aggiungere il codice seguente alla classe per esporre un costruttore pubblico che accetta un percorso di file come parametro di input e aprire il file di testo per la lettura.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. Le `Current` proprietà per `IEnumerator(Of String)` `IEnumerator` le interfacce e restituiscono l'elemento corrente dal file di testo come `String`file . L'implementazione `Current` della `IEnumerator` proprietà dell'interfaccia può essere effettuata, `Private` `IEnumerator(Of String)` perché è necessario esporre solo i membri dell'interfaccia. Sostituire il codice generato da `Current` Visual Basic per le proprietà con il codice seguente.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. Il `MoveNext` metodo `IEnumerator` dell'interfaccia passa all'elemento successivo nel file di testo e `Current` aggiorna il valore restituito dalla proprietà . Se non sono presenti altri `MoveNext` elementi `False`da leggere, il metodo restituisce ; in `MoveNext` caso `True`contrario, il metodo restituisce . Aggiungere il codice seguente al metodo `MoveNext` .

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. Il `Reset` metodo `IEnumerator` dell'interfaccia indica all'iteratore di puntare all'inizio del file di testo e cancella il valore dell'elemento corrente. Aggiungere il codice seguente al metodo `Reset` .

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. Il `Dispose` metodo `IEnumerator` dell'interfaccia garantisce che tutte le risorse non gestite vengano rilasciate prima che l'iteratore venga eliminato. L'handle di file `StreamReader` utilizzato dall'oggetto è una risorsa non gestita e deve essere chiuso prima che l'istanza dell'iteratore venga eliminata. Sostituire il codice generato da `Dispose` Visual Basic per il metodo con il codice seguente.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>Utilizzo dell'iteratore di esempioUsing the Sample Iterator

 È possibile utilizzare una classe enumerabile nel codice insieme `IEnumerable`a strutture `For Next` di controllo che richiedono un oggetto che implementa , ad esempio un ciclo o una query LINQ. Nell'esempio seguente `StreamReaderEnumerable` viene illustrato l'oggetto in una query LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Istruzione For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

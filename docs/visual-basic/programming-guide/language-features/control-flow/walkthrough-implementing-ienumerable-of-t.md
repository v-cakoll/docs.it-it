---
title: Implementazione di IEnumerable in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4645153f9c830bc96b7ec55367f46f09098eb78d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Procedura dettagliata: implementazione di IEnumerable(Of T) in Visual Basic
Il <xref:System.Collections.Generic.IEnumerable%601> interfaccia è implementata da classi che possono restituire una sequenza di valori un elemento alla volta. Il vantaggio di restituzione di dati è di un elemento in un momento non è necessario caricare il set completo di dati in memoria per utilizzarlo. È necessario utilizzare solo memoria sufficiente per caricare un singolo elemento dai dati. Le classi che implementano il `IEnumerable(T)` interfaccia può essere utilizzata con `For Each` cicli o le query LINQ.  
  
 Ad esempio, si consideri un'applicazione che è necessario leggere un file di testo di grandi dimensioni e restituire ogni riga del file che corrisponde ai criteri di ricerca particolare. L'applicazione utilizza una query LINQ per restituire le righe dal file che corrispondono ai criteri specificati. Per eseguire una query il contenuto del file tramite una query LINQ, l'applicazione è stato possibile caricare il contenuto del file in una matrice o una raccolta. Tuttavia, il caricamento dell'intero file in una matrice o raccolta richiederebbe molta più memoria rispetto a quelli necessari. La query LINQ potrebbe invece eseguire una query il contenuto del file utilizzando una classe enumerabile, restituendo solo i valori che corrispondono ai criteri di ricerca. Le query che restituiscono solo alcuni valori corrispondenti comporta l'utilizzo di memoria molto inferiore.  
  
 È possibile creare una classe che implementa il <xref:System.Collections.Generic.IEnumerable%601> interfaccia da esporre i dati di origine dati enumerabili. La classe che implementa il `IEnumerable(T)` interfaccia richiederà un'altra classe che implementa il <xref:System.Collections.Generic.IEnumerator%601> interfaccia per scorrere i dati di origine. Queste due classi consentono di restituire gli elementi di dati in sequenza come un tipo specifico.  
  
 In questa procedura dettagliata, si creerà una classe che implementa il `IEnumerable(Of String)` interfaccia e una classe che implementa il `IEnumerator(Of String)` interfaccia per leggere un file di testo di una riga alla volta.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Creazione della classe enumerabile  
  
|Per creare il progetto di classe enumerabile|  
|---|  
|1.  In Visual Basic nel **File** dal menu **New** e quindi fare clic su **progetto**.<br />2.  Nel riquadro **Tipi di progetto** della finestra di dialogo **Nuovo progetto** verificare che sia selezionata l'opzione **Windows**. Selezionare **Libreria di classi** nel riquadro **Modelli**. Nella casella **Nome** digitare `StreamReaderEnumerable` e quindi fare clic su **OK**. Viene visualizzato il nuovo progetto.<br />3.  In **Esplora**, il file Class1. vb e fare clic su **rinominare**. Rinominare il file `StreamReaderEnumerable.vb` e premere INVIO. Modificando il nome del file, anche la classe verrà rinominata `StreamReaderEnumerable`. Questa classe implementerà l'interfaccia `IEnumerable(Of String)`.<br />4.  Fare clic sul progetto StreamReaderEnumerable, scegliere **Aggiungi**, quindi fare clic su **nuovo elemento**. Selezionare il **classe** modello. Nel **nome** digitare `StreamReaderEnumerator.vb` e fare clic su **OK**.|  
  
 La prima classe nel progetto è la classe enumerabile che implementerà il `IEnumerable(Of String)` interfaccia. Implementa l'interfaccia generica di <xref:System.Collections.IEnumerable> interfaccia e assicura che gli utenti di questa classe possono accedere a valori tipizzati come `String`.  
  
|Per aggiungere il codice per implementare IEnumerable|  
|---|  
|1.  Aprire il file StreamReaderEnumerable.<br />2.  Nella riga dopo `Public Class StreamReaderEnumerable`, digitare il comando seguente e premere INVIO.<br />     [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     Visual Basic popola automaticamente la classe con i membri necessari per il `IEnumerable(Of String)` interfaccia.<br />3.  Questa classe enumerabile leggerà righe da un file di testo di una riga alla volta. Aggiungere il codice seguente alla classe per esporre un costruttore pubblico che accetta un percorso di file come parametro di input.<br />     [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.  L'implementazione del <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> metodo il `IEnumerable(Of String)` interfaccia restituirà una nuova istanza della `StreamReaderEnumerator` classe. L'implementazione del `GetEnumerator` metodo il `IEnumerable` interfaccia può essere reso `Private`, in quanto è necessario esporre solo i membri del `IEnumerable(Of String)` interfaccia. Sostituire il codice Visual Basic generato per il `GetEnumerator` metodi con il codice seguente.<br />     [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
|Per aggiungere il codice per implementare IEnumerator|  
|---|  
|1.  Aprire il file StreamReaderEnumerator.<br />2.  Nella riga dopo `Public Class StreamReaderEnumerator`, digitare il comando seguente e premere INVIO.<br />     [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     Visual Basic popola automaticamente la classe con i membri necessari per il `IEnumerator(Of String)` interfaccia.<br />3.  La classe dell'enumeratore apre il file di testo ed esegue il file dei / o per leggere le righe dal file. Aggiungere il codice seguente alla classe per esporre un costruttore pubblico che accetta un percorso di file come parametro di input e aprire il file di testo per la lettura.<br />     [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.  Il `Current` proprietà sia per il `IEnumerator(Of String)` e `IEnumerator` interfacce restituiscono l'elemento corrente dal file di testo come una `String`. L'implementazione del `Current` proprietà del `IEnumerator` interfaccia può essere reso `Private`, poiché è necessario esporre solo i membri del `IEnumerator(Of String)` interfaccia. Sostituire il codice Visual Basic generato per il `Current` proprietà con il codice seguente.<br />     [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.  Il `MoveNext` metodo il `IEnumerator` interfaccia passa all'elemento successivo nel file di testo e aggiorna il valore restituito dal `Current` proprietà. Se sono presenti più elementi da leggere, il `MoveNext` restituisce `False`; in caso contrario il `MoveNext` restituisce `True`. Aggiungere al metodo `MoveNext` il seguente codice.<br />     [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.  Il `Reset` metodo il `IEnumerator` interfaccia indirizza l'iteratore in modo da puntare all'inizio del file di testo e cancella il valore dell'elemento corrente. Aggiungere al metodo `Reset` il seguente codice.<br />     [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.  Il `Dispose` metodo il `IEnumerator` interfaccia garantisce che tutte le risorse non gestite vengono rilasciate prima che l'iteratore venga eliminato. L'handle di file che viene utilizzato il `StreamReader` oggetto è una risorsa non gestita e deve essere chiuso prima che l'istanza dell'iteratore venga eliminato. Sostituire il codice Visual Basic generato per il `Dispose` (metodo) con il codice seguente.<br />     [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## <a name="using-the-sample-iterator"></a>Utilizzo dell'iteratore di esempio  
 È possibile utilizzare una classe enumerabile nel codice insieme alle strutture di controllo che richiedono un oggetto che implementa `IEnumerable`, ad esempio un `For Next` ciclo o una query LINQ. Nell'esempio seguente il `StreamReaderEnumerable` in una query LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Flusso di controllo](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Strutture di ciclo](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Istruzione For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

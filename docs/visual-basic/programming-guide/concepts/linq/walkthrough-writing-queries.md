---
title: Scrittura di query
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 6d2e472cc996c42aa091ed95c6954d0879c98372
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636757"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Procedura dettagliata: Scrittura delle query in Visual Basic

In questa procedura dettagliata viene illustrato come è possibile utilizzare le funzionalità del linguaggio Visual Basic per scrivere espressioni di query LINQ (Language-Integrated Query). Nella procedura dettagliata viene illustrato come creare query in un elenco di oggetti Student, come eseguire le query e come modificarli. Le query includono diverse funzionalità, inclusi gli inizializzatori di oggetto, l'inferenza del tipo locale e i tipi anonimi.

Al termine di questa procedura dettagliata, si sarà pronti a passare agli esempi e alla documentazione per il provider LINQ specifico a cui si è interessati. I provider LINQ includono [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet e [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].

## <a name="create-a-project"></a>Creare un progetto

### <a name="to-create-a-console-application-project"></a>Per creare un progetto di applicazione console

1. Avviare Visual Studio.

2. Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**.

3. Nell'elenco **modelli installati** fare clic su **Visual Basic**.

4. Nell'elenco dei tipi di progetto fare clic su **applicazione console**. Nella casella **nome** Digitare un nome per il progetto, quindi fare clic su **OK**.

    Viene creato un progetto. Per impostazione predefinita, contiene un riferimento a System. Core. dll. Inoltre, l'elenco degli **spazi dei nomi importati** nella [pagina riferimenti, progettazione progetti (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) include lo spazio dei nomi <xref:System.Linq?displayProperty=nameWithType>.

5. Nella [pagina compilazione, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), assicurarsi che l' **opzione deduce** sia impostata **su on**.

## <a name="add-an-in-memory-data-source"></a>Aggiungere un'origine dati in memoria

L'origine dati per le query in questa procedura dettagliata è un elenco di oggetti `Student`. Ogni oggetto `Student` contiene un nome, un cognome, un anno di classe e un rango accademico nel corpo degli studenti.

### <a name="to-add-the-data-source"></a>Per aggiungere l'origine dati

- Definire una classe `Student` e creare un elenco di istanze della classe.

  > [!IMPORTANT]
  > Il codice necessario per definire la classe `Student` e creare l'elenco usato negli esempi di procedura dettagliata è disponibile in [procedura: creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). È possibile copiarlo da questa posizione e incollarlo nel progetto. Il nuovo codice sostituisce il codice visualizzato quando è stato creato il progetto.

### <a name="to-add-a-new-student-to-the-students-list"></a>Per aggiungere un nuovo studente all'elenco degli studenti

- Seguire il modello nel metodo `getStudents` per aggiungere un'altra istanza della classe `Student` all'elenco. Aggiungendo lo studente si introdurranno gli inizializzatori di oggetto. Per altre informazioni, vedere [inizializzatori di oggetto: tipi denominati e anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).

## <a name="create-a-query"></a>Creare una query

Quando viene eseguita, la query aggiunta in questa sezione produce un elenco degli studenti il cui rango accademico li inserisce nei primi dieci. Poiché la query seleziona ogni volta l'oggetto `Student` completo, il tipo del risultato della query viene `IEnumerable(Of Student)`. Tuttavia, il tipo della query non viene in genere specificato nelle definizioni di query. Al contrario, il compilatore usa l'inferenza del tipo locale per determinare il tipo. Per altre informazioni, vedere [inferenza dei tipi locali](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md). La variabile di intervallo della query, `currentStudent`, funge da riferimento a ogni istanza di `Student` nell'origine `students`che fornisce l'accesso alle proprietà di ogni oggetto `students`.

### <a name="to-create-a-simple-query"></a>Per creare una query semplice

1. Individuare la posizione nel metodo `Main` del progetto contrassegnato come segue:

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    Copiare il codice seguente e incollarlo in.

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. Posizionare il puntatore del mouse su `studentQuery` nel codice per verificare che il tipo assegnato dal compilatore sia `IEnumerable(Of Student)`.

## <a name="run-the-query"></a>Eseguire la query

La variabile `studentQuery` contiene la definizione della query, non i risultati dell'esecuzione della query. Un meccanismo tipico per l'esecuzione di una query è un ciclo `For Each`. È possibile accedere a ogni elemento nella sequenza restituita tramite la variabile di iterazione del ciclo. Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura della prima query LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).

### <a name="to-run-the-query"></a>Per eseguire la query

1. Aggiungere il seguente ciclo di `For Each` sotto la query nel progetto.

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. Posizionare il puntatore del mouse sulla variabile di controllo del ciclo `studentRecord` per visualizzarne il tipo di dati. Il tipo di `studentRecord` viene dedotto come `Student`, perché `studentQuery` restituisce una raccolta di istanze di `Student`.

3. Compilare ed eseguire l'applicazione premendo CTRL + F5. Si notino i risultati nella finestra della console.

## <a name="modify-the-query"></a>Modificare la query

È più semplice analizzare i risultati della query se sono in un ordine specificato. È possibile ordinare la sequenza restituita in base a qualsiasi campo disponibile.

### <a name="to-order-the-results"></a>Per ordinare i risultati

1. Aggiungere la seguente clausola `Order By` tra l'istruzione `Where` e l'istruzione `Select` della query. Con la clausola `Order By` i risultati vengono ordinati in ordine alfabetico da a a Z, in base al cognome di ogni studente.

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. Per eseguire l'ordinamento in base al cognome e quindi al nome, aggiungere entrambi i campi alla query:

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    È anche possibile specificare `Descending` per ordinare da Z a A.

3. Compilare ed eseguire l'applicazione premendo CTRL + F5. Si notino i risultati nella finestra della console.

### <a name="to-introduce-a-local-identifier"></a>Per introdurre un identificatore locale

1. Aggiungere il codice in questa sezione per introdurre un identificatore locale nell'espressione di query. L'identificatore locale conterrà un risultato intermedio. Nell'esempio seguente `name` è un identificatore che include una concatenazione del nome e del cognome dello studente. Un identificatore locale può essere usato per praticità oppure può migliorare le prestazioni archiviando i risultati di un'espressione che altrimenti verrebbe calcolata più volte.

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. Compilare ed eseguire l'applicazione premendo CTRL + F5. Si notino i risultati nella finestra della console.

### <a name="to-project-one-field-in-the-select-clause"></a>Per proiettare un campo nella clausola SELECT

1. Aggiungere la query e il ciclo `For Each` da questa sezione per creare una query che produce una sequenza i cui elementi differiscono dagli elementi nell'origine. Nell'esempio seguente l'origine è una raccolta di oggetti `Student`, ma viene restituito solo un membro di ogni oggetto: il nome degli studenti il cui cognome è Garcia. Poiché `currentStudent.First` è una stringa, il tipo di dati della sequenza restituita da `studentQuery3` è `IEnumerable(Of String)`, una sequenza di stringhe. Come negli esempi precedenti, l'assegnazione di un tipo di dati per `studentQuery3` viene lasciata al compilatore per determinare utilizzando l'inferenza del tipo locale.

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. Posizionare il puntatore del mouse su `studentQuery3` nel codice per verificare che il tipo assegnato sia `IEnumerable(Of String)`.

3. Compilare ed eseguire l'applicazione premendo CTRL + F5. Si notino i risultati nella finestra della console.

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Per creare un tipo anonimo nella clausola SELECT

1. Aggiungere il codice da questa sezione per vedere come vengono usati i tipi anonimi nelle query. Vengono usati nelle query quando si desidera restituire più campi dall'origine dati anziché record completi (`currentStudent` record negli esempi precedenti) o campi singoli (`First` nella sezione precedente). Anziché definire un nuovo tipo denominato che contiene i campi che si desidera includere nel risultato, è necessario specificare i campi nella clausola `Select` e il compilatore crea un tipo anonimo con tali campi come proprietà. Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

    Nell'esempio seguente viene creata una query che restituisce il nome e il rango degli anziani il cui rango accademico è compreso tra 1 e 10, in ordine di rango accademico. In questo esempio, il tipo di `studentQuery4` deve essere dedotto perché la clausola `Select` restituisce un'istanza di un tipo anonimo e un tipo anonimo non ha un nome utilizzabile.

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. Compilare ed eseguire l'applicazione premendo CTRL + F5. Si notino i risultati nella finestra della console.

## <a name="additional-examples"></a>Esempi aggiuntivi

A questo punto, dopo aver compreso le nozioni di base, di seguito è riportato un elenco di esempi aggiuntivi per illustrare la flessibilità e la potenza delle query LINQ. Ogni esempio è preceduto da una breve descrizione dell'operazione. Posizionare il puntatore del mouse sulla variabile dei risultati della query per ogni query per visualizzare il tipo dedotto. Usare un ciclo `For Each` per produrre i risultati.

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a>Informazioni aggiuntive

Dopo aver acquisito familiarità con i concetti di base relativi all'utilizzo delle query, è possibile leggere la documentazione e gli esempi relativi al tipo specifico di provider LINQ a cui si è interessati:

- [LINQ to Objects](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)

- [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)

- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)

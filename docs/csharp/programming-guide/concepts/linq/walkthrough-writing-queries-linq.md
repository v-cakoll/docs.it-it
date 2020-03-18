---
title: 'Procedura dettagliata: scrittura di query in C# (LINQ)'
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], walkthroughs
- LINQ [C#], writing queries
- queries [LINQ in C#], writing
- writing LINQ queries
ms.assetid: 2962a610-419a-4276-9ec8-4b7f2af0c081
ms.openlocfilehash: f2135c6c3649ba2fc87e3b49770439688a58269b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73418060"
---
# <a name="walkthrough-writing-queries-in-c-linq"></a>Procedura dettagliata: scrittura di query in C# (LINQ)
Questa procedura dettagliata illustra le funzionalità del linguaggio C# utilizzate per scrivere espressioni di query LINQ.  
  
## <a name="create-a-c-project"></a>Creare un progetto C#  
  
> [!NOTE]
> Le istruzioni seguenti riguardano Visual Studio. Se si usa un ambiente di sviluppo diverso, creare un progetto console con un riferimento a System.Core.dll e una direttiva `using` per lo spazio dei nomi <xref:System.Linq?displayProperty=nameWithType>.  
  
#### <a name="to-create-a-project-in-visual-studio"></a>Per creare un progetto in Visual Studio  
  
1. Avviare Visual Studio.  
  
2. Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.  
  
     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
3. Espandere **Installati**, **Modelli** e **Visual C#** e scegliere **Applicazione console**.  
  
4. Nella casella di testo **Nome** immettere un nome diverso o accettare il nome predefinito e quindi scegliere il pulsante **OK**.  
  
     Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.  
  
5. Si noti che il progetto contiene un riferimento a System.Core.dll e una direttiva `using` per lo spazio dei nomi <xref:System.Linq?displayProperty=nameWithType>.  
  
## <a name="create-an-in-memory-data-source"></a>Creare un'origine dati in memoria  
 L'origine dati per le query è un semplice elenco di oggetti `Student`. Ogni record `Student` ha un nome, un cognome e una matrice di interi che rappresenta i punteggi dei test nella classe. Copiare questo codice nel progetto. Tenere presente le seguenti caratteristiche:  
  
- La classe `Student` consiste di proprietà implementate automaticamente.  
  
- Ogni studente nell'elenco viene inizializzato con un inizializzatore di oggetto.  
  
- L'elenco stesso viene inizializzato con un inizializzatore di raccolta.  
  
 Questa intera struttura di dati sarà inizializzata e istanziata senza chiamate esplicite ad alcun costruttore o accesso a membri espliciti. Per altre informazioni su queste nuove funzionalità, vedere [Proprietà implementate automaticamente](../../classes-and-structs/auto-implemented-properties.md) e [Inizializzatori di oggetto e di raccolta](../../classes-and-structs/object-and-collection-initializers.md).  
  
#### <a name="to-add-the-data-source"></a>Per aggiungere l'origine dati  
  
- Aggiungere la classe `Student` e l'elenco di studenti inizializzato alla classe `Program` nel progetto.  
  
     [!code-csharp[CsLinqGettingStarted#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#11)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a>Per aggiungere un nuovo studente all'elenco degli studenti  
  
1. Aggiungere un nuovo `Student` all'elenco `Students` e usare un nome e punteggi di test di propria scelta. Provare a digitare tutte le nuove informazioni sugli studenti per imparare meglio la sintassi per l'inizializzatore di oggetto.  
  
## <a name="create-the-query"></a>Creare la query  
  
#### <a name="to-create-a-simple-query"></a>Per creare una query semplice  
  
- Nel metodo `Main` dell'applicazione creare una query semplice che, quando viene eseguita, genera un elenco di tutti gli studenti il cui punteggio del primo test è maggiore di 90. Si noti che, poiché è selezionato l'intero oggetto `Student`, il tipo di query è `IEnumerable<Student>`. Il codice potrebbe usare anche la tipizzazione implicita mediante la parola chiave [var](../../../language-reference/keywords/var.md), ma si usa la tipizzazione esplicita per illustrare dettagliatamente i risultati. Per ulteriori informazioni `var`sulle variabili [locali tipizzate in modo implicito, vedere Variabili locali tipizzate in modo implicito.](../../classes-and-structs/implicitly-typed-local-variables.md)  
  
     Si noti anche che la variabile di intervallo della query, `student`, funge da riferimento a ogni `Student` nell'origine, fornendo l'accesso di membro per ogni oggetto.  
  
 [!code-csharp[CsLINQGettingStarted#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#12)]  
  
## <a name="execute-the-query"></a>Eseguire la query  
  
#### <a name="to-execute-the-query"></a>Per eseguire la query  
  
1. Scrivere ora il ciclo `foreach` che avvia l'esecuzione della query. Tenere presente quanto segue in merito al codice:  
  
    - A ogni elemento della sequenza restituita si accede tramite la variabile di iterazione nel ciclo `foreach`.  
  
    - Il tipo di questa variabile è `Student` e il tipo della variabile di query è compatibile, `IEnumerable<Student>`.  
  
2. Dopo aver aggiunto questo codice, compilare ed eseguire l'applicazione per vedere i risultati nella finestra **Console**.  
  
 [!code-csharp[CsLINQGettingStarted#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#13)]  
  
#### <a name="to-add-another-filter-condition"></a>Per aggiungere un'altra condizione di filtro  
  
1. È possibile combinare più condizioni booleane nel clausola `where` per perfezionare ulteriormente la query. Il codice seguente aggiunge una condizione in modo che la query restituisca gli studenti il cui primo punteggio era maggiore di 90 e il cui ultimo punteggio era minore di 80. La clausola `where` dovrebbe essere simile al codice seguente.  
  
    ```csharp
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     Per ulteriori informazioni, vedere [clausola where](../../../language-reference/keywords/where-clause.md).  
  
## <a name="modify-the-query"></a>Modificare la query  
  
#### <a name="to-order-the-results"></a>Per ordinare i risultati  
  
1. Sarà più semplice analizzare i risultati se si trovano nello stesso tipo di ordine. È possibile ordinare la sequenza restituita in base a qualsiasi campo accessibile negli elementi di origine. Ad esempio, la clausola `orderby` seguente dispone i risultati in ordine alfabetico dalla A alla Z in base al cognome dello studente. Aggiungere la seguente clausola `orderby` alla query, subito dopo l'istruzione `where` e prima dell'istruzione `select`:  
  
    ```csharp
    orderby student.Last ascending  
    ```  
  
2. Modificare ora la clausola `orderby` in modo che disponga i risultati in ordine decrescente in base al punteggio del primo test, dal punteggio più alto al più basso.  
  
    ```csharp
    orderby student.Scores[0] descending  
    ```  
  
3. Modificare la stringa di formato `WriteLine` in modo che sia possibile vedere i punteggi:  
  
    ```csharp
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     Per altre informazioni, vedere [Clausola orderby](../../../language-reference/keywords/orderby-clause.md).  
  
#### <a name="to-group-the-results"></a>Per raggruppare i risultati  
  
1. Il raggruppamento è una potente funzionalità delle espressioni di query. Una query con una clausola group genera una sequenza di gruppi e ogni gruppo contiene un `Key` e una sequenza costituita da tutti i membri di quel gruppo. La nuova query riportata di seguito raggruppa gli studenti usando la prima lettera del cognome come chiave.  
  
     [!code-csharp[CsLINQGettingStarted#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#14)]  
  
2. Si noti che il tipo della query è stato modificato. Ora genera una sequenza di gruppi che hanno il tipo `char` come chiave e una sequenza di oggetti `Student`. Siccome il tipo della query è cambiato, il codice seguente cambia anche il ciclo di esecuzione `foreach`:  
  
     [!code-csharp[CsLINQGettingStarted#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#15)]  
  
3. Eseguire l'applicazione e visualizzare i risultati nella finestra **Console**.  
  
     Per altre informazioni, vedere [Clausola group](../../../language-reference/keywords/group-clause.md).  
  
#### <a name="to-make-the-variables-implicitly-typed"></a>Per ottenere che le variabili siano tipizzate in modo implicito  
  
1. Codificare in modo esplicito `IEnumerables` di `IGroupings` può risultare noioso. È possibile scrivere la stessa query e ciclo `foreach` in modo molto più semplice usando `var`. La parola chiave `var` non cambia il tipo degli oggetti ma si limita a istruire il compilatore a dedurre i tipi. Cambiare il tipo di `studentQuery` e la variabile di iterazione `group` in `var` ed eseguire di nuovo la query. Si noti che nel ciclo `foreach` interno, la variabile di iterazione è ancora tipizzata come `Student` e la query funziona esattamente come prima. Cambiare la variabile di iterazione `s` in `var` ed eseguire di nuovo la query. Si noti che si ottengono esattamente gli stessi risultati.  
  
     [!code-csharp[CsLINQGettingStarted#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#16)]  
  
     Per altre informazioni su [var](../../../language-reference/keywords/var.md), vedere [Variabili locali tipizzate in modo implicito](../../classes-and-structs/implicitly-typed-local-variables.md).  
  
#### <a name="to-order-the-groups-by-their-key-value"></a>Per ordinare i gruppi in base al valore della chiave  
  
1. Quando si esegue la query precedente, si nota che i gruppi non sono in ordine alfabetico. Per modificare questa impostazione è necessario fornire una clausola `orderby` dopo la clausola `group`. Ma per usare una clausola `orderby`, è necessario un identificatore che funge da riferimento ai gruppi creati per la clausola `group`. L'identificatore viene fornito usando la parola chiave `into`, come segue:  
  
     [!code-csharp[csLINQGettingStarted#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#17)]  
  
     Quando si esegue questa query si può notare che i gruppi vengono disposti in ordine alfabetico.  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a>Per introdurre un identificatore usando let  
  
1. È possibile usare la parola chiave `let` per introdurre un identificatore per qualsiasi risultato di espressione nell'espressione di query. Questo identificatore può essere comodo, come nell'esempio seguente, oppure può migliorare le prestazioni archiviando i risultati di un'espressione in modo che non debba essere calcolata più volte.  
  
     [!code-csharp[csLINQGettingStarted#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#18)]  
  
     Per altre informazioni, vedere [Clausola let](../../../language-reference/keywords/let-clause.md).  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a>Per usare la sintassi del metodo in un'espressione di query  
  
1. Come descritto in [Sintassi di query e sintassi di metodi in LINQ](./query-syntax-and-method-syntax-in-linq.md), alcune operazioni di query possono essere espresse solo usando la sintassi dei metodi. Il codice seguente calcola il punteggio totale per ogni `Student` nella sequenza di origine e quindi chiama il metodo `Average()` sui risultati della query per calcolare il punteggio medio della classe.
  
     [!code-csharp[csLINQGettingStarted#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#19)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a>Per eseguire trasformazioni o proiezioni nella clausola select  
  
1. Un compito molto comune per una query è generare una sequenza i cui elementi differiscono da quelli delle sequenze di origine. Eliminare o impostare come commento il ciclo di query ed esecuzione precedente e sostituirlo con il codice seguente. Si noti che la query restituisce una sequenza di stringhe (non `Students`) e questo si riflette nel ciclo `foreach`.  
  
     [!code-csharp[csLINQGettingStarted#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#20)]  
  
2. Il codice precedente di questa procedura dettagliata indica che il punteggio medio della classe è pari a circa 334. Per produrre una sequenza di `Students` il cui punteggio totale sia maggiore della media della classe, insieme al loro `Student ID`, è possibile usare un tipo anonimo nell'istruzione `select`:  
  
     [!code-csharp[csLINQGettingStarted#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#21)]  
  
## <a name="next-steps"></a>Passaggi successivi  
 Dopo aver acquisito familiarità con i fondamenti dell'uso delle query in C#, è possibile leggere la documentazione e vedere gli esempi per il tipo specifico di provider LINQ a cui si è interessati:  
  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [LINQ to XML (C#)](./linq-to-xml-overview.md)  
  
 [LINQ to Objects (C#)](./linq-to-objects.md)  
  
## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query) (C#)](./index.md)
- [Espressioni di query LINQLINQ Query Expressions](../../../linq/index.md)

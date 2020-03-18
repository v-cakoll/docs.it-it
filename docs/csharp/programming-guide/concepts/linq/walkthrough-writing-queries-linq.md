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
# <a name="walkthrough-writing-queries-in-c-linq"></a><span data-ttu-id="b86f5-102">Procedura dettagliata: scrittura di query in C# (LINQ)</span><span class="sxs-lookup"><span data-stu-id="b86f5-102">Walkthrough: Writing Queries in C# (LINQ)</span></span>
<span data-ttu-id="b86f5-103">Questa procedura dettagliata illustra le funzionalità del linguaggio C# utilizzate per scrivere espressioni di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="b86f5-103">This walkthrough demonstrates the C# language features that are used to write LINQ query expressions.</span></span>  
  
## <a name="create-a-c-project"></a><span data-ttu-id="b86f5-104">Creare un progetto C#</span><span class="sxs-lookup"><span data-stu-id="b86f5-104">Create a C# Project</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b86f5-105">Le istruzioni seguenti riguardano Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b86f5-105">The following instructions are for Visual Studio.</span></span> <span data-ttu-id="b86f5-106">Se si usa un ambiente di sviluppo diverso, creare un progetto console con un riferimento a System.Core.dll e una direttiva `using` per lo spazio dei nomi <xref:System.Linq?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b86f5-106">If you are using a different development environment, create a console project with a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
#### <a name="to-create-a-project-in-visual-studio"></a><span data-ttu-id="b86f5-107">Per creare un progetto in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b86f5-107">To create a project in Visual Studio</span></span>  
  
1. <span data-ttu-id="b86f5-108">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b86f5-108">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="b86f5-109">Nella barra dei menu scegliere **File**, **Nuovo**, **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="b86f5-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="b86f5-110">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="b86f5-110">The **New Project** dialog box opens.</span></span>  
  
3. <span data-ttu-id="b86f5-111">Espandere **Installati**, **Modelli** e **Visual C#** e scegliere **Applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="b86f5-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4. <span data-ttu-id="b86f5-112">Nella casella di testo **Nome** immettere un nome diverso o accettare il nome predefinito e quindi scegliere il pulsante **OK**.</span><span class="sxs-lookup"><span data-stu-id="b86f5-112">In the **Name** text box, enter a different name or accept the default name, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="b86f5-113">Il nuovo progetto verrà visualizzato in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="b86f5-113">The new project appears in **Solution Explorer**.</span></span>  
  
5. <span data-ttu-id="b86f5-114">Si noti che il progetto contiene un riferimento a System.Core.dll e una direttiva `using` per lo spazio dei nomi <xref:System.Linq?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b86f5-114">Notice that your project has a reference to System.Core.dll and a `using` directive for the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="create-an-in-memory-data-source"></a><span data-ttu-id="b86f5-115">Creare un'origine dati in memoria</span><span class="sxs-lookup"><span data-stu-id="b86f5-115">Create an in-Memory Data Source</span></span>  
 <span data-ttu-id="b86f5-116">L'origine dati per le query è un semplice elenco di oggetti `Student`.</span><span class="sxs-lookup"><span data-stu-id="b86f5-116">The data source for the queries is a simple list of `Student` objects.</span></span> <span data-ttu-id="b86f5-117">Ogni record `Student` ha un nome, un cognome e una matrice di interi che rappresenta i punteggi dei test nella classe.</span><span class="sxs-lookup"><span data-stu-id="b86f5-117">Each `Student` record has a first name, last name, and an array of integers that represents their test scores in the class.</span></span> <span data-ttu-id="b86f5-118">Copiare questo codice nel progetto.</span><span class="sxs-lookup"><span data-stu-id="b86f5-118">Copy this code into your project.</span></span> <span data-ttu-id="b86f5-119">Tenere presente le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="b86f5-119">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="b86f5-120">La classe `Student` consiste di proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b86f5-120">The `Student` class consists of auto-implemented properties.</span></span>  
  
- <span data-ttu-id="b86f5-121">Ogni studente nell'elenco viene inizializzato con un inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="b86f5-121">Each student in the list is initialized with an object initializer.</span></span>  
  
- <span data-ttu-id="b86f5-122">L'elenco stesso viene inizializzato con un inizializzatore di raccolta.</span><span class="sxs-lookup"><span data-stu-id="b86f5-122">The list itself is initialized with a collection initializer.</span></span>  
  
 <span data-ttu-id="b86f5-123">Questa intera struttura di dati sarà inizializzata e istanziata senza chiamate esplicite ad alcun costruttore o accesso a membri espliciti.</span><span class="sxs-lookup"><span data-stu-id="b86f5-123">This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access.</span></span> <span data-ttu-id="b86f5-124">Per altre informazioni su queste nuove funzionalità, vedere [Proprietà implementate automaticamente](../../classes-and-structs/auto-implemented-properties.md) e [Inizializzatori di oggetto e di raccolta](../../classes-and-structs/object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="b86f5-124">For more information about these new features, see [Auto-Implemented Properties](../../classes-and-structs/auto-implemented-properties.md) and [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md).</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="b86f5-125">Per aggiungere l'origine dati</span><span class="sxs-lookup"><span data-stu-id="b86f5-125">To add the data source</span></span>  
  
- <span data-ttu-id="b86f5-126">Aggiungere la classe `Student` e l'elenco di studenti inizializzato alla classe `Program` nel progetto.</span><span class="sxs-lookup"><span data-stu-id="b86f5-126">Add the `Student` class and the initialized list of students to the `Program` class in your project.</span></span>  
  
     [!code-csharp[CsLinqGettingStarted#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#11)]  
  
#### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="b86f5-127">Per aggiungere un nuovo studente all'elenco degli studenti</span><span class="sxs-lookup"><span data-stu-id="b86f5-127">To add a new Student to the Students list</span></span>  
  
1. <span data-ttu-id="b86f5-128">Aggiungere un nuovo `Student` all'elenco `Students` e usare un nome e punteggi di test di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="b86f5-128">Add a new `Student` to the `Students` list and use a name and test scores of your choice.</span></span> <span data-ttu-id="b86f5-129">Provare a digitare tutte le nuove informazioni sugli studenti per imparare meglio la sintassi per l'inizializzatore di oggetto.</span><span class="sxs-lookup"><span data-stu-id="b86f5-129">Try typing all the new student information in order to better learn the syntax for the object initializer.</span></span>  
  
## <a name="create-the-query"></a><span data-ttu-id="b86f5-130">Creare la query</span><span class="sxs-lookup"><span data-stu-id="b86f5-130">Create the Query</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="b86f5-131">Per creare una query semplice</span><span class="sxs-lookup"><span data-stu-id="b86f5-131">To create a simple query</span></span>  
  
- <span data-ttu-id="b86f5-132">Nel metodo `Main` dell'applicazione creare una query semplice che, quando viene eseguita, genera un elenco di tutti gli studenti il cui punteggio del primo test è maggiore di 90.</span><span class="sxs-lookup"><span data-stu-id="b86f5-132">In the application's `Main` method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90.</span></span> <span data-ttu-id="b86f5-133">Si noti che, poiché è selezionato l'intero oggetto `Student`, il tipo di query è `IEnumerable<Student>`.</span><span class="sxs-lookup"><span data-stu-id="b86f5-133">Note that because the whole `Student` object is selected, the type of the query is `IEnumerable<Student>`.</span></span> <span data-ttu-id="b86f5-134">Il codice potrebbe usare anche la tipizzazione implicita mediante la parola chiave [var](../../../language-reference/keywords/var.md), ma si usa la tipizzazione esplicita per illustrare dettagliatamente i risultati.</span><span class="sxs-lookup"><span data-stu-id="b86f5-134">Although the code could also use implicit typing by using the [var](../../../language-reference/keywords/var.md) keyword, explicit typing is used to clearly illustrate results.</span></span> <span data-ttu-id="b86f5-135">Per ulteriori informazioni `var`sulle variabili [locali tipizzate in modo implicito, vedere Variabili locali tipizzate in modo implicito.](../../classes-and-structs/implicitly-typed-local-variables.md)</span><span class="sxs-lookup"><span data-stu-id="b86f5-135">(For more information about `var`, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).)</span></span>  
  
     <span data-ttu-id="b86f5-136">Si noti anche che la variabile di intervallo della query, `student`, funge da riferimento a ogni `Student` nell'origine, fornendo l'accesso di membro per ogni oggetto.</span><span class="sxs-lookup"><span data-stu-id="b86f5-136">Note also that the query's range variable, `student`, serves as a reference to each `Student` in the source, providing member access for each object.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#12)]  
  
## <a name="execute-the-query"></a><span data-ttu-id="b86f5-137">Eseguire la query</span><span class="sxs-lookup"><span data-stu-id="b86f5-137">Execute the Query</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="b86f5-138">Per eseguire la query</span><span class="sxs-lookup"><span data-stu-id="b86f5-138">To execute the query</span></span>  
  
1. <span data-ttu-id="b86f5-139">Scrivere ora il ciclo `foreach` che avvia l'esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="b86f5-139">Now write the `foreach` loop that will cause the query to execute.</span></span> <span data-ttu-id="b86f5-140">Tenere presente quanto segue in merito al codice:</span><span class="sxs-lookup"><span data-stu-id="b86f5-140">Note the following about the code:</span></span>  
  
    - <span data-ttu-id="b86f5-141">A ogni elemento della sequenza restituita si accede tramite la variabile di iterazione nel ciclo `foreach`.</span><span class="sxs-lookup"><span data-stu-id="b86f5-141">Each element in the returned sequence is accessed through the iteration variable in the `foreach` loop.</span></span>  
  
    - <span data-ttu-id="b86f5-142">Il tipo di questa variabile è `Student` e il tipo della variabile di query è compatibile, `IEnumerable<Student>`.</span><span class="sxs-lookup"><span data-stu-id="b86f5-142">The type of this variable is `Student`, and the type of the query variable is compatible, `IEnumerable<Student>`.</span></span>  
  
2. <span data-ttu-id="b86f5-143">Dopo aver aggiunto questo codice, compilare ed eseguire l'applicazione per vedere i risultati nella finestra **Console**.</span><span class="sxs-lookup"><span data-stu-id="b86f5-143">After you have added this code, build and run the application to see the results in the **Console** window.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#13)]  
  
#### <a name="to-add-another-filter-condition"></a><span data-ttu-id="b86f5-144">Per aggiungere un'altra condizione di filtro</span><span class="sxs-lookup"><span data-stu-id="b86f5-144">To add another filter condition</span></span>  
  
1. <span data-ttu-id="b86f5-145">È possibile combinare più condizioni booleane nel clausola `where` per perfezionare ulteriormente la query.</span><span class="sxs-lookup"><span data-stu-id="b86f5-145">You can combine multiple Boolean conditions in the `where` clause in order to further refine a query.</span></span> <span data-ttu-id="b86f5-146">Il codice seguente aggiunge una condizione in modo che la query restituisca gli studenti il cui primo punteggio era maggiore di 90 e il cui ultimo punteggio era minore di 80.</span><span class="sxs-lookup"><span data-stu-id="b86f5-146">The following code adds a condition so that the query returns those students whose first score was over 90 and whose last score was less than 80.</span></span> <span data-ttu-id="b86f5-147">La clausola `where` dovrebbe essere simile al codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b86f5-147">The `where` clause should resemble the following code.</span></span>  
  
    ```csharp
    where student.Scores[0] > 90 && student.Scores[3] < 80  
    ```  
  
     <span data-ttu-id="b86f5-148">Per ulteriori informazioni, vedere [clausola where](../../../language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b86f5-148">For more information, see [where clause](../../../language-reference/keywords/where-clause.md).</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="b86f5-149">Modificare la query</span><span class="sxs-lookup"><span data-stu-id="b86f5-149">Modify the Query</span></span>  
  
#### <a name="to-order-the-results"></a><span data-ttu-id="b86f5-150">Per ordinare i risultati</span><span class="sxs-lookup"><span data-stu-id="b86f5-150">To order the results</span></span>  
  
1. <span data-ttu-id="b86f5-151">Sarà più semplice analizzare i risultati se si trovano nello stesso tipo di ordine.</span><span class="sxs-lookup"><span data-stu-id="b86f5-151">It will be easier to scan the results if they are in some kind of order.</span></span> <span data-ttu-id="b86f5-152">È possibile ordinare la sequenza restituita in base a qualsiasi campo accessibile negli elementi di origine.</span><span class="sxs-lookup"><span data-stu-id="b86f5-152">You can order the returned sequence by any accessible field in the source elements.</span></span> <span data-ttu-id="b86f5-153">Ad esempio, la clausola `orderby` seguente dispone i risultati in ordine alfabetico dalla A alla Z in base al cognome dello studente.</span><span class="sxs-lookup"><span data-stu-id="b86f5-153">For example, the following `orderby` clause orders the results in alphabetical order from A to Z according to the last name of each student.</span></span> <span data-ttu-id="b86f5-154">Aggiungere la seguente clausola `orderby` alla query, subito dopo l'istruzione `where` e prima dell'istruzione `select`:</span><span class="sxs-lookup"><span data-stu-id="b86f5-154">Add the following `orderby` clause to your query, right after the `where` statement and before the `select` statement:</span></span>  
  
    ```csharp
    orderby student.Last ascending  
    ```  
  
2. <span data-ttu-id="b86f5-155">Modificare ora la clausola `orderby` in modo che disponga i risultati in ordine decrescente in base al punteggio del primo test, dal punteggio più alto al più basso.</span><span class="sxs-lookup"><span data-stu-id="b86f5-155">Now change the `orderby` clause so that it orders the results in reverse order according to the score on the first test, from the highest score to the lowest score.</span></span>  
  
    ```csharp
    orderby student.Scores[0] descending  
    ```  
  
3. <span data-ttu-id="b86f5-156">Modificare la stringa di formato `WriteLine` in modo che sia possibile vedere i punteggi:</span><span class="sxs-lookup"><span data-stu-id="b86f5-156">Change the `WriteLine` format string so that you can see the scores:</span></span>  
  
    ```csharp
    Console.WriteLine("{0}, {1} {2}", student.Last, student.First, student.Scores[0]);  
    ```  
  
     <span data-ttu-id="b86f5-157">Per altre informazioni, vedere [Clausola orderby](../../../language-reference/keywords/orderby-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b86f5-157">For more information, see [orderby clause](../../../language-reference/keywords/orderby-clause.md).</span></span>  
  
#### <a name="to-group-the-results"></a><span data-ttu-id="b86f5-158">Per raggruppare i risultati</span><span class="sxs-lookup"><span data-stu-id="b86f5-158">To group the results</span></span>  
  
1. <span data-ttu-id="b86f5-159">Il raggruppamento è una potente funzionalità delle espressioni di query.</span><span class="sxs-lookup"><span data-stu-id="b86f5-159">Grouping is a powerful capability in query expressions.</span></span> <span data-ttu-id="b86f5-160">Una query con una clausola group genera una sequenza di gruppi e ogni gruppo contiene un `Key` e una sequenza costituita da tutti i membri di quel gruppo.</span><span class="sxs-lookup"><span data-stu-id="b86f5-160">A query with a group clause produces a sequence of groups, and each group itself contains a `Key` and a sequence that consists of all the members of that group.</span></span> <span data-ttu-id="b86f5-161">La nuova query riportata di seguito raggruppa gli studenti usando la prima lettera del cognome come chiave.</span><span class="sxs-lookup"><span data-stu-id="b86f5-161">The following new query groups the students by using the first letter of their last name as the key.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#14)]  
  
2. <span data-ttu-id="b86f5-162">Si noti che il tipo della query è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="b86f5-162">Note that the type of the query has now changed.</span></span> <span data-ttu-id="b86f5-163">Ora genera una sequenza di gruppi che hanno il tipo `char` come chiave e una sequenza di oggetti `Student`.</span><span class="sxs-lookup"><span data-stu-id="b86f5-163">It now produces a sequence of groups that have a `char` type as a key, and a sequence of `Student` objects.</span></span> <span data-ttu-id="b86f5-164">Siccome il tipo della query è cambiato, il codice seguente cambia anche il ciclo di esecuzione `foreach`:</span><span class="sxs-lookup"><span data-stu-id="b86f5-164">Because the type of the query has changed, the following code changes the `foreach` execution loop also:</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#15)]  
  
3. <span data-ttu-id="b86f5-165">Eseguire l'applicazione e visualizzare i risultati nella finestra **Console**.</span><span class="sxs-lookup"><span data-stu-id="b86f5-165">Run the application and view the results in the **Console** window.</span></span>  
  
     <span data-ttu-id="b86f5-166">Per altre informazioni, vedere [Clausola group](../../../language-reference/keywords/group-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b86f5-166">For more information, see [group clause](../../../language-reference/keywords/group-clause.md).</span></span>  
  
#### <a name="to-make-the-variables-implicitly-typed"></a><span data-ttu-id="b86f5-167">Per ottenere che le variabili siano tipizzate in modo implicito</span><span class="sxs-lookup"><span data-stu-id="b86f5-167">To make the variables implicitly typed</span></span>  
  
1. <span data-ttu-id="b86f5-168">Codificare in modo esplicito `IEnumerables` di `IGroupings` può risultare noioso.</span><span class="sxs-lookup"><span data-stu-id="b86f5-168">Explicitly coding `IEnumerables` of `IGroupings` can quickly become tedious.</span></span> <span data-ttu-id="b86f5-169">È possibile scrivere la stessa query e ciclo `foreach` in modo molto più semplice usando `var`.</span><span class="sxs-lookup"><span data-stu-id="b86f5-169">You can write the same query and `foreach` loop much more conveniently by using `var`.</span></span> <span data-ttu-id="b86f5-170">La parola chiave `var` non cambia il tipo degli oggetti ma si limita a istruire il compilatore a dedurre i tipi.</span><span class="sxs-lookup"><span data-stu-id="b86f5-170">The `var` keyword does not change the types of your objects; it just instructs the compiler to infer the types.</span></span> <span data-ttu-id="b86f5-171">Cambiare il tipo di `studentQuery` e la variabile di iterazione `group` in `var` ed eseguire di nuovo la query.</span><span class="sxs-lookup"><span data-stu-id="b86f5-171">Change the type of `studentQuery` and the iteration variable `group` to `var` and rerun the query.</span></span> <span data-ttu-id="b86f5-172">Si noti che nel ciclo `foreach` interno, la variabile di iterazione è ancora tipizzata come `Student` e la query funziona esattamente come prima.</span><span class="sxs-lookup"><span data-stu-id="b86f5-172">Note that in the inner `foreach` loop, the iteration variable is still typed as `Student`, and the query works just as before.</span></span> <span data-ttu-id="b86f5-173">Cambiare la variabile di iterazione `s` in `var` ed eseguire di nuovo la query.</span><span class="sxs-lookup"><span data-stu-id="b86f5-173">Change the `s` iteration variable to `var` and run the query again.</span></span> <span data-ttu-id="b86f5-174">Si noti che si ottengono esattamente gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="b86f5-174">You see that you get exactly the same results.</span></span>  
  
     [!code-csharp[CsLINQGettingStarted#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#16)]  
  
     <span data-ttu-id="b86f5-175">Per altre informazioni su [var](../../../language-reference/keywords/var.md), vedere [Variabili locali tipizzate in modo implicito](../../classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="b86f5-175">For more information about [var](../../../language-reference/keywords/var.md), see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
#### <a name="to-order-the-groups-by-their-key-value"></a><span data-ttu-id="b86f5-176">Per ordinare i gruppi in base al valore della chiave</span><span class="sxs-lookup"><span data-stu-id="b86f5-176">To order the groups by their key value</span></span>  
  
1. <span data-ttu-id="b86f5-177">Quando si esegue la query precedente, si nota che i gruppi non sono in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="b86f5-177">When you run the previous query, you notice that the groups are not in alphabetical order.</span></span> <span data-ttu-id="b86f5-178">Per modificare questa impostazione è necessario fornire una clausola `orderby` dopo la clausola `group`.</span><span class="sxs-lookup"><span data-stu-id="b86f5-178">To change this, you must provide an `orderby` clause after the `group` clause.</span></span> <span data-ttu-id="b86f5-179">Ma per usare una clausola `orderby`, è necessario un identificatore che funge da riferimento ai gruppi creati per la clausola `group`.</span><span class="sxs-lookup"><span data-stu-id="b86f5-179">But to use an `orderby` clause, you first need an identifier that serves as a reference to the groups created by the `group` clause.</span></span> <span data-ttu-id="b86f5-180">L'identificatore viene fornito usando la parola chiave `into`, come segue:</span><span class="sxs-lookup"><span data-stu-id="b86f5-180">You provide the identifier by using the `into` keyword, as follows:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#17)]  
  
     <span data-ttu-id="b86f5-181">Quando si esegue questa query si può notare che i gruppi vengono disposti in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="b86f5-181">When you run this query, you will see the groups are now sorted in alphabetical order.</span></span>  
  
#### <a name="to-introduce-an-identifier-by-using-let"></a><span data-ttu-id="b86f5-182">Per introdurre un identificatore usando let</span><span class="sxs-lookup"><span data-stu-id="b86f5-182">To introduce an identifier by using let</span></span>  
  
1. <span data-ttu-id="b86f5-183">È possibile usare la parola chiave `let` per introdurre un identificatore per qualsiasi risultato di espressione nell'espressione di query.</span><span class="sxs-lookup"><span data-stu-id="b86f5-183">You can use the `let` keyword to introduce an identifier for any expression result in the query expression.</span></span> <span data-ttu-id="b86f5-184">Questo identificatore può essere comodo, come nell'esempio seguente, oppure può migliorare le prestazioni archiviando i risultati di un'espressione in modo che non debba essere calcolata più volte.</span><span class="sxs-lookup"><span data-stu-id="b86f5-184">This identifier can be a convenience, as in the following example, or it can enhance performance by storing the results of an expression so that it does not have to be calculated multiple times.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#18)]  
  
     <span data-ttu-id="b86f5-185">Per altre informazioni, vedere [Clausola let](../../../language-reference/keywords/let-clause.md).</span><span class="sxs-lookup"><span data-stu-id="b86f5-185">For more information, see [let clause](../../../language-reference/keywords/let-clause.md).</span></span>  
  
#### <a name="to-use-method-syntax-in-a-query-expression"></a><span data-ttu-id="b86f5-186">Per usare la sintassi del metodo in un'espressione di query</span><span class="sxs-lookup"><span data-stu-id="b86f5-186">To use method syntax in a query expression</span></span>  
  
1. <span data-ttu-id="b86f5-187">Come descritto in [Sintassi di query e sintassi di metodi in LINQ](./query-syntax-and-method-syntax-in-linq.md), alcune operazioni di query possono essere espresse solo usando la sintassi dei metodi.</span><span class="sxs-lookup"><span data-stu-id="b86f5-187">As described in [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md), some query operations can only be expressed by using method syntax.</span></span> <span data-ttu-id="b86f5-188">Il codice seguente calcola il punteggio totale per ogni `Student` nella sequenza di origine e quindi chiama il metodo `Average()` sui risultati della query per calcolare il punteggio medio della classe.</span><span class="sxs-lookup"><span data-stu-id="b86f5-188">The following code calculates the total score for each `Student` in the source sequence, and then calls the `Average()` method on the results of that query to calculate the average score of the class.</span></span>
  
     [!code-csharp[csLINQGettingStarted#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#19)]  
  
#### <a name="to-transform-or-project-in-the-select-clause"></a><span data-ttu-id="b86f5-189">Per eseguire trasformazioni o proiezioni nella clausola select</span><span class="sxs-lookup"><span data-stu-id="b86f5-189">To transform or project in the select clause</span></span>  
  
1. <span data-ttu-id="b86f5-190">Un compito molto comune per una query è generare una sequenza i cui elementi differiscono da quelli delle sequenze di origine.</span><span class="sxs-lookup"><span data-stu-id="b86f5-190">It is very common for a query to produce a sequence whose elements differ from the elements in the source sequences.</span></span> <span data-ttu-id="b86f5-191">Eliminare o impostare come commento il ciclo di query ed esecuzione precedente e sostituirlo con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b86f5-191">Delete or comment out your previous query and execution loop, and replace it with the following code.</span></span> <span data-ttu-id="b86f5-192">Si noti che la query restituisce una sequenza di stringhe (non `Students`) e questo si riflette nel ciclo `foreach`.</span><span class="sxs-lookup"><span data-stu-id="b86f5-192">Note that the query returns a sequence of strings (not `Students`), and this fact is reflected in the `foreach` loop.</span></span>  
  
     [!code-csharp[csLINQGettingStarted#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#20)]  
  
2. <span data-ttu-id="b86f5-193">Il codice precedente di questa procedura dettagliata indica che il punteggio medio della classe è pari a circa 334.</span><span class="sxs-lookup"><span data-stu-id="b86f5-193">Code earlier in this walkthrough indicated that the average class score is approximately 334.</span></span> <span data-ttu-id="b86f5-194">Per produrre una sequenza di `Students` il cui punteggio totale sia maggiore della media della classe, insieme al loro `Student ID`, è possibile usare un tipo anonimo nell'istruzione `select`:</span><span class="sxs-lookup"><span data-stu-id="b86f5-194">To produce a sequence of `Students` whose total score is greater than the class average, together with their `Student ID`, you can use an anonymous type in the `select` statement:</span></span>  
  
     [!code-csharp[csLINQGettingStarted#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#21)]  
  
## <a name="next-steps"></a><span data-ttu-id="b86f5-195">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b86f5-195">Next Steps</span></span>  
 <span data-ttu-id="b86f5-196">Dopo aver acquisito familiarità con i fondamenti dell'uso delle query in C#, è possibile leggere la documentazione e vedere gli esempi per il tipo specifico di provider LINQ a cui si è interessati:</span><span class="sxs-lookup"><span data-stu-id="b86f5-196">After you are familiar with the basic aspects of working with queries in C#, you are ready to read the documentation and samples for the specific type of LINQ provider you are interested in:</span></span>  
  
 [<span data-ttu-id="b86f5-197">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b86f5-197">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="b86f5-198">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="b86f5-198">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
 [<span data-ttu-id="b86f5-199">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b86f5-199">LINQ to XML (C#)</span></span>](./linq-to-xml-overview.md)  
  
 [<span data-ttu-id="b86f5-200">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="b86f5-200">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="b86f5-201">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b86f5-201">See also</span></span>

- [<span data-ttu-id="b86f5-202">LINQ (Language-Integrated Query) (C#)</span><span class="sxs-lookup"><span data-stu-id="b86f5-202">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="b86f5-203">Espressioni di query LINQLINQ Query Expressions</span><span class="sxs-lookup"><span data-stu-id="b86f5-203">LINQ Query Expressions</span></span>](../../../linq/index.md)

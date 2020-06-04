---
title: 'Procedura: Combinare dati con LINQ usando Join'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: de8c4ec3ab8a0f2335c034231c661380420fd31b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405004"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="ae17e-102">Procedura: combinare dati con LINQ utilizzando join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae17e-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>
<span data-ttu-id="ae17e-103">Visual Basic fornisce le `Join` `Group Join` clausole di query e per consentire di combinare il contenuto di più raccolte in base ai valori comuni tra le raccolte.</span><span class="sxs-lookup"><span data-stu-id="ae17e-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="ae17e-104">Questi valori sono noti come valori *chiave* .</span><span class="sxs-lookup"><span data-stu-id="ae17e-104">These values are known as *key* values.</span></span> <span data-ttu-id="ae17e-105">Gli sviluppatori che hanno familiarità con i concetti di database relazionale riconoscono la `Join` clausola come Inner join e la `Group Join` clausola come, in realtà, un left outer join.</span><span class="sxs-lookup"><span data-stu-id="ae17e-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="ae17e-106">Negli esempi di questo argomento vengono illustrati alcuni modi per combinare i dati utilizzando `Join` le `Group Join` clausole di query e.</span><span class="sxs-lookup"><span data-stu-id="ae17e-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="ae17e-107">Creare un progetto e aggiungere dati di esempio</span><span class="sxs-lookup"><span data-stu-id="ae17e-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="ae17e-108">Per creare un progetto che contiene dati e tipi di esempio</span><span class="sxs-lookup"><span data-stu-id="ae17e-108">To create a project that contains sample data and types</span></span>  
  
1. <span data-ttu-id="ae17e-109">Per eseguire gli esempi in questo argomento, aprire Visual Studio e aggiungere un nuovo progetto di applicazione console Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ae17e-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="ae17e-110">Fare doppio clic sul file Module1. vb creato da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ae17e-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2. <span data-ttu-id="ae17e-111">Negli esempi di questo argomento vengono usati `Person` i `Pet` tipi e e i dati dell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ae17e-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="ae17e-112">Copiare questo codice nel modulo predefinito `Module1` creato da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ae17e-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="ae17e-113">Eseguire un inner join usando la clausola join</span><span class="sxs-lookup"><span data-stu-id="ae17e-113">Perform an Inner Join by Using the Join Clause</span></span>  
 <span data-ttu-id="ae17e-114">Un INNER JOIN combina i dati di due raccolte.</span><span class="sxs-lookup"><span data-stu-id="ae17e-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="ae17e-115">Sono inclusi gli elementi per i quali corrispondono i valori di chiave specificati.</span><span class="sxs-lookup"><span data-stu-id="ae17e-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="ae17e-116">Tutti gli elementi di una raccolta che non dispongono di un elemento corrispondente nell'altra raccolta vengono esclusi.</span><span class="sxs-lookup"><span data-stu-id="ae17e-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="ae17e-117">In Visual Basic LINQ fornisce due opzioni per l'esecuzione di un INNER JOIN, ovvero un join implicito e un join esplicito.</span><span class="sxs-lookup"><span data-stu-id="ae17e-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="ae17e-118">Un join implicito specifica le raccolte da unire in una `From` clausola e identifica i campi chiave corrispondenti in una `Where` clausola.</span><span class="sxs-lookup"><span data-stu-id="ae17e-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="ae17e-119">Visual Basic unisce in modo implicito le due raccolte in base ai campi chiave specificati.</span><span class="sxs-lookup"><span data-stu-id="ae17e-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="ae17e-120">È possibile specificare un join esplicito usando la `Join` clausola quando si desidera essere specifici dei campi chiave da usare nel join.</span><span class="sxs-lookup"><span data-stu-id="ae17e-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="ae17e-121">In questo caso, `Where` è ancora possibile utilizzare una clausola per filtrare i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="ae17e-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="ae17e-122">Per eseguire un inner join tramite la clausola join</span><span class="sxs-lookup"><span data-stu-id="ae17e-122">To perform an Inner Join by using the Join clause</span></span>  
  
1. <span data-ttu-id="ae17e-123">Aggiungere il codice seguente al `Module1` modulo nel progetto per visualizzare esempi di Inner join impliciti ed espliciti.</span><span class="sxs-lookup"><span data-stu-id="ae17e-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="ae17e-124">Eseguire un left outer join usando la clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="ae17e-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  
 <span data-ttu-id="ae17e-125">Un LEFT OUTER JOIN include tutti gli elementi della raccolta di sinistra del join e solo i valori corrispondenti dalla raccolta di destra del join.</span><span class="sxs-lookup"><span data-stu-id="ae17e-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="ae17e-126">Tutti gli elementi della raccolta di destra del join che non dispongono di un elemento corrispondente nell'insieme di sinistra vengono esclusi dal risultato della query.</span><span class="sxs-lookup"><span data-stu-id="ae17e-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="ae17e-127">La `Group Join` clausola esegue, in effetti, un left outer join.</span><span class="sxs-lookup"><span data-stu-id="ae17e-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="ae17e-128">La differenza tra ciò che è in genere noto come LEFT OUTER JOIN e la `Group Join` clausola restituita dalla clausola è che la `Group Join` clausola raggruppa i risultati della raccolta di destra del join per ogni elemento nella raccolta di sinistra.</span><span class="sxs-lookup"><span data-stu-id="ae17e-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="ae17e-129">In un database relazionale, un LEFT OUTER JOIN restituisce un risultato non raggruppato in cui ogni elemento nel risultato della query contiene elementi corrispondenti di entrambe le raccolte nel join.</span><span class="sxs-lookup"><span data-stu-id="ae17e-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="ae17e-130">In questo caso, gli elementi della raccolta di sinistra del join vengono ripetuti per ogni elemento corrispondente dalla raccolta di destra.</span><span class="sxs-lookup"><span data-stu-id="ae17e-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="ae17e-131">Quando si completa la procedura successiva, verrà visualizzato questo aspetto.</span><span class="sxs-lookup"><span data-stu-id="ae17e-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="ae17e-132">È possibile recuperare i risultati di una `Group Join` query come risultato non raggruppato estendendo la query in modo da restituire un elemento per ogni risultato della query raggruppata.</span><span class="sxs-lookup"><span data-stu-id="ae17e-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="ae17e-133">A tale scopo, è necessario assicurarsi di eseguire una query sul `DefaultIfEmpty` metodo della raccolta raggruppata.</span><span class="sxs-lookup"><span data-stu-id="ae17e-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="ae17e-134">In questo modo si garantisce che gli elementi della raccolta di sinistra del join siano ancora inclusi nel risultato della query anche se non hanno risultati corrispondenti dalla raccolta di destra.</span><span class="sxs-lookup"><span data-stu-id="ae17e-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="ae17e-135">È possibile aggiungere codice alla query per fornire un valore di risultato predefinito quando non esiste alcun valore corrispondente dalla raccolta di destra del join.</span><span class="sxs-lookup"><span data-stu-id="ae17e-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="ae17e-136">Per eseguire un left outer join tramite la clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="ae17e-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1. <span data-ttu-id="ae17e-137">Aggiungere il codice seguente al `Module1` modulo nel progetto per visualizzare esempi di un left outer join raggruppato e di un left outer join non raggruppato.</span><span class="sxs-lookup"><span data-stu-id="ae17e-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="ae17e-138">Eseguire un join usando una chiave composta</span><span class="sxs-lookup"><span data-stu-id="ae17e-138">Perform a Join by Using a Composite Key</span></span>  
 <span data-ttu-id="ae17e-139">È possibile usare la `And` parola chiave in `Join` una `Group Join` clausola o per identificare più campi chiave da usare quando si corrispondono ai valori delle raccolte da unire.</span><span class="sxs-lookup"><span data-stu-id="ae17e-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="ae17e-140">La `And` parola chiave specifica che tutti i campi chiave specificati devono corrispondere per gli elementi da unire.</span><span class="sxs-lookup"><span data-stu-id="ae17e-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="ae17e-141">Per eseguire un join utilizzando una chiave composta</span><span class="sxs-lookup"><span data-stu-id="ae17e-141">To perform a Join by using a composite key</span></span>  
  
1. <span data-ttu-id="ae17e-142">Aggiungere il codice seguente al `Module1` modulo nel progetto per visualizzare esempi di un join che usa una chiave composta.</span><span class="sxs-lookup"><span data-stu-id="ae17e-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a><span data-ttu-id="ae17e-143">Eseguire il codice</span><span class="sxs-lookup"><span data-stu-id="ae17e-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="ae17e-144">Per aggiungere codice per eseguire gli esempi</span><span class="sxs-lookup"><span data-stu-id="ae17e-144">To add code to run the examples</span></span>  
  
1. <span data-ttu-id="ae17e-145">Sostituire `Sub Main` nel modulo del `Module1` progetto con il codice seguente per eseguire gli esempi in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ae17e-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. <span data-ttu-id="ae17e-146">Premere F5 per eseguire gli esempi.</span><span class="sxs-lookup"><span data-stu-id="ae17e-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae17e-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae17e-147">See also</span></span>

- [<span data-ttu-id="ae17e-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="ae17e-148">LINQ</span></span>](index.md)
- [<span data-ttu-id="ae17e-149">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae17e-149">Introduction to LINQ in Visual Basic</span></span>](introduction-to-linq.md)
- [<span data-ttu-id="ae17e-150">Clausola join</span><span class="sxs-lookup"><span data-stu-id="ae17e-150">Join Clause</span></span>](../../../language-reference/queries/join-clause.md)
- [<span data-ttu-id="ae17e-151">Clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="ae17e-151">Group Join Clause</span></span>](../../../language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="ae17e-152">Clausola from</span><span class="sxs-lookup"><span data-stu-id="ae17e-152">From Clause</span></span>](../../../language-reference/queries/from-clause.md)
- [<span data-ttu-id="ae17e-153">Clausola WHERE</span><span class="sxs-lookup"><span data-stu-id="ae17e-153">Where Clause</span></span>](../../../language-reference/queries/where-clause.md)
- [<span data-ttu-id="ae17e-154">Query</span><span class="sxs-lookup"><span data-stu-id="ae17e-154">Queries</span></span>](../../../language-reference/queries/index.md)
- [<span data-ttu-id="ae17e-155">Trasformazioni dati con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="ae17e-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)

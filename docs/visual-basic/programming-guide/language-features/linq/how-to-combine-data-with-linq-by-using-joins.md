---
title: 'Procedura: combinare dati con LINQ usando join'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: 7279908c5d262b65f4c4da9cd9b6c1b4117bc402
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344996"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="c0fda-102">Procedura: combinare dati con LINQ utilizzando join (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0fda-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>
<span data-ttu-id="c0fda-103">Visual Basic fornisce le clausole di query `Join` e `Group Join` per consentire di combinare il contenuto di più raccolte in base ai valori comuni tra le raccolte.</span><span class="sxs-lookup"><span data-stu-id="c0fda-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="c0fda-104">Questi valori sono noti come valori *chiave* .</span><span class="sxs-lookup"><span data-stu-id="c0fda-104">These values are known as *key* values.</span></span> <span data-ttu-id="c0fda-105">Gli sviluppatori che hanno familiarità con i concetti di database relazionale riconoscono la clausola `Join` come INNER JOIN e la clausola `Group Join` come, in effetti, un LEFT OUTER JOIN.</span><span class="sxs-lookup"><span data-stu-id="c0fda-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="c0fda-106">Negli esempi di questo argomento vengono illustrati alcuni modi per combinare i dati utilizzando le clausole di query `Join` e `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="c0fda-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="c0fda-107">Creare un progetto e aggiungere dati di esempio</span><span class="sxs-lookup"><span data-stu-id="c0fda-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="c0fda-108">Per creare un progetto che contiene dati e tipi di esempio</span><span class="sxs-lookup"><span data-stu-id="c0fda-108">To create a project that contains sample data and types</span></span>  
  
1. <span data-ttu-id="c0fda-109">Per eseguire gli esempi in questo argomento, aprire Visual Studio e aggiungere un nuovo progetto di applicazione console Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c0fda-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="c0fda-110">Fare doppio clic sul file Module1. vb creato da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c0fda-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2. <span data-ttu-id="c0fda-111">Negli esempi di questo argomento vengono utilizzati i tipi e i dati `Person` e `Pet` dell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c0fda-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="c0fda-112">Copiare questo codice nel modulo predefinito `Module1` creato da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c0fda-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="c0fda-113">Eseguire un inner join usando la clausola join</span><span class="sxs-lookup"><span data-stu-id="c0fda-113">Perform an Inner Join by Using the Join Clause</span></span>  
 <span data-ttu-id="c0fda-114">Un INNER JOIN combina i dati di due raccolte.</span><span class="sxs-lookup"><span data-stu-id="c0fda-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="c0fda-115">Sono inclusi gli elementi per i quali corrispondono i valori di chiave specificati.</span><span class="sxs-lookup"><span data-stu-id="c0fda-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="c0fda-116">Tutti gli elementi di una raccolta che non dispongono di un elemento corrispondente nell'altra raccolta vengono esclusi.</span><span class="sxs-lookup"><span data-stu-id="c0fda-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="c0fda-117">In Visual Basic LINQ fornisce due opzioni per l'esecuzione di un INNER JOIN, ovvero un join implicito e un join esplicito.</span><span class="sxs-lookup"><span data-stu-id="c0fda-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="c0fda-118">Un join implicito specifica le raccolte da unire in una clausola `From` e identifica i campi chiave corrispondenti in una clausola `Where`.</span><span class="sxs-lookup"><span data-stu-id="c0fda-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="c0fda-119">Visual Basic unisce in modo implicito le due raccolte in base ai campi chiave specificati.</span><span class="sxs-lookup"><span data-stu-id="c0fda-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="c0fda-120">È possibile specificare un join esplicito usando la clausola `Join` quando si vuole essere specifici sui campi chiave da usare nel join.</span><span class="sxs-lookup"><span data-stu-id="c0fda-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="c0fda-121">In questo caso, è ancora possibile utilizzare una clausola `Where` per filtrare i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="c0fda-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="c0fda-122">Per eseguire un inner join tramite la clausola join</span><span class="sxs-lookup"><span data-stu-id="c0fda-122">To perform an Inner Join by using the Join clause</span></span>  
  
1. <span data-ttu-id="c0fda-123">Aggiungere il codice seguente al modulo `Module1` nel progetto per visualizzare esempi di inner join impliciti ed espliciti.</span><span class="sxs-lookup"><span data-stu-id="c0fda-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="c0fda-124">Eseguire un left outer join usando la clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="c0fda-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  
 <span data-ttu-id="c0fda-125">Un LEFT OUTER JOIN include tutti gli elementi della raccolta di sinistra del join e solo i valori corrispondenti dalla raccolta di destra del join.</span><span class="sxs-lookup"><span data-stu-id="c0fda-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="c0fda-126">Tutti gli elementi della raccolta di destra del join che non dispongono di un elemento corrispondente nell'insieme di sinistra vengono esclusi dal risultato della query.</span><span class="sxs-lookup"><span data-stu-id="c0fda-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="c0fda-127">La clausola `Group Join` esegue, in effetti, un LEFT OUTER JOIN.</span><span class="sxs-lookup"><span data-stu-id="c0fda-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="c0fda-128">La differenza tra ciò che è in genere noto come LEFT OUTER JOIN e il risultato restituito dalla clausola `Group Join` è che la clausola `Group Join` raggruppa i risultati della raccolta di destra del join per ogni elemento nella raccolta di sinistra.</span><span class="sxs-lookup"><span data-stu-id="c0fda-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="c0fda-129">In un database relazionale, un LEFT OUTER JOIN restituisce un risultato non raggruppato in cui ogni elemento nel risultato della query contiene elementi corrispondenti di entrambe le raccolte nel join.</span><span class="sxs-lookup"><span data-stu-id="c0fda-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="c0fda-130">In questo caso, gli elementi della raccolta di sinistra del join vengono ripetuti per ogni elemento corrispondente dalla raccolta di destra.</span><span class="sxs-lookup"><span data-stu-id="c0fda-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="c0fda-131">Quando si completa la procedura successiva, verrà visualizzato questo aspetto.</span><span class="sxs-lookup"><span data-stu-id="c0fda-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="c0fda-132">È possibile recuperare i risultati di una query di `Group Join` come risultato non raggruppato estendendo la query in modo da restituire un elemento per ogni risultato della query raggruppata.</span><span class="sxs-lookup"><span data-stu-id="c0fda-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="c0fda-133">A tale scopo, è necessario assicurarsi di eseguire una query sul metodo `DefaultIfEmpty` della raccolta raggruppata.</span><span class="sxs-lookup"><span data-stu-id="c0fda-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="c0fda-134">In questo modo si garantisce che gli elementi della raccolta di sinistra del join siano ancora inclusi nel risultato della query anche se non hanno risultati corrispondenti dalla raccolta di destra.</span><span class="sxs-lookup"><span data-stu-id="c0fda-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="c0fda-135">È possibile aggiungere codice alla query per fornire un valore di risultato predefinito quando non esiste alcun valore corrispondente dalla raccolta di destra del join.</span><span class="sxs-lookup"><span data-stu-id="c0fda-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="c0fda-136">Per eseguire un left outer join tramite la clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="c0fda-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1. <span data-ttu-id="c0fda-137">Aggiungere il codice seguente al modulo `Module1` nel progetto per visualizzare esempi di un left outer join raggruppato e di un left outer join non raggruppato.</span><span class="sxs-lookup"><span data-stu-id="c0fda-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="c0fda-138">Eseguire un join usando una chiave composta</span><span class="sxs-lookup"><span data-stu-id="c0fda-138">Perform a Join by Using a Composite Key</span></span>  
 <span data-ttu-id="c0fda-139">È possibile usare la parola chiave `And` in una clausola `Join` o `Group Join` per identificare più campi chiave da usare quando si corrispondono ai valori delle raccolte da unire.</span><span class="sxs-lookup"><span data-stu-id="c0fda-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="c0fda-140">La parola chiave `And` specifica che tutti i campi chiave specificati devono corrispondere per gli elementi da unire.</span><span class="sxs-lookup"><span data-stu-id="c0fda-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="c0fda-141">Per eseguire un join utilizzando una chiave composta</span><span class="sxs-lookup"><span data-stu-id="c0fda-141">To perform a Join by using a composite key</span></span>  
  
1. <span data-ttu-id="c0fda-142">Aggiungere il codice seguente al modulo `Module1` nel progetto per visualizzare esempi di un join che usa una chiave composta.</span><span class="sxs-lookup"><span data-stu-id="c0fda-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a><span data-ttu-id="c0fda-143">Eseguire il codice</span><span class="sxs-lookup"><span data-stu-id="c0fda-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="c0fda-144">Per aggiungere codice per eseguire gli esempi</span><span class="sxs-lookup"><span data-stu-id="c0fda-144">To add code to run the examples</span></span>  
  
1. <span data-ttu-id="c0fda-145">Sostituire il `Sub Main` nel modulo `Module1` nel progetto con il codice seguente per eseguire gli esempi in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c0fda-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. <span data-ttu-id="c0fda-146">Premere F5 per eseguire gli esempi.</span><span class="sxs-lookup"><span data-stu-id="c0fda-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0fda-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0fda-147">See also</span></span>

- [<span data-ttu-id="c0fda-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="c0fda-148">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="c0fda-149">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c0fda-149">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="c0fda-150">Clausola Join</span><span class="sxs-lookup"><span data-stu-id="c0fda-150">Join Clause</span></span>](../../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="c0fda-151">Clausola Group Join</span><span class="sxs-lookup"><span data-stu-id="c0fda-151">Group Join Clause</span></span>](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="c0fda-152">Clausola From</span><span class="sxs-lookup"><span data-stu-id="c0fda-152">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="c0fda-153">Clausola Where</span><span class="sxs-lookup"><span data-stu-id="c0fda-153">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="c0fda-154">Query</span><span class="sxs-lookup"><span data-stu-id="c0fda-154">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="c0fda-155">Trasformazioni dati con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="c0fda-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)

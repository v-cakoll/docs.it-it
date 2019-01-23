---
title: 'Procedura: Combinare dati con LINQ utilizzando join (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: fd1025d056dfb11d2253a39defb384c1d05efa32
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553698"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Procedura: Combinare dati con LINQ utilizzando join (Visual Basic)
Visual Basic fornisce il `Join` e `Group Join` clausole che consentono di combinare i contenuti di più raccolte in base ai valori comuni tra le raccolte di query. Questi valori sono dette *chiave* valori. Verranno considerati dagli sviluppatori ha familiari con concetti relativi ai database relazionali di `Join` clausola come un INNER JOIN e `Group Join` clausola come, in effetti, un LEFT OUTER JOIN.  
  
 Gli esempi in questo argomento illustrano alcuni modi per combinare dati utilizzando il `Join` e `Group Join` clausole di query.  
  
## <a name="create-a-project-and-add-sample-data"></a>Creare un progetto e aggiungere dati di esempio  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Per creare un progetto che contiene i tipi e i dati di esempio  
  
1.  Per eseguire gli esempi in questo argomento, aprire Visual Studio e aggiungere un nuovo progetto di applicazione Console Visual Basic. Fare doppio clic sul file Module1.vb creato da Visual Basic.  
  
2.  Gli esempi in questo argomento viene utilizzato il `Person` e `Pet` tipi e i dati di esempio di codice seguente. Copiare questo codice nel valore predefinito `Module1` modulo è stato creato da Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Eseguire un Inner Join usando la clausola Join  
 Un INNER JOIN vengono combinati i dati dalle due raccolte. Vengono inclusi gli elementi per cui i valori di chiave specificati corrispondono. Sono esclusi tutti gli elementi da una qualsiasi raccolta che non è un elemento corrispondente in altro insieme.  
  
 In Visual Basic LINQ sono disponibili due opzioni per l'esecuzione di un INNER JOIN: un join implicito e un join esplicito.  
  
 Specifica di un join implicito le raccolte da includere in un `From` clausola e identifica i campi chiave corrispondenti in un `Where` clausola. Visual Basic crea un join in modo implicito le due raccolte in base ai campi di chiave specificati.  
  
 È possibile specificare un join esplicito utilizzando il `Join` clausola quando si desidera essere specifici quali campi chiave per l'utilizzo del join. In questo caso, un `Where` clausola può ancora essere utilizzata per filtrare i risultati della query.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Eseguire un Inner Join usando la clausola Join  
  
1.  Aggiungere il codice seguente per il `Module1` modulo nel progetto per vedere esempi di inner join sia impliciti ed espliciti.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Eseguire un Left Outer Join con la clausola Group Join  
 LEFT OUTER JOIN include tutti gli elementi dalla raccolta a sinistra del join e solo i corrispondenti valori dalla raccolta a destra del join. Tutti gli elementi dalla raccolta a destra del join che non è un elemento corrispondente nella raccolta a sinistra vengono esclusi dal risultato della query.  
  
 Il `Group Join` clausola esegue, in effetti, un LEFT OUTER JOIN. La differenza tra ciò che è in genere noto come un LEFT OUTER JOIN e quali le `Group Join` la clausola restituisce è che il `Group Join` risultati del nodo gruppi clausola dalla raccolta a destra del join per ogni elemento nella raccolta a sinistra. In un database relazionale, un LEFT OUTER JOIN restituisce un risultato non raggruppato nella quale restituire ogni elemento della query contiene gli elementi corrispondenti da entrambe le raccolte nel join. In questo caso, gli elementi dalla raccolta a sinistra del join vengono ripetuti per ogni elemento corrispondente dalla raccolta a destra. Verrà visualizzato come appare quando si completa la procedura successiva.  
  
 È possibile recuperare i risultati di una `Group Join` query come risultato non raggruppato mediante l'estensione di query per restituire un elemento per ogni risultato della query raggruppati. A tale scopo, è necessario assicurarsi che si esegue una query nella `DefaultIfEmpty` metodo della raccolta raggruppata. Ciò garantisce che gli elementi della raccolta lato sinistro del join sono ancora incluse nel risultato della query, anche se non hanno risultati corrispondenti dalla raccolta a destra. È possibile aggiungere codice alla query per fornire un valore predefinito quando è presente alcun valore corrispondente dalla raccolta a destra del join.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Per eseguire un Left Outer Join con la clausola Group Join  
  
1.  Aggiungere il codice seguente per il `Module1` modulo nel progetto per visualizzare un esempio di un left outer join raggruppati e un left outer join non raggruppati.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Eseguire un Join usando una chiave composta  
 È possibile usare la `And` parola chiave in un `Join` o `Group Join` clausola per identificare più campi di chiave da usare durante l'associazione di valori dalle raccolte da unire in join. Il `And` parola chiave specifica che tutti specificati devono corrispondere ai campi chiave per gli elementi da unire.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Per eseguire un Join usando una chiave composta  
  
1.  Aggiungere il codice seguente per il `Module1` modulo nel progetto per vedere esempi di join che utilizza una chiave composta.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a>Eseguire il codice  
  
#### <a name="to-add-code-to-run-the-examples"></a>Per aggiungere il codice per eseguire gli esempi  
  
1.  Sostituire il `Sub Main` nella `Module1` modulo nel progetto con il codice seguente per eseguire gli esempi in questo argomento.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  Premere F5 per eseguire gli esempi.  
  
## <a name="see-also"></a>Vedere anche
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md)
- [Clausola Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Clausola From](../../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
- [Trasformazioni dati con LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)

---
title: 'Procedura: combinare dati con LINQ utilizzando join (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 432be646ce4353fd4627a34f363e7562f6181e92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Procedura: combinare dati con LINQ utilizzando join (Visual Basic)
Visual Basic fornisce il `Join` e `Group Join` clausole che consentono di unire il contenuto di più raccolte in base ai valori comuni tra le raccolte di query. Questi valori sono noti come *chiave* valori. Gli sviluppatori che hanno familiari con concetti di database relazionale riconosceranno il `Join` clausola come un INNER JOIN e `Group Join` clausola come, in modo efficace, un LEFT OUTER JOIN.  
  
 Gli esempi in questo argomento illustrano alcuni modi per combinare dati utilizzando il `Join` e `Group Join` clausole di query.  
  
## <a name="create-a-project-and-add-sample-data"></a>Creare un progetto e aggiungere dati di esempio  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Per creare un progetto che contiene i tipi e i dati di esempio  
  
1.  Per eseguire gli esempi in questo argomento, aprire Visual Studio e aggiungere un nuovo progetto applicazione Console Visual Basic. Fare doppio clic sul file Module1. vb creato da Visual Basic.  
  
2.  Gli esempi in questo argomento usano il `Person` e `Pet` tipi e i dati di esempio di codice seguente. Copiare il codice nel valore predefinito `Module1` modulo creato da Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Eseguire un Inner Join tramite la clausola Join  
 Un INNER JOIN combina i dati dalle due raccolte. Vengono inclusi gli elementi per cui i valori di chiave specificati corrispondano. Sono esclusi tutti gli elementi da una qualsiasi raccolta che non sono un elemento corrispondente in altro insieme.  
  
 In Visual Basic LINQ sono disponibili due opzioni per l'esecuzione di un INNER JOIN: un join implicito e un join esplicito.  
  
 Un join implicito specifica le raccolte da includere in un `From` clausola e identifica i campi chiave corrispondenti in un `Where` clausola. Visual Basic in modo implicito unisce le due raccolte in base ai campi di chiave specificati.  
  
 È possibile specificare un join esplicito utilizzando il `Join` clausola quando si desidera specificare quali campi chiave per l'utilizzo del join. In questo caso, un `Where` clausola può ancora essere utilizzata per filtrare i risultati della query.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Per eseguire un'operazione Inner Join tramite la clausola Join  
  
1.  Aggiungere il codice seguente per il `Module1` modulo nel progetto per vedere gli esempi di inner join sia implicite ed esplicite.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Eseguire un Left Outer Join con la clausola Group Join  
 Un LEFT OUTER JOIN include tutti gli elementi dalla raccolta sul lato sinistro del join e solo i valori dalla raccolta a destra del join corrispondenti. Tutti gli elementi dalla raccolta a destra del join che non sono un elemento corrispondente nella raccolta a sinistra vengono escluse dai risultati della query.  
  
 Il `Group Join` clausola esegue, in effetti, un LEFT OUTER JOIN. La differenza tra quello che viene in genere noto come un LEFT OUTER JOIN e cosa il `Group Join` clausola restituisce un valore che è il `Group Join` clausola Raggruppa i risultati dalla raccolta a destra del join per ogni elemento nella raccolta a sinistra. In un database relazionale, un LEFT OUTER JOIN restituisce un risultato non raggruppato in cui ogni elemento nella query risultato contiene elementi corrispondenti da entrambe le raccolte nel join. In questo caso, gli elementi dalla raccolta sul lato sinistro del join vengono ripetuti per ogni elemento corrispondente dalla raccolta a destra. Verrà visualizzato questo aspetto quando si completa la procedura successiva.  
  
 È possibile recuperare i risultati di una `Group Join` query come risultato non raggruppato mediante l'estensione di query per restituire un elemento per ogni risultato della query raggruppati. A tale scopo, è necessario assicurarsi che si esegue una query su di `DefaultIfEmpty` del raggruppati insieme. Ciò garantisce che gli elementi della raccolta a sinistra del join sono ancora incluse nel risultato della query anche se non hanno risultati corrispondenti dalla raccolta a destra. È possibile aggiungere codice alla query per fornire un valore predefinito quando è presente alcun valore corrispondente dalla raccolta a destra del join.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Per eseguire un Left Outer Join con la clausola Group Join  
  
1.  Aggiungere il codice seguente per il `Module1` modulo nel progetto per vedere gli esempi di un left outer join raggruppato e non separate.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Eseguire un Join utilizzando una chiave composta  
 È possibile utilizzare il `And` parola chiave in un `Join` o `Group Join` clausola per identificare più campi chiave da utilizzare quando si confrontano i valori dalle raccolte da includere. Il `And` la parola chiave specifica tutti specificati campi chiave devono corrispondere per gli elementi da unire.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Per eseguire un Join utilizzando una chiave composta  
  
1.  Aggiungere il codice seguente per il `Module1` modulo nel progetto per vedere gli esempi di join che utilizza una chiave composta.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a>Eseguire il codice  
  
#### <a name="to-add-code-to-run-the-examples"></a>Per aggiungere il codice per eseguire gli esempi  
  
1.  Sostituire il `Sub Main` nel `Module1` modulo nel progetto con il codice seguente per eseguire gli esempi in questo argomento.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  Premere F5 per eseguire gli esempi.  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md)  
 [Clausola Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Clausola From](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [Query](../../../../visual-basic/language-reference/queries/queries.md)  
 [Trasformazioni dati con LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)

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
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Procedura: combinare dati con LINQ utilizzando join (Visual Basic)
Visual Basic fornisce le `Join` `Group Join` clausole di query e per consentire di combinare il contenuto di più raccolte in base ai valori comuni tra le raccolte. Questi valori sono noti come valori *chiave* . Gli sviluppatori che hanno familiarità con i concetti di database relazionale riconoscono la `Join` clausola come Inner join e la `Group Join` clausola come, in realtà, un left outer join.  
  
 Negli esempi di questo argomento vengono illustrati alcuni modi per combinare i dati utilizzando `Join` le `Group Join` clausole di query e.  
  
## <a name="create-a-project-and-add-sample-data"></a>Creare un progetto e aggiungere dati di esempio  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Per creare un progetto che contiene dati e tipi di esempio  
  
1. Per eseguire gli esempi in questo argomento, aprire Visual Studio e aggiungere un nuovo progetto di applicazione console Visual Basic. Fare doppio clic sul file Module1. vb creato da Visual Basic.  
  
2. Negli esempi di questo argomento vengono usati `Person` i `Pet` tipi e e i dati dell'esempio di codice seguente. Copiare questo codice nel modulo predefinito `Module1` creato da Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Eseguire un inner join usando la clausola join  
 Un INNER JOIN combina i dati di due raccolte. Sono inclusi gli elementi per i quali corrispondono i valori di chiave specificati. Tutti gli elementi di una raccolta che non dispongono di un elemento corrispondente nell'altra raccolta vengono esclusi.  
  
 In Visual Basic LINQ fornisce due opzioni per l'esecuzione di un INNER JOIN, ovvero un join implicito e un join esplicito.  
  
 Un join implicito specifica le raccolte da unire in una `From` clausola e identifica i campi chiave corrispondenti in una `Where` clausola. Visual Basic unisce in modo implicito le due raccolte in base ai campi chiave specificati.  
  
 È possibile specificare un join esplicito usando la `Join` clausola quando si desidera essere specifici dei campi chiave da usare nel join. In questo caso, `Where` è ancora possibile utilizzare una clausola per filtrare i risultati della query.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Per eseguire un inner join tramite la clausola join  
  
1. Aggiungere il codice seguente al `Module1` modulo nel progetto per visualizzare esempi di Inner join impliciti ed espliciti.  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Eseguire un left outer join usando la clausola Group Join  
 Un LEFT OUTER JOIN include tutti gli elementi della raccolta di sinistra del join e solo i valori corrispondenti dalla raccolta di destra del join. Tutti gli elementi della raccolta di destra del join che non dispongono di un elemento corrispondente nell'insieme di sinistra vengono esclusi dal risultato della query.  
  
 La `Group Join` clausola esegue, in effetti, un left outer join. La differenza tra ciò che è in genere noto come LEFT OUTER JOIN e la `Group Join` clausola restituita dalla clausola è che la `Group Join` clausola raggruppa i risultati della raccolta di destra del join per ogni elemento nella raccolta di sinistra. In un database relazionale, un LEFT OUTER JOIN restituisce un risultato non raggruppato in cui ogni elemento nel risultato della query contiene elementi corrispondenti di entrambe le raccolte nel join. In questo caso, gli elementi della raccolta di sinistra del join vengono ripetuti per ogni elemento corrispondente dalla raccolta di destra. Quando si completa la procedura successiva, verrà visualizzato questo aspetto.  
  
 È possibile recuperare i risultati di una `Group Join` query come risultato non raggruppato estendendo la query in modo da restituire un elemento per ogni risultato della query raggruppata. A tale scopo, è necessario assicurarsi di eseguire una query sul `DefaultIfEmpty` metodo della raccolta raggruppata. In questo modo si garantisce che gli elementi della raccolta di sinistra del join siano ancora inclusi nel risultato della query anche se non hanno risultati corrispondenti dalla raccolta di destra. È possibile aggiungere codice alla query per fornire un valore di risultato predefinito quando non esiste alcun valore corrispondente dalla raccolta di destra del join.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Per eseguire un left outer join tramite la clausola Group Join  
  
1. Aggiungere il codice seguente al `Module1` modulo nel progetto per visualizzare esempi di un left outer join raggruppato e di un left outer join non raggruppato.  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Eseguire un join usando una chiave composta  
 È possibile usare la `And` parola chiave in `Join` una `Group Join` clausola o per identificare più campi chiave da usare quando si corrispondono ai valori delle raccolte da unire. La `And` parola chiave specifica che tutti i campi chiave specificati devono corrispondere per gli elementi da unire.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Per eseguire un join utilizzando una chiave composta  
  
1. Aggiungere il codice seguente al `Module1` modulo nel progetto per visualizzare esempi di un join che usa una chiave composta.  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a>Eseguire il codice  
  
#### <a name="to-add-code-to-run-the-examples"></a>Per aggiungere codice per eseguire gli esempi  
  
1. Sostituire `Sub Main` nel modulo del `Module1` progetto con il codice seguente per eseguire gli esempi in questo argomento.  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. Premere F5 per eseguire gli esempi.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ](index.md)
- [Introduzione a LINQ in Visual Basic](introduction-to-linq.md)
- [Clausola join](../../../language-reference/queries/join-clause.md)
- [Clausola Group Join](../../../language-reference/queries/group-join-clause.md)
- [Clausola from](../../../language-reference/queries/from-clause.md)
- [Clausola WHERE](../../../language-reference/queries/where-clause.md)
- [Query](../../../language-reference/queries/index.md)
- [Trasformazioni dati con LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)

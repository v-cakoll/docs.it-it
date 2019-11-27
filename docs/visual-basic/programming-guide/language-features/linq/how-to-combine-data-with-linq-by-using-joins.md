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
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Procedura: combinare dati con LINQ utilizzando join (Visual Basic)
Visual Basic fornisce le clausole di query `Join` e `Group Join` per consentire di combinare il contenuto di più raccolte in base ai valori comuni tra le raccolte. Questi valori sono noti come valori *chiave* . Gli sviluppatori che hanno familiarità con i concetti di database relazionale riconoscono la clausola `Join` come INNER JOIN e la clausola `Group Join` come, in effetti, un LEFT OUTER JOIN.  
  
 Negli esempi di questo argomento vengono illustrati alcuni modi per combinare i dati utilizzando le clausole di query `Join` e `Group Join`.  
  
## <a name="create-a-project-and-add-sample-data"></a>Creare un progetto e aggiungere dati di esempio  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Per creare un progetto che contiene dati e tipi di esempio  
  
1. Per eseguire gli esempi in questo argomento, aprire Visual Studio e aggiungere un nuovo progetto di applicazione console Visual Basic. Fare doppio clic sul file Module1. vb creato da Visual Basic.  
  
2. Negli esempi di questo argomento vengono utilizzati i tipi e i dati `Person` e `Pet` dell'esempio di codice seguente. Copiare questo codice nel modulo predefinito `Module1` creato da Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Eseguire un inner join usando la clausola join  
 Un INNER JOIN combina i dati di due raccolte. Sono inclusi gli elementi per i quali corrispondono i valori di chiave specificati. Tutti gli elementi di una raccolta che non dispongono di un elemento corrispondente nell'altra raccolta vengono esclusi.  
  
 In Visual Basic LINQ fornisce due opzioni per l'esecuzione di un INNER JOIN, ovvero un join implicito e un join esplicito.  
  
 Un join implicito specifica le raccolte da unire in una clausola `From` e identifica i campi chiave corrispondenti in una clausola `Where`. Visual Basic unisce in modo implicito le due raccolte in base ai campi chiave specificati.  
  
 È possibile specificare un join esplicito usando la clausola `Join` quando si vuole essere specifici sui campi chiave da usare nel join. In questo caso, è ancora possibile utilizzare una clausola `Where` per filtrare i risultati della query.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Per eseguire un inner join tramite la clausola join  
  
1. Aggiungere il codice seguente al modulo `Module1` nel progetto per visualizzare esempi di inner join impliciti ed espliciti.  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Eseguire un left outer join usando la clausola Group Join  
 Un LEFT OUTER JOIN include tutti gli elementi della raccolta di sinistra del join e solo i valori corrispondenti dalla raccolta di destra del join. Tutti gli elementi della raccolta di destra del join che non dispongono di un elemento corrispondente nell'insieme di sinistra vengono esclusi dal risultato della query.  
  
 La clausola `Group Join` esegue, in effetti, un LEFT OUTER JOIN. La differenza tra ciò che è in genere noto come LEFT OUTER JOIN e il risultato restituito dalla clausola `Group Join` è che la clausola `Group Join` raggruppa i risultati della raccolta di destra del join per ogni elemento nella raccolta di sinistra. In un database relazionale, un LEFT OUTER JOIN restituisce un risultato non raggruppato in cui ogni elemento nel risultato della query contiene elementi corrispondenti di entrambe le raccolte nel join. In questo caso, gli elementi della raccolta di sinistra del join vengono ripetuti per ogni elemento corrispondente dalla raccolta di destra. Quando si completa la procedura successiva, verrà visualizzato questo aspetto.  
  
 È possibile recuperare i risultati di una query di `Group Join` come risultato non raggruppato estendendo la query in modo da restituire un elemento per ogni risultato della query raggruppata. A tale scopo, è necessario assicurarsi di eseguire una query sul metodo `DefaultIfEmpty` della raccolta raggruppata. In questo modo si garantisce che gli elementi della raccolta di sinistra del join siano ancora inclusi nel risultato della query anche se non hanno risultati corrispondenti dalla raccolta di destra. È possibile aggiungere codice alla query per fornire un valore di risultato predefinito quando non esiste alcun valore corrispondente dalla raccolta di destra del join.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Per eseguire un left outer join tramite la clausola Group Join  
  
1. Aggiungere il codice seguente al modulo `Module1` nel progetto per visualizzare esempi di un left outer join raggruppato e di un left outer join non raggruppato.  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Eseguire un join usando una chiave composta  
 È possibile usare la parola chiave `And` in una clausola `Join` o `Group Join` per identificare più campi chiave da usare quando si corrispondono ai valori delle raccolte da unire. La parola chiave `And` specifica che tutti i campi chiave specificati devono corrispondere per gli elementi da unire.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Per eseguire un join utilizzando una chiave composta  
  
1. Aggiungere il codice seguente al modulo `Module1` nel progetto per visualizzare esempi di un join che usa una chiave composta.  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a>Eseguire il codice  
  
#### <a name="to-add-code-to-run-the-examples"></a>Per aggiungere codice per eseguire gli esempi  
  
1. Sostituire il `Sub Main` nel modulo `Module1` nel progetto con il codice seguente per eseguire gli esempi in questo argomento.  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. Premere F5 per eseguire gli esempi.  
  
## <a name="see-also"></a>Vedere anche

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md)
- [Clausola Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Clausola From](../../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
- [Trasformazioni dati con LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)

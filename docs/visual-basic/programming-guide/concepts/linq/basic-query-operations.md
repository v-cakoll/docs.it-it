---
title: Operazioni di query di base (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
ms.openlocfilehash: 5ca92324dec1d4fa8885a610a6e246640f4a5752
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973028"
---
# <a name="basic-query-operations-visual-basic"></a>Operazioni di query di base (Visual Basic)
In questo argomento fornisce una breve introduzione alla [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] espressioni in Visual Basic e ad alcuni dei tipi di operazioni eseguite in una query tipici. Per altre informazioni, vedere i seguenti argomenti:  
  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Query](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Procedura dettagliata: Scrittura di query in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Specifica l'origine dati (da)  
 In un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, il primo passaggio consiste nello specificare l'origine dati che si desidera eseguire una query. Pertanto, il `From` clausola in una query di verifica sempre per prima. Gli operatori di query selezionano e organizzare i risultati in base al tipo dell'origine.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 Il `From` clausola specifica l'origine dati `customers`e una *variabile di intervallo*, `cust`. La variabile di intervallo è simile a una variabile di iterazione del ciclo, ad eccezione del fatto che in un'espressione di query, si verifica alcuna iterazione effettivo. Quando viene eseguita la query, spesso usando un `For Each` ciclo, la variabile di intervallo viene usato come un riferimento a ogni elemento successivo in `customers`. Poiché il compilatore può dedurre il tipo di `cust`, non è necessario specificarlo in modo esplicito. Per esempi di query scritte con e senza tipizzazione esplicita, vedere [relazioni tra i tipi nelle operazioni di Query (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Per altre informazioni su come usare il `From` clausola in Visual Basic, vedere [clausola From](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtro dei dati (in)  
 L'operazione di query più comune è probabilmente applicando un filtro sotto forma di un'espressione booleana. Quindi, la query restituisce solo gli elementi per cui l'espressione è true. Oggetto `Where` clausola viene utilizzata per eseguire le operazioni di filtraggio. Il filtro consente di specificare quali elementi nell'origine dati da includere nella sequenza risultante. Nell'esempio seguente, sono inclusi solo i clienti che hanno un indirizzo in Londra.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 È possibile usare gli operatori logici, ad esempio `And` e `Or` combinare le espressioni di filtro in un `Where` clausola. Ad esempio, per restituire solo i clienti di Londra e il cui nome è Devon, usare il codice seguente:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Per restituire i clienti di Londra o Parigi, usare il codice seguente:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Per altre informazioni su come usare il `Where` clausola in Visual Basic, vedere [clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Ordinamento dei dati (Order By)  
 Spesso è utile organizzare i dati restituiti in un ordine particolare. Il `Order By` clausola consente di ordinare gli elementi nella sequenza restituita di ordinamento una o più campi specificati. Ad esempio, la query seguente consente di ordinare i risultati in base il `Name` proprietà. Poiché `Name` è una stringa, i dati restituiti verranno ordinati in ordine alfabetico, da A Z.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Per ordinare i risultati in ordine inverso, da Z ad A, usare la clausola `Order By...Descending`. Il valore predefinito è `Ascending` quando non si `Ascending` né `Descending` è specificato.  
  
 Per altre informazioni su come usare il `Order By` clausola in Visual Basic, vedere [clausola Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Selezione dei dati (Select)  
 Il `Select` clausola che specifica il formato e il contenuto di elementi restituiti. Ad esempio, è possibile specificare se i risultati saranno costituiti completa `Customer` oggetti, solo uno `Customer` proprietà, un subset delle proprietà, una combinazione delle proprietà da varie origini dati o un nuovo tipo di risultati basato su un calcolo. Quando la clausola `Select` produce un valore diverso da una copia dell'elemento d'origine, l'operazione viene chiamata *proiezione*.  
  
 Per recuperare un insieme costituito da completa `Customer` oggetti, selezionare la variabile di intervallo se stessa:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Se un `Customer` istanza è un oggetto di grandi dimensioni contenente molti campi, e tutto ciò che si desidera recuperare è il nome, è possibile selezionare `cust.Name`, come illustrato nell'esempio seguente. L'inferenza del tipo locale riconosce che questa operazione modificherà il tipo di risultato da una raccolta di `Customer` oggetti da una raccolta di stringhe.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Per selezionare più campi dall'origine dati, sono disponibili due opzioni:  
  
-   Nel `Select` clausola, specificare i campi da includere nel risultato. Il compilatore verrà definiti un tipo anonimo che include i campi come le relative proprietà. Per altre informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Poiché gli elementi restituiti nell'esempio seguente sono istanze di un tipo anonimo, è possibile fare riferimento al tipo di base al nome in un' posizione nel codice. Il nome definito dal compilatore per il tipo contiene caratteri non validi in normale codice di Visual Basic. Nell'esempio seguente, gli elementi nella raccolta restituita dalla query in `londonCusts4` sono istanze di un tipo anonimo  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     -oppure-  
  
-   Definire un tipo denominato che contiene i campi specifici che si desidera includere nel risultato e creare e inizializzare istanze del tipo nel `Select` clausola. Usare questa opzione solo se è necessario utilizzare esterne alla raccolta in cui vengono restituiti i singoli risultati o se è necessario passarli come parametri nelle chiamate al metodo. Il tipo di `londonCusts5` nell'esempio seguente è IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Per altre informazioni su come usare il `Select` clausola in Visual Basic, vedere [clausola Select](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Dati unita tramite join (Join e Join di gruppo)  
 È possibile combinare più di un'origine dati nel `From` clausola in diversi modi. Ad esempio, il codice seguente usa due origini dati e in modo implicito combina le proprietà da entrambi gli elementi nel risultato. La query Seleziona gli studenti il cui cognome iniziano con una vocale.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
>  È possibile eseguire questo codice con l'elenco degli studenti creati in [come: Creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 Il `Join` parola chiave è equivalente a un `INNER JOIN` in SQL. Combina due raccolte in base ai valori chiave corrispondenti tra gli elementi nelle due raccolte. La query restituisce tutto o parte degli elementi della raccolta che hanno valori della chiave corrispondenti. Ad esempio, il codice seguente consente di duplicare l'azione di join implicite precedente.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join` Combina le raccolte in un'unica raccolta gerarchica, come un `LEFT JOIN` in SQL. Per altre informazioni, vedere [clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md) e [clausola Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Raggruppamento dei dati (Raggruppa per)  
 È possibile aggiungere un `Group By` clausola per raggruppare gli elementi in un risultato della query in base a uno o più campi degli elementi. Ad esempio, il codice seguente Raggruppa gli studenti per anno di classe.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Se si esegue questo codice utilizzando l'elenco degli studenti creati in [come: Creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), l'output di `For Each` istruzione è:  
  
 Anno: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, Lance  
  
 Anno: Senior  
  
 Omelchenko, Svetlana  
  
 Osada, Michiko  
  
 Fakhouri, Fadi  
  
 Feng, Hanying  
  
 Adams, Terry  
  
 Anno: Seconda superiore  
  
 Mortensen, Sven  
  
 Garcia, Cesar  
  
 La variazione illustrata nel codice seguente Ordina gli anni di classe e quindi ordini gli studenti all'interno di ogni anno in base al cognome.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Per altre informazioni sulle `Group By`, vedere [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Collections.Generic.IEnumerable%601>
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
- [Panoramica degli operatori query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)

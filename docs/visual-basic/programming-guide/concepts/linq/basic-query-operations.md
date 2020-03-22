---
title: Operazioni di query di base
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
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266378"
---
# <a name="basic-query-operations-visual-basic"></a>Operazioni di query di base (Visual Basic)
In questo argomento viene fornita una breve introduzione alle espressioni LINQ (Language-Integrated Query) in Visual Basic e ad alcuni dei tipi tipici di operazioni eseguite in una query. Per altre informazioni, vedere gli argomenti seguenti:  
  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Query](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Procedura dettagliata: Scrittura delle query in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Specifica dell'origine dati (Da)  
 In una query LINQ, il primo passaggio consiste nello specificare l'origine dati su cui si desidera eseguire la query. Pertanto, `From` la clausola in una query viene sempre prima. Gli operatori di query selezionano e modellano il risultato in base al tipo di origine.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 La `From` clausola specifica l'origine dati `customers`, `cust`, e una variabile di *intervallo*, . La variabile di intervallo è simile a una variabile di iterazione del ciclo, ad eccezione del fatto che in un'espressione di query non si verifica alcuna iterazione effettiva. Quando la query viene eseguita, `For Each` spesso utilizzando un ciclo, la variabile `customers`di intervallo funge da riferimento per ogni elemento successivo in . Poiché il compilatore può dedurre il tipo di `cust`, non è necessario specificarlo in modo esplicito. Per esempi di query scritte con e senza tipi di digitazione esplicita, vedere Relazioni tra tipi nelle operazioni di [query (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Per ulteriori informazioni sull'utilizzo della `From` clausola in Visual Basic, vedere [Clausola From](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtraggio dei dati (Dove)  
 Probabilmente l'operazione di query più comune consiste nell'applicazione di un filtro sotto forma di espressione booleana. La query restituisce quindi solo gli elementi per i quali l'espressione è vera. Una `Where` clausola viene utilizzata per eseguire il filtro. Il filtro specifica quali elementi nell'origine dati includere nella sequenza risultante. Nell'esempio seguente vengono inclusi solo i clienti che dispongono di un indirizzo a Londra.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 È possibile utilizzare operatori `And` `Or` logici, ad `Where` esempio e per combinare espressioni di filtro in una clausola. Ad esempio, per restituire solo i clienti che provengono da Londra e il cui nome è Devon, utilizzare il codice seguente:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 Per restituire clienti da Londra o Parigi, utilizzare il codice seguente:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 Per ulteriori informazioni sull'utilizzo della `Where` clausola in Visual Basic, vedere [Clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Ordinare i dati (Ordina per)  
 Spesso è conveniente ordinare i dati restituiti in un ordine particolare. La `Order By` clausola farà sì che gli elementi nella sequenza restituita vengano ordinati in base a uno o più campi specificati. Ad esempio, la query seguente ordina `Name` i risultati in base alla proprietà. Poiché `Name` è una stringa, i dati restituiti verranno ordinati alfabeticamente, dalla A alla .  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Per ordinare i risultati in ordine inverso, da Z ad A, usare la clausola `Order By...Descending`. Il valore `Ascending` predefinito `Ascending` `Descending` è quando non viene specificato né.  
  
 Per ulteriori informazioni sull'utilizzo della `Order By` clausola in Visual Basic, vedere [Clausola Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Selezione dei dati (seleziona)  
 La `Select` clausola specifica il formato e il contenuto degli elementi restituiti. Ad esempio, è possibile specificare se `Customer` i risultati `Customer` saranno costituiti da oggetti completi, solo una proprietà, un subset di proprietà, una combinazione di proprietà da varie origini dati o un nuovo tipo di risultato basato su un calcolo. Quando la clausola `Select` produce un valore diverso da una copia dell'elemento d'origine, l'operazione viene chiamata *proiezione*.  
  
 Per recuperare una raccolta `Customer` costituita da oggetti completi, selezionare la variabile di intervallo stessa:To retrieve a collection that consists of complete objects, select the range variable itself:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Se `Customer` un'istanza è un oggetto di grandi dimensioni con molti campi e `cust.Name`tutto ciò che si desidera recuperare è il nome, è possibile selezionare , come illustrato nell'esempio seguente. L'inferenza del tipo locale riconosce che in `Customer` questo modo il tipo di risultato viene modificato da una raccolta di oggetti a una raccolta di stringhe.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Per selezionare più campi dall'origine dati, sono disponibili due opzioni:  
  
- Nella `Select` clausola specificare i campi che si desidera includere nel risultato. Il compilatore definirà un tipo anonimo con tali campi come proprietà. Per ulteriori informazioni, vedere [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Poiché gli elementi restituiti nell'esempio seguente sono istanze di un tipo anonimo, non è possibile fare riferimento al tipo in base al nome in un altro punto del codice. Il nome designato dal compilatore per il tipo contiene caratteri non validi nel normale codice Visual Basic. Nell'esempio seguente, gli elementi nella raccolta restituita `londonCusts4` dalla query in sono istanze di un tipo anonimo  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     -oppure-  
  
- Definire un tipo denominato che contiene i campi specifici che si desidera includere nel `Select` risultato e creare e inizializzare istanze del tipo nella clausola. Utilizzare questa opzione solo se è necessario utilizzare singoli risultati all'esterno della raccolta in cui vengono restituiti o se è necessario passarli come parametri nelle chiamate al metodo. Il tipo `londonCusts5` di nell'esempio seguente è IEnumerable(Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Per ulteriori informazioni sull'utilizzo della `Select` clausola in Visual Basic, vedere [Clausola Select](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Unione di dati (Join e Group Join)  
 È possibile combinare più di `From` un'origine dati nella clausola in diversi modi. Ad esempio, il codice seguente usa due origini dati e combina in modo implicito le proprietà di entrambe nel risultato. La query seleziona gli studenti il cui cognome inizia con una vocale.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> È possibile eseguire questo codice con l'elenco di studenti creato in [Procedura: creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 La `Join` parola chiave `INNER JOIN` è equivalente a un in SQL. Combina due raccolte in base ai valori chiave corrispondenti tra gli elementi nelle due raccolte. La query restituisce tutti o parte degli elementi della raccolta con valori di chiave corrispondenti. Ad esempio, il codice seguente duplica l'azione del join implicito precedente.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join`combina le raccolte in un'unica `LEFT JOIN` raccolta gerarchica, proprio come un in SQL. Per ulteriori informazioni, vedere [Clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md) e [Clausola Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Raggruppamento dei dati (Raggruppa per)  
 È possibile `Group By` aggiungere una clausola per raggruppare gli elementi in un risultato della query in base a uno o più campi degli elementi. Ad esempio, il codice seguente raggruppa gli studenti in base all'anno della classe.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Se si esegue questo codice utilizzando l'elenco di studenti creato in [Procedura: Creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), l'output dell'istruzione `For Each` è:  
  
 Anno: Junior  
  
 Tucker  
  
 Garcia  
  
 Garcia  
  
 Tucker  
  
 Anno: Senior  
  
 Omelchenko  
  
 Osada  
  
 Fakhouri  
  
 Feng  
  
 Adams  
  
 Anno: Matricola  
  
 Mortensen  
  
 Garcia  
  
 La variazione mostrata nel codice seguente ordina gli anni della classe, quindi ordina gli studenti all'interno di ogni anno in base al cognome.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Per ulteriori `Group By`informazioni sulla [clausola Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic.IEnumerable%601>
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
- [Panoramica degli operatori query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)

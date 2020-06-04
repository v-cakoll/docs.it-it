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
ms.openlocfilehash: 92ac5beb70526795eb140bd794e47981cebfea93
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410916"
---
# <a name="basic-query-operations-visual-basic"></a>Operazioni di query di base (Visual Basic)
In questo argomento viene fornita una breve introduzione alle espressioni LINQ (Language-Integrated Query) in Visual Basic e ad alcuni tipi tipici di operazioni eseguite in una query. Per altre informazioni, vedere gli argomenti seguenti:  
  
 [Introduzione a LINQ in Visual Basic](../../language-features/linq/introduction-to-linq.md)  
  
 [Query](../../../language-reference/queries/index.md)  
  
 [Procedura dettagliata: Scrittura delle query in Visual Basic](walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Specifica dell'origine dati (da)  
 In una query LINQ, il primo passaggio consiste nel specificare l'origine dati su cui si desidera eseguire la query. Pertanto, la `From` clausola in una query viene sempre eseguita per prima. Gli operatori di query selezionano e formano il risultato in base al tipo di origine.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 La `From` clausola specifica l'origine dati, `customers` e una *variabile di intervallo*, `cust` . La variabile di intervallo è come una variabile di iterazione del ciclo, ad eccezione del fatto che in un'espressione di query non si verifica alcuna iterazione effettiva. Quando la query viene eseguita spesso usando un `For Each` ciclo, la variabile di intervallo funge da riferimento a ogni elemento successivo in `customers` . Poiché il compilatore può dedurre il tipo di `cust`, non è necessario specificarlo in modo esplicito. Per esempi di query scritte con e senza tipizzazione esplicita, vedere relazioni tra i [tipi nelle operazioni di query (Visual Basic)](type-relationships-in-query-operations.md).  
  
 Per ulteriori informazioni su come utilizzare la `From` clausola in Visual Basic, vedere [clausola from](../../../language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Filtraggio dei dati (dove)  
 Probabilmente l'operazione di query più comune è l'applicazione di un filtro sotto forma di espressione booleana. La query restituisce quindi solo gli elementi per i quali l'espressione è true. Una `Where` clausola viene utilizzata per eseguire il filtro. Il filtro specifica quali elementi dell'origine dati includere nella sequenza risultante. Nell'esempio seguente vengono inclusi solo i clienti che hanno un indirizzo a Londra.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 È possibile utilizzare operatori logici come `And` e `Or` per combinare le espressioni di filtro in una `Where` clausola. Ad esempio, per restituire solo i clienti che si trovano a Londra e il cui nome è Devon, usare il codice seguente:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 Per restituire i clienti di Londra o Parigi, usare il codice seguente:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 Per ulteriori informazioni su come utilizzare la `Where` clausola in Visual Basic, vedere [clausola WHERE](../../../language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Ordinamento dei dati (order by)  
 Spesso è utile ordinare i dati restituiti in un ordine specifico. La `Order By` clausola provocherà l'ordinamento degli elementi nella sequenza restituita in base a un campo o a campi specificati. La query seguente, ad esempio, Ordina i risultati in base alla `Name` Proprietà. Poiché `Name` è una stringa, i dati restituiti verranno ordinati alfabeticamente, da a a Z.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Per ordinare i risultati in ordine inverso, da Z ad A, usare la clausola `Order By...Descending`. Il valore predefinito è `Ascending` quando né `Ascending` né `Descending` viene specificato.  
  
 Per ulteriori informazioni su come utilizzare la `Order By` clausola in Visual Basic, vedere [clausola ORDER BY](../../../language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Selezione dei dati (selezione)  
 La `Select` clausola specifica il form e il contenuto degli elementi restituiti. È ad esempio possibile specificare se i risultati sono costituiti da `Customer` oggetti completi, una sola `Customer` proprietà, un subset di proprietà, una combinazione di proprietà di varie origini dati o un nuovo tipo di risultato basato su un calcolo. Quando la clausola `Select` produce un valore diverso da una copia dell'elemento d'origine, l'operazione viene chiamata *proiezione*.  
  
 Per recuperare una raccolta costituita da `Customer` oggetti completi, selezionare la variabile di intervallo stessa:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Se un' `Customer` istanza è un oggetto di grandi dimensioni con molti campi e si desidera recuperare solo il nome, è possibile selezionare `cust.Name` , come illustrato nell'esempio seguente. L'inferenza del tipo locale riconosce che questo modifica il tipo di risultato da una raccolta di `Customer` oggetti in una raccolta di stringhe.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Per selezionare più campi dall'origine dati, sono disponibili due opzioni:  
  
- Nella `Select` clausola specificare i campi che si desidera includere nel risultato. Il compilatore definirà un tipo anonimo che ha tali campi come proprietà. Per ulteriori informazioni, vedere [tipi anonimi](../../language-features/objects-and-classes/anonymous-types.md).  
  
     Poiché gli elementi restituiti nell'esempio seguente sono istanze di un tipo anonimo, non è possibile fare riferimento al tipo in base al nome in un'altra parte del codice. Il nome designato dal compilatore per il tipo contiene caratteri non validi nel codice di Visual Basic normale. Nell'esempio seguente, gli elementi della raccolta restituiti dalla query in `londonCusts4` sono istanze di un tipo anonimo  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     -oppure-  
  
- Definire un tipo denominato che contiene i campi specifici che si desidera includere nel risultato, quindi creare e inizializzare istanze del tipo nella `Select` clausola. Usare questa opzione solo se è necessario usare singoli risultati al di fuori della raccolta in cui vengono restituiti o se è necessario passarli come parametri nelle chiamate al metodo. Il tipo di `londonCusts5` nell'esempio seguente è IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Per ulteriori informazioni su come utilizzare la `Select` clausola in Visual Basic, vedere [clausola SELECT](../../../language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Unione di dati (join e gruppo join)  
 È possibile combinare più origini dati nella `From` clausola in diversi modi. Il codice seguente, ad esempio, usa due origini dati e combina in modo implicito le proprietà da entrambe nel risultato. La query seleziona gli studenti i cui cognomi iniziano con una vocale.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> È possibile eseguire questo codice con l'elenco degli studenti creati in [procedura: creare un elenco di elementi](how-to-create-a-list-of-items.md).  
  
 La `Join` parola chiave equivale a un oggetto `INNER JOIN` in SQL. Combina due raccolte in base ai valori di chiave corrispondenti tra gli elementi nelle due raccolte. La query restituisce tutti gli elementi della raccolta che hanno valori di chiave corrispondenti. Il codice seguente, ad esempio, Duplica l'azione del precedente join implicito.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join`combina le raccolte in un'unica raccolta gerarchica, proprio come `LEFT JOIN` in SQL. Per ulteriori informazioni, vedere clausola [join](../../../language-reference/queries/join-clause.md) e [clausola Group Join](../../../language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Raggruppamento di dati (Group by)  
 È possibile aggiungere una `Group By` clausola per raggruppare gli elementi del risultato di una query in base a uno o più campi degli elementi. Il codice seguente, ad esempio, raggruppa gli studenti per classe Year.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Se si esegue questo codice usando l'elenco degli studenti creati in [procedura: creare un elenco di elementi](how-to-create-a-list-of-items.md), l'output dell' `For Each` istruzione è:  
  
 Anno: Junior  
  
 Tucker, Michael  
  
 Garcia, Hugo  
  
 Garcia, Debra  
  
 Tucker, Lance  
  
 Anno: Senior  
  
 Omelchenko, Svetlana  
  
 Osada, il  
  
 Fattori, Fadi  
  
 Feng, Khaliding  
  
 Adams, Terry  
  
 Anno: aggiornamento  
  
 Mortensen, Sven  
  
 Garcia, Cesar  
  
 La variazione mostrata nel codice seguente ordina la classe years e quindi Ordina gli studenti entro ogni anno in base al cognome.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Per ulteriori informazioni su `Group By` , vedere [clausola Group by](../../../language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Collections.Generic.IEnumerable%601>
- [Introduzione a LINQ in Visual Basic](getting-started-with-linq.md)
- [Query](../../../language-reference/queries/index.md)
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)
- [LINQ](../../language-features/linq/index.md)

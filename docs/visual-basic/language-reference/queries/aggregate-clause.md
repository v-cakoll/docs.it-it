---
title: Clausola Aggregate (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 1db4b7fdcf9c8a38c2c49eca9d874eccea90ab1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="aggregate-clause-visual-basic"></a>Clausola Aggregate (Visual Basic)
Applica uno o più funzioni di aggregazione a una raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`element`|Obbligatorio. Variabile utilizzata per scorrere gli elementi della raccolta.|  
|`type`|Facoltativo. Tipo di `element`. Se viene specificato alcun tipo, il tipo di `element` viene dedotto dal `collection`.|  
|`collection`|Obbligatorio. Fa riferimento alla raccolta su cui operare.|  
|`clause`|Facoltativo. Uno o più clausole di query, ad esempio un `Where` clausola per perfezionare il risultato della query per applicare la clausola di aggregazione o le clausole di.|  
|`expressionList`|Obbligatorio. Uno o più delimitato da virgole espressioni che identificano una funzione di aggregazione da applicare alla raccolta. È possibile applicare un alias a una funzione di aggregazione per specificare un nome di membro per il risultato della query. Se non viene specificato alcun alias, viene utilizzato il nome della funzione di aggregazione. Per esempi, vedere la sezione sulle funzioni di aggregazione più avanti in questo argomento.|  
  
## <a name="remarks"></a>Note  
 Il `Aggregate` clausola può essere utilizzata per includere funzioni di aggregazione nelle query. Funzioni di aggregazione eseguono controlli e calcoli su un set di valori e restituiscono un singolo valore. Il valore calcolato è possibile accedere utilizzando un membro del tipo di risultato della query. Le funzioni di aggregazione standard che è possibile utilizzare il `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, e `Sum` funzioni. Queste funzioni sono note agli sviluppatori che hanno familiarità con le aggregazioni in SQL. Vengono descritte nella sezione seguente di questo argomento.  
  
 Il risultato di una funzione di aggregazione è incluso nel risultato della query come un campo del tipo di risultato della query. È possibile fornire un alias per il risultato della funzione di aggregazione specificare il nome del membro del tipo di risultato di query che conterrà il valore di aggregazione. Se non viene specificato alcun alias, viene utilizzato il nome della funzione di aggregazione.  
  
 Il `Aggregate` clausola può iniziare una query, o può essere inclusa come una clausola aggiuntiva in una query. Se il `Aggregate` clausola inizia una query, il risultato è un singolo valore che rappresenta il risultato della funzione di aggregazione specificato nella `Into` clausola. Se viene specificata più di una funzione di aggregazione nel `Into` clausola, la query restituisce un solo tipo con una proprietà separata per fare riferimento al risultato di ogni funzione di aggregazione nel `Into` clausola. Se il `Aggregate` clausola è inclusa come una clausola aggiuntiva in una query, il tipo restituito nella raccolta di query avrà una proprietà separata per fare riferimento al risultato di ogni funzione di aggregazione nel `Into` clausola.  
  
## <a name="aggregate-functions"></a>Funzioni di aggregazione  
 L'elenco seguente descrive le funzioni di aggregazione standard che possono essere utilizzate con il `Aggregate` clausola.  
  
|Funzione|Descrizione|  
|---|---|  
|`All`|Restituisce `true` se tutti gli elementi nella raccolta soddisfano una condizione specificata; in caso contrario restituisce `false`. Di seguito è riportato un esempio:<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]|  
|`Any`|Restituisce `true` se qualsiasi elemento nella raccolta soddisfa una condizione specificata; in caso contrario restituisce `false`. Di seguito è riportato un esempio:<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]|  
|`Average`|Calcola la media di tutti gli elementi nella raccolta, o calcola l'espressione fornita per tutti gli elementi nella raccolta. Di seguito è riportato un esempio:<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]|  
|`Count`|Conta il numero di elementi nella raccolta. È possibile fornire un parametro facoltativo `Boolean` espressione per calcolare solo il numero di elementi nella raccolta che soddisfano una condizione. Di seguito è riportato un esempio:<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]|  
|`Group`|Fa riferimento ai risultati della query che vengono raggruppati in seguito a un `Group By` o `Group Join` clausola. Il `Group` è valida solo nella funzione di `Into` clausola di un `Group By` o `Group Join` clausola. Per ulteriori informazioni ed esempi, vedere [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) e [clausola Join gruppo](../../../visual-basic/language-reference/queries/group-join-clause.md).|  
|`LongCount`|Conta il numero di elementi nella raccolta. È possibile fornire un parametro facoltativo `Boolean` espressione per calcolare solo il numero di elementi nella raccolta che soddisfano una condizione. Restituisce il risultato come un `Long`. Per un esempio, vedere il `Count` funzione di aggregazione.|  
|`Max`|Calcola il valore massimo dalla raccolta, o calcola un'espressione fornita per tutti gli elementi nella raccolta. Di seguito è riportato un esempio:<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]|  
|`Min`|Calcola il valore minimo dalla raccolta, o calcola un'espressione fornita per tutti gli elementi nella raccolta. Di seguito è riportato un esempio:<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]|  
|`Sum`|Calcola la somma di tutti gli elementi nella raccolta, o calcola un'espressione fornita per tutti gli elementi nella raccolta. Di seguito è riportato un esempio:<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]|  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come utilizzare il `Aggregate` clausola per applicare funzioni di aggregazione per un risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Creazione di funzioni di aggregazione definita dall'utente  
 È possibile includere funzioni di aggregazione personalizzate in un'espressione di query mediante l'aggiunta di metodi di estensione per il <xref:System.Collections.Generic.IEnumerable%601> tipo. Il metodo personalizzato può quindi eseguire un calcolo o l'operazione sulla raccolta enumerabile che ha fatto riferimento alla funzione di aggregazione. Per altre informazioni sui metodi di estensione, vedere [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Ad esempio, l'esempio di codice seguente viene illustrata una funzione di aggregazione personalizzata che calcola il valore mediano di una raccolta di numeri. Ci sono due overload di `Median` metodo di estensione. Il primo overload accetta come input, una raccolta di tipo `IEnumerable(Of Double)`. Se il `Median` funzione di aggregazione viene chiamata per un campo di query di tipo `Double`, questo metodo verrà chiamato. Il secondo overload di `Median` metodo può essere passato a qualsiasi tipo generico. L'overload generico del `Median` metodo accetta un secondo parametro che fa riferimento il `Func(Of T, Double)` un'espressione lambda a un valore per un tipo (da una raccolta) il progetto come il valore corrispondente di tipo `Double`. Il calcolo del valore mediano per l'altro overload di delega quindi la `Median` metodo. Per altre informazioni sulle espressioni lambda, vedere [Espressioni lambda in C++](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 Nell'esempio di codice riportato di seguito viene illustrato esempio query che chiamano il `Median` funzione in una raccolta di tipo di aggregazione `Integer`e una raccolta di tipo `Double`. La query che chiama il `Median` funzione per la raccolta del tipo di aggregazione `Double` chiama l'overload di `Median` metodo che accetta come input, una raccolta di tipo `Double`. La query che chiama il `Median` funzione per la raccolta del tipo di aggregazione `Integer` chiama l'overload generico del `Median` metodo.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Clausola Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)

---
title: Clausola Aggregate
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 5aa4b9afea4b6b26b853d4f4f6d4c8db08554e19
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350876"
---
# <a name="aggregate-clause-visual-basic"></a>Clausola Aggregate (Visual Basic)
Applica una o più funzioni di aggregazione a una raccolta.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`element`|Obbligatoria. Variabile utilizzata per scorrere gli elementi della raccolta.|  
|`type`|Facoltativa. Tipo di `element`. Se non viene specificato alcun tipo, il tipo di `element` viene dedotto da `collection`.|  
|`collection`|Obbligatoria. Fa riferimento alla raccolta su cui operare.|  
|`clause`|Facoltativa. Una o più clausole di query, ad esempio una clausola `Where`, per perfezionare il risultato della query in modo da applicare la clausola o le clausole Aggregate a.|  
|`expressionList`|Obbligatoria. Una o più espressioni delimitate da virgole che identificano una funzione di aggregazione da applicare alla raccolta. È possibile applicare un alias a una funzione di aggregazione per specificare il nome di un membro per il risultato della query. Se non viene specificato alcun alias, viene usato il nome della funzione di aggregazione. Per esempi, vedere la sezione sulle funzioni di aggregazione più avanti in questo argomento.|  
  
## <a name="remarks"></a>Note  
 È possibile utilizzare la clausola `Aggregate` per includere funzioni di aggregazione nelle query. Le funzioni di aggregazione eseguono controlli e calcoli su un set di valori e restituiscono un singolo valore. È possibile accedere al valore calcolato utilizzando un membro del tipo di risultato della query. Le funzioni di aggregazione standard che è possibile utilizzare sono le funzioni `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`e `Sum`. Queste funzioni hanno familiarità con gli sviluppatori che hanno familiarità con le aggregazioni di SQL. Sono descritti nella sezione seguente di questo argomento.  
  
 Il risultato di una funzione di aggregazione viene incluso nel risultato della query come campo del tipo di risultato della query. È possibile fornire un alias per il risultato della funzione di aggregazione per specificare il nome del membro del tipo di risultato della query che conterrà il valore di aggregazione. Se non viene specificato alcun alias, viene usato il nome della funzione di aggregazione.  
  
 La clausola `Aggregate` può iniziare una query oppure può essere inclusa come clausola aggiuntiva in una query. Se la clausola `Aggregate` inizia una query, il risultato è un singolo valore che rappresenta il risultato della funzione di aggregazione specificata nella clausola `Into`. Se nella clausola `Into` viene specificata più di una funzione di aggregazione, la query restituisce un singolo tipo con una proprietà separata per fare riferimento al risultato di ogni funzione di aggregazione nella clausola `Into`. Se la clausola `Aggregate` viene inclusa come clausola aggiuntiva in una query, il tipo restituito nella raccolta di query avrà una proprietà separata per fare riferimento al risultato di ogni funzione di aggregazione nella clausola `Into`.  
  
## <a name="aggregate-functions"></a>Funzioni di aggregazione

Di seguito sono riportate le funzioni di aggregazione standard che è possibile utilizzare con la clausola `Aggregate`.  
  
### <a name="all"></a>Tutte

Restituisce `true` se tutti gli elementi della raccolta soddisfano una condizione specificata. in caso contrario, restituisce `false`. Di seguito si riporta un esempio.

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>Any

Restituisce `true` se un elemento della raccolta soddisfa una condizione specificata. in caso contrario, restituisce `false`. Di seguito si riporta un esempio.

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Media

Calcola la media di tutti gli elementi della raccolta o calcola un'espressione fornita per tutti gli elementi della raccolta. Di seguito si riporta un esempio.

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Conteggio

Conta il numero di elementi nella raccolta. È possibile specificare un'espressione `Boolean` facoltativa per contare solo il numero di elementi della raccolta che soddisfano una condizione. Di seguito si riporta un esempio.

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Gruppo

Fa riferimento ai risultati della query raggruppati come risultato di una clausola `Group By` o `Group Join`. La funzione `Group` è valida solo nella clausola `Into` di una clausola `Group By` o `Group Join`. Per ulteriori informazioni ed esempi, vedere clausola [Group by](../../../visual-basic/language-reference/queries/group-by-clause.md) e [clausola Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md).

### <a name="longcount"></a>LongCount

Conta il numero di elementi nella raccolta. È possibile specificare un'espressione `Boolean` facoltativa per contare solo il numero di elementi della raccolta che soddisfano una condizione. Restituisce il risultato come `Long`. Per un esempio, vedere la funzione di aggregazione `Count`.

### <a name="max"></a>Max

Calcola il valore massimo dalla raccolta oppure calcola un'espressione fornita per tutti gli elementi della raccolta. Di seguito si riporta un esempio.

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>Min

Calcola il valore minimo dalla raccolta oppure calcola un'espressione fornita per tutti gli elementi della raccolta. Di seguito si riporta un esempio.

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>Sum

Calcola la somma di tutti gli elementi della raccolta o calcola un'espressione fornita per tutti gli elementi della raccolta. Di seguito si riporta un esempio.

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>Esempio  

Nell'esempio seguente viene illustrato come utilizzare la clausola `Aggregate` per applicare funzioni di aggregazione al risultato di una query.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Creazione di funzioni di aggregazione definite dall'utente

 È possibile includere funzioni di aggregazione personalizzate in un'espressione di query aggiungendo metodi di estensione al tipo di <xref:System.Collections.Generic.IEnumerable%601>. Il metodo personalizzato può quindi eseguire un calcolo o un'operazione sulla raccolta enumerabile che ha fatto riferimento alla funzione di aggregazione. Per altre informazioni sui metodi di estensione, vedere [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Nell'esempio seguente viene illustrata una funzione di aggregazione personalizzata che calcola il valore mediano di una raccolta di numeri. Esistono due overload del metodo di estensione `Median`. Il primo overload accetta come input una raccolta di tipo `IEnumerable(Of Double)`. Se la funzione di aggregazione `Median` viene chiamata per un campo di query di tipo `Double`, questo metodo verrà chiamato. Il secondo overload del metodo `Median` può essere passato a qualsiasi tipo generico. L'overload generico del metodo `Median` accetta un secondo parametro che fa riferimento all'espressione lambda `Func(Of T, Double)` per proiettare un valore per un tipo (da una raccolta) come valore corrispondente di tipo `Double`. Delega quindi il calcolo del valore mediano all'altro overload del metodo `Median`. Per altre informazioni sulle espressioni lambda, vedere [Espressioni lambda in C++](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 Nell'esempio seguente vengono illustrate query di esempio che chiamano la funzione di aggregazione `Median` su una raccolta di tipo `Integer`e una raccolta di tipo `Double`. La query che chiama la funzione di aggregazione `Median` sulla raccolta di tipo `Double` chiama l'overload del metodo `Median` che accetta come input una raccolta di tipo `Double`. La query che chiama la funzione di aggregazione `Median` sulla raccolta di tipo `Integer` chiama l'overload generico del metodo `Median`.  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Clausola Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)

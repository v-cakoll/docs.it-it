---
title: Aggregate Clause
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
ms.openlocfilehash: 326c3306368ceca2122e912556efd84e4bfef1f1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413001"
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
|`element`|Obbligatorio. Variabile utilizzata per scorrere gli elementi della raccolta.|  
|`type`|Facoltativa. Tipo di `element`. Se non viene specificato alcun tipo, il tipo di `element` viene dedotto da `collection` .|  
|`collection`|Obbligatorio. Fa riferimento alla raccolta su cui operare.|  
|`clause`|Facoltativa. Una o più clausole di query, ad esempio una `Where` clausola, per perfezionare il risultato della query per applicare la clausola o le clausole Aggregate a.|  
|`expressionList`|Obbligatorio. Una o più espressioni delimitate da virgole che identificano una funzione di aggregazione da applicare alla raccolta. È possibile applicare un alias a una funzione di aggregazione per specificare il nome di un membro per il risultato della query. Se non viene specificato alcun alias, viene usato il nome della funzione di aggregazione. Per esempi, vedere la sezione sulle funzioni di aggregazione più avanti in questo argomento.|  
  
## <a name="remarks"></a>Commenti  
 La `Aggregate` clausola può essere utilizzata per includere funzioni di aggregazione nelle query. Le funzioni di aggregazione eseguono controlli e calcoli su un set di valori e restituiscono un singolo valore. È possibile accedere al valore calcolato utilizzando un membro del tipo di risultato della query. Le funzioni di aggregazione standard che è possibile utilizzare sono le `All` `Any` funzioni,, `Average` , `Count` , `LongCount` , `Max` , `Min` e `Sum` . Queste funzioni hanno familiarità con gli sviluppatori che hanno familiarità con le aggregazioni di SQL. Sono descritti nella sezione seguente di questo argomento.  
  
 Il risultato di una funzione di aggregazione viene incluso nel risultato della query come campo del tipo di risultato della query. È possibile fornire un alias per il risultato della funzione di aggregazione per specificare il nome del membro del tipo di risultato della query che conterrà il valore di aggregazione. Se non viene specificato alcun alias, viene usato il nome della funzione di aggregazione.  
  
 La `Aggregate` clausola può iniziare una query oppure può essere inclusa come clausola aggiuntiva in una query. Se la `Aggregate` clausola inizia una query, il risultato è un singolo valore che rappresenta il risultato della funzione di aggregazione specificata nella `Into` clausola. Se nella clausola viene specificata più di una funzione di aggregazione `Into` , la query restituisce un singolo tipo con una proprietà separata per fare riferimento al risultato di ogni funzione di aggregazione nella `Into` clausola. Se la `Aggregate` clausola viene inclusa come clausola aggiuntiva in una query, il tipo restituito nella raccolta di query avrà una proprietà separata per fare riferimento al risultato di ogni funzione di aggregazione nella `Into` clausola.  
  
## <a name="aggregate-functions"></a>Funzioni di aggregazione

Di seguito sono riportate le funzioni di aggregazione standard che è possibile utilizzare con la `Aggregate` clausola.  
  
### <a name="all"></a>Tutti

Restituisce `true` se tutti gli elementi della raccolta soddisfano una condizione specificata; in caso contrario, restituisce `false` . Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>Qualsiasi

Restituisce `true` se un elemento della raccolta soddisfa una condizione specificata; in caso contrario, restituisce `false` . Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Media

Calcola la media di tutti gli elementi della raccolta o calcola un'espressione fornita per tutti gli elementi della raccolta. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Conteggio

Conta il numero di elementi nella raccolta. È possibile specificare un'espressione facoltativa `Boolean` per contare solo il numero di elementi della raccolta che soddisfano una condizione. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Gruppo

Fa riferimento ai risultati della query raggruppati come risultato di una `Group By` clausola o `Group Join` . La `Group` funzione è valida solo nella `Into` clausola di una `Group By` clausola o `Group Join` . Per ulteriori informazioni ed esempi, vedere clausola [Group by](group-by-clause.md) e [clausola Group Join](group-join-clause.md).

### <a name="longcount"></a>LongCount

Conta il numero di elementi nella raccolta. È possibile specificare un'espressione facoltativa `Boolean` per contare solo il numero di elementi della raccolta che soddisfano una condizione. Restituisce il risultato come `Long` . Per un esempio, vedere la `Count` funzione Aggregate.

### <a name="max"></a>Max

Calcola il valore massimo dalla raccolta oppure calcola un'espressione fornita per tutti gli elementi della raccolta. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>Min

Calcola il valore minimo dalla raccolta oppure calcola un'espressione fornita per tutti gli elementi della raccolta. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>Somma

Calcola la somma di tutti gli elementi della raccolta o calcola un'espressione fornita per tutti gli elementi della raccolta. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>Esempio  

Nell'esempio seguente viene illustrato come utilizzare la `Aggregate` clausola per applicare funzioni di aggregazione a un risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Creazione di funzioni di aggregazione definite dall'utente

 È possibile includere funzioni di aggregazione personalizzate in un'espressione di query aggiungendo metodi di estensione al <xref:System.Collections.Generic.IEnumerable%601> tipo. Il metodo personalizzato può quindi eseguire un calcolo o un'operazione sulla raccolta enumerabile che ha fatto riferimento alla funzione di aggregazione. Per altre informazioni sui metodi di estensione, vedere [Metodi di estensione](../../programming-guide/language-features/procedures/extension-methods.md).  
  
 Nell'esempio seguente viene illustrata una funzione di aggregazione personalizzata che calcola il valore mediano di una raccolta di numeri. Esistono due overload del `Median` metodo di estensione. Il primo overload accetta come input una raccolta di tipo `IEnumerable(Of Double)` . Se la `Median` funzione di aggregazione viene chiamata per un campo di query di tipo `Double` , questo metodo verrà chiamato. Il secondo overload del `Median` metodo può essere passato a qualsiasi tipo generico. L'overload generico del `Median` metodo accetta un secondo parametro che fa riferimento all' `Func(Of T, Double)` espressione lambda per proiettare un valore per un tipo (da una raccolta) come valore corrispondente di tipo `Double` . Delega quindi il calcolo del valore mediano all'altro overload del `Median` metodo. Per ulteriori informazioni sulle espressioni lambda, vedere [espressioni lambda](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 Nell'esempio seguente vengono illustrate query di esempio che chiamano la `Median` funzione di aggregazione su una raccolta di tipo `Integer` e una raccolta di tipo `Double` . La query che chiama la `Median` funzione di aggregazione sulla raccolta di tipo `Double` chiama l'overload del `Median` metodo che accetta come input una raccolta di tipo `Double` . La query che chiama la `Median` funzione di aggregazione sulla raccolta di tipo `Integer` chiama l'overload generico del `Median` metodo.  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola SELECT](select-clause.md)
- [Clausola from](from-clause.md)
- [Clausola WHERE](where-clause.md)
- [Clausola Group By](group-by-clause.md)

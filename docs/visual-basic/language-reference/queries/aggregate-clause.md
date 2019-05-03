---
title: Clausola Aggregate (Visual Basic)
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
ms.openlocfilehash: 21781db637c71abbbe9366bc95b6ee4c89ac2246
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61712630"
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
|`type`|Facoltativo. Tipo di `element`. Se viene specificato alcun tipo, il tipo della `element` viene dedotto dal `collection`.|  
|`collection`|Obbligatorio. Fa riferimento alla raccolta su cui operare.|  
|`clause`|Facoltativo. Uno o più clausole di query, ad esempio un `Where` clausola, il risultato della query per applicare la clausola aggregate o le clausole per perfezionare.|  
|`expressionList`|Obbligatorio. Uno o più valori delimitati da virgole espressioni che identificano una funzione di aggregazione da applicare all'insieme. È possibile applicare un alias a una funzione di aggregazione per specificare un nome di membro per il risultato della query. Se non viene specificato alcun alias, viene utilizzato il nome della funzione di aggregazione. Per esempi, vedere la sezione sulle funzioni di aggregazione più avanti in questo argomento.|  
  
## <a name="remarks"></a>Note  
 Il `Aggregate` clausola può essere utilizzata per includere le funzioni di aggregazione nelle query. Le funzioni di aggregazione eseguono verifiche e calcoli su un set di valori e restituiscono un singolo valore. Il valore calcolato è possibile accedere utilizzando un membro del tipo di risultato della query. Sono le funzioni di aggregazione standard che è possibile usare la `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, e `Sum` funzioni. Queste funzioni sono note agli sviluppatori che hanno familiari con funzioni di aggregazione in SQL. Vengono descritti nella sezione seguente di questo argomento.  
  
 Il risultato di una funzione di aggregazione è incluso nel risultato della query come un campo del tipo di risultato della query. È possibile fornire un alias per il risultato della funzione di aggregazione specificare il nome del membro del tipo di risultato della query che conterrà il valore di aggregazione. Se non viene specificato alcun alias, viene utilizzato il nome della funzione di aggregazione.  
  
 Il `Aggregate` clausola può iniziare una query, o può essere incluso come una clausola aggiuntiva in una query. Se il `Aggregate` clausola inizia una query, il risultato è un singolo valore che rappresenta il risultato della funzione di aggregazione specificato nella `Into` clausola. Se è specificata più di una funzione di aggregazione nel `Into` clausola, la query restituisce un singolo tipo con una proprietà separata per fare riferimento al risultato di ogni funzione di aggregazione nel `Into` clausola. Se il `Aggregate` clausola viene inclusa come una clausola in una query, il tipo restituito nella raccolta di query avranno una proprietà separata per fare riferimento al risultato di ogni funzione di aggregazione nel `Into` clausola.  
  
## <a name="aggregate-functions"></a>Funzioni di aggregazione

Di seguito sono le funzioni di aggregazione standard che possono essere usate con il `Aggregate` clausola.  
  
### <a name="all"></a>Tutti

Restituisce `true` se tutti gli elementi della raccolta soddisfano una condizione specificata; in caso contrario restituisce `false`. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>Qualsiasi

Restituisce `true` se ogni elemento della raccolta soddisfa una condizione specificata; in caso contrario restituisce `false`. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Media

Calcola la media di tutti gli elementi nella raccolta, o calcola un'espressione fornita per tutti gli elementi nella raccolta. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Conteggio

Conta il numero di elementi nella raccolta. È possibile fornire facoltativo `Boolean` espressione per contare solo il numero di elementi nella raccolta che soddisfano una condizione. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Raggruppa

Fa riferimento ai risultati delle query che vengono raggruppati in seguito a un `Group By` o `Group Join` clausola. Il `Group` è valida solo in funzione la `Into` clausola di un `Group By` o `Group Join` clausola. Per altre informazioni ed esempi, vedere [Group By Clause](../../../visual-basic/language-reference/queries/group-by-clause.md) e [clausola Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md).

### <a name="longcount"></a>LongCount

Conta il numero di elementi nella raccolta. È possibile fornire facoltativo `Boolean` espressione per contare solo il numero di elementi nella raccolta che soddisfano una condizione. Restituisce il risultato come un `Long`. Per un esempio, vedere il `Count` funzione di aggregazione.

### <a name="max"></a>Max

Calcola il valore massimo dalla raccolta, o calcola un'espressione fornita per tutti gli elementi nella raccolta. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>Min

Calcola il valore minimo dalla raccolta, o calcola un'espressione fornita per tutti gli elementi nella raccolta. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>Sum

Calcola la somma di tutti gli elementi nella raccolta, o calcola un'espressione fornita per tutti gli elementi nella raccolta. Di seguito è riportato un esempio:

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>Esempio  

Nell'esempio seguente viene illustrato come utilizzare il `Aggregate` clausola per applicare le funzioni di aggregazione per un risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Creazione di funzioni di aggregazione definita dall'utente

 È possibile includere funzioni di aggregazione personalizzate in un'espressione di query mediante l'aggiunta di metodi di estensione per il <xref:System.Collections.Generic.IEnumerable%601> tipo. Il metodo personalizzato può quindi eseguire un calcolo o l'operazione sulla raccolta enumerabile che ha fatto riferimento alla funzione di aggregazione. Per altre informazioni sui metodi di estensione, vedere [Metodi di estensione](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Ad esempio, nell'esempio seguente viene illustrata una funzione di aggregazione personalizzata che calcola il valore mediano di una raccolta di numeri. Esistono due overload del `Median` metodo di estensione. Il primo overload accetta come input, una raccolta di tipo `IEnumerable(Of Double)`. Se il `Median` funzione di aggregazione viene chiamata per un campo di query di tipo `Double`, questo metodo verrà chiamato. Il secondo overload del `Median` metodo può essere passato a qualsiasi tipo generico. L'overload generico del `Median` metodo accetta un secondo parametro che fa riferimento il `Func(Of T, Double)` un'espressione lambda a un valore per un tipo (da una raccolta) il progetto come il valore corrispondente di tipo `Double`. Il calcolo del valore mediano per l'altro overload di delega quindi la `Median` (metodo). Per altre informazioni sulle espressioni lambda, vedere [Espressioni lambda in C++](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 L'esempio seguente illustra esempi di query che chiamano il `Median` funzione in una raccolta del tipo di aggregazione `Integer`e una raccolta di tipo `Double`. La query che chiama il `Median` funzione per la raccolta del tipo di aggregazione `Double` chiama l'overload del metodo le `Median` metodo che accetta come input, una raccolta di tipo `Double`. La query che chiama il `Median` funzione per la raccolta del tipo di aggregazione `Integer` chiama l'overload generico del `Median` (metodo).  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Clausola Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)

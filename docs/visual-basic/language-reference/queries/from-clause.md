---
title: Clausola From
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 33680f49247b3b2a6082b3a6b27ca64f8401e42d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396181"
---
# <a name="from-clause-visual-basic"></a>Clausola From (Visual Basic)
Specifica una o più variabili di intervallo e una raccolta su cui eseguire una query.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`element`|Obbligatorio. *Variabile di intervallo* utilizzata per scorrere gli elementi della raccolta. Una variabile di intervallo viene utilizzata per fare riferimento a ogni membro di `collection` mentre la query scorre `collection` . Deve essere un tipo enumerabile.|  
|`type`|Facoltativa. Tipo di `element`. Se non `type` viene specificato alcun parametro, il tipo di `element` viene dedotto da `collection` .|  
|`collection`|Obbligatorio. Fa riferimento alla raccolta su cui eseguire una query. Deve essere un tipo enumerabile.|  
  
## <a name="remarks"></a>Commenti  
 La `From` clausola viene utilizzata per identificare i dati di origine per una query e le variabili utilizzate per fare riferimento a un elemento della raccolta di origine. Queste variabili sono denominate *variabili di intervallo*. La `From` clausola è obbligatoria per una query, tranne quando la `Aggregate` clausola viene utilizzata per identificare una query che restituisce solo i risultati aggregati. Per ulteriori informazioni, vedere [clausola Aggregate](aggregate-clause.md).  
  
 È possibile specificare più `From` clausole in una query per identificare più raccolte da unire in join. Quando si specificano più raccolte, vengono ripetute in modo indipendente oppure è possibile unirle se sono correlate. È possibile unire le raccolte in modo implicito usando la `Select` clausola oppure in modo esplicito usando le `Join` `Group Join` clausole o. In alternativa, è possibile specificare più variabili di intervallo e raccolte in una singola `From` clausola, con ogni variabile di intervallo e raccolta correlate separate dalle altre da una virgola. Nell'esempio di codice seguente vengono illustrate entrambe le opzioni di sintassi per la `From` clausola.  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 La `From` clausola definisce l'ambito di una query, che è simile all'ambito di un `For` ciclo. Ogni `element` variabile di intervallo nell'ambito di una query deve pertanto avere un nome univoco. Poiché è possibile specificare più `From` clausole per una query, `From` le clausole successive possono fare riferimento alle variabili di intervallo nella `From` clausola oppure possono fare riferimento alle variabili di intervallo in una `From` clausola precedente. Ad esempio, nell'esempio seguente viene illustrata una clausola annidata `From` in cui la raccolta nella seconda clausola è basata su una proprietà della variabile di intervallo nella prima clausola.  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 Ogni `From` clausola può essere seguita da qualsiasi combinazione di clausole di query aggiuntive per perfezionare la query. È possibile affinare la query nei modi seguenti:  
  
- Combinare più raccolte in modo implicito usando `From` le `Select` clausole e oppure in modo esplicito usando `Join` le `Group Join` clausole o.  
  
- Utilizzare la `Where` clausola per filtrare il risultato della query.  
  
- Ordinare il risultato usando la `Order By` clausola.  
  
- Raggruppare i risultati simili utilizzando la `Group By` clausola.  
  
- Utilizzare la `Aggregate` clausola per identificare le funzioni di aggregazione da valutare per l'intero risultato della query.  
  
- Utilizzare la `Let` clausola per introdurre una variabile di iterazione il cui valore è determinato da un'espressione anziché da una raccolta.  
  
- Utilizzare la `Distinct` clausola per ignorare i risultati della query duplicati.  
  
- Identificare le parti del risultato da restituire utilizzando le `Skip` `Take` clausole,, `Skip While` e `Take While` .  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una `From` clausola per dichiarare una variabile di intervallo `cust` per ogni `Customer` oggetto della `customers` raccolta. La `Where` clausola usa la variabile di intervallo per limitare l'output ai clienti dall'area specificata. Il `For Each` ciclo Visualizza il nome della società per ogni cliente nel risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a>Vedere anche

- [Query](index.md)
- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Istruzione For Each...Next](../statements/for-each-next-statement.md)
- [Istruzione For...Next](../statements/for-next-statement.md)
- [Clausola SELECT](select-clause.md)
- [Clausola WHERE](where-clause.md)
- [Aggregate Clause](aggregate-clause.md)
- [Clausola Distinct](distinct-clause.md)
- [Clausola join](join-clause.md)
- [Clausola Group Join](group-join-clause.md)
- [Clausola Order By](order-by-clause.md)
- [Clausola Let](let-clause.md)
- [Clausola Skip](skip-clause.md)
- [Clausola Take](take-clause.md)
- [Clausola Skip While](skip-while-clause.md)
- [Clausola Take While](take-while-clause.md)

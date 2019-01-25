---
title: Clausola From (Visual Basic)
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
ms.openlocfilehash: fd11d00ebfa42eda272db39965d25b905bd5c841
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678785"
---
# <a name="from-clause-visual-basic"></a>Clausola From (Visual Basic)
Specifica uno o più variabili di intervallo e una raccolta di query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`element`|Obbligatorio. Oggetto *variabile di intervallo* utilizzato per scorrere gli elementi della raccolta. Una variabile di intervallo viene usata per fare riferimento a ogni membro del `collection` perché la query esegue l'iterazione attraverso la `collection`. Deve essere un tipo enumerabile.|  
|`type`|Facoltativo. Tipo di `element`. Se nessun `type` viene specificato, il tipo di `element` viene dedotto dal `collection`.|  
|`collection`|Obbligatorio. Fa riferimento alla raccolta per eseguire una query. Deve essere un tipo enumerabile.|  
  
## <a name="remarks"></a>Note  
 Il `From` clausola viene utilizzata per identificare i dati di origine per una query e le variabili che vengono utilizzate per fare riferimento a un elemento dalla raccolta di origine. Queste variabili vengono chiamate *variabili di intervallo*. Il `From` clausola è necessaria per una query, tranne quando la `Aggregate` clausola viene utilizzata per identificare una query che restituisce solo i risultati aggregati. Per altre informazioni, vedere [clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 È possibile specificare più `From` clausole in una query per identificare più raccolte di essere unito in join. Quando si specificano più raccolte, essi vengono scorsi in modo indipendente oppure è possibile unirle se sono correlati. È possibile unire le raccolte in modo implicito utilizzando la `Select` clausola, o in modo esplicito usando il `Join` o `Group Join` clausole. In alternativa, è possibile specificare più variabili di intervallo e le raccolte in una singola `From` clausola, con ogni raccolta separato dagli altri da una virgola e la variabile di intervallo correlato. Esempio di codice seguente illustra entrambe le opzioni della sintassi per il `From` clausola.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 Il `From` clausola definisce l'ambito di una query, che è simile all'ambito di un `For` ciclo. Pertanto, ogni `element` variabile di intervallo nell'ambito di una query deve avere un nome univoco. Poiché è possibile specificare più `From` clausole per una query, le successive `From` clausole possono fare riferimento a variabili di intervallo nel `From` clausola oppure è possibile fare riferimento alle variabili di intervallo in una precedente `From` clausola. Ad esempio, l'esempio seguente mostra un nidificata `From` clausola in cui la raccolta nella seconda clausola si basa su una proprietà della variabile di intervallo nella prima clausola.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 Ogni `From` clausola può essere seguita da una qualsiasi combinazione di clausole di query aggiuntive per perfezionare la query. È possibile affinare la query nei modi seguenti:  
  
-   Combinare più raccolte in modo implicito usando la `From` e `Select` clausole, o in modo esplicito tramite il `Join` o `Group Join` clausole.  
  
-   Usare il `Where` clausola per filtrare i risultati della query.  
  
-   Ordinare il risultato utilizzando il `Order By` clausola.  
  
-   Raggruppare i risultati simili tramite la `Group By` clausola.  
  
-   Usare il `Aggregate` clausola per identificare le funzioni di aggregazione da valutare per l'intero risultato della query.  
  
-   Usare il `Let` clausola per introdurre una variabile di iterazione il cui valore è determinato da un'espressione anziché una raccolta.  
  
-   Usare il `Distinct` clausola per ignorare i risultati della query duplicata.  
  
-   Identificare le parti del risultato da restituire con il `Skip`, `Take`, `Skip While`, e `Take While` clausole.  
  
## <a name="example"></a>Esempio  
 La query seguente espressione Usa un `From` clausola per dichiarare una variabile di intervallo `cust` per ogni `Customer` dell'oggetto nel `customers` raccolta. Il `Where` clausola utilizza la variabile di intervallo per limitare l'output per i clienti dall'area specificata. Il `For Each` ciclo Visualizza il nome della società per ogni cliente nel risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a>Vedere anche
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Istruzione For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Clausola Distinct](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [Clausola Join](../../../visual-basic/language-reference/queries/join-clause.md)
- [Clausola Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Clausola Order By](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Clausola Let](../../../visual-basic/language-reference/queries/let-clause.md)
- [Clausola Skip](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Clausola Take](../../../visual-basic/language-reference/queries/take-clause.md)
- [Clausola Skip While](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Clausola Take While](../../../visual-basic/language-reference/queries/take-while-clause.md)

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
ms.openlocfilehash: 781902f1bf28bd029c8d9825aee155a6691cbae9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004786"
---
# <a name="from-clause-visual-basic"></a>Clausola From (Visual Basic)
Specifica una o più variabili di intervallo e una raccolta su cui eseguire una query.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>Parti  
  
|Nome|Definizione|  
|---|---|  
|`element`|Obbligatorio. *Variabile di intervallo* utilizzata per scorrere gli elementi della raccolta. Una variabile di intervallo viene utilizzata per fare riferimento a ogni membro del `collection` quando la query esegue l'iterazione nel `collection`. Deve essere un tipo enumerabile.|  
|`type`|facoltativo. Tipo di `element`. Se non si specifica `type`, il tipo di `element` viene dedotto da `collection`.|  
|`collection`|Obbligatorio. Fa riferimento alla raccolta su cui eseguire una query. Deve essere un tipo enumerabile.|  
  
## <a name="remarks"></a>Note  
 La clausola `From` viene utilizzata per identificare i dati di origine per una query e le variabili utilizzate per fare riferimento a un elemento della raccolta di origine. Queste variabili sono denominate *variabili di intervallo*. La clausola `From` è obbligatoria per una query, tranne quando la clausola `Aggregate` viene utilizzata per identificare una query che restituisce solo i risultati aggregati. Per ulteriori informazioni, vedere [clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 È possibile specificare più clausole `From` in una query per identificare più raccolte da unire in join. Quando si specificano più raccolte, vengono ripetute in modo indipendente oppure è possibile unirle se sono correlate. È possibile unire le raccolte in modo implicito usando la clausola `Select` oppure in modo esplicito usando le clausole `Join` o `Group Join`. In alternativa, è possibile specificare più variabili di intervallo e raccolte in una singola clausola `From`, con ogni variabile di intervallo e raccolta correlate separate dalle altre con una virgola. Nell'esempio di codice seguente vengono illustrate entrambe le opzioni di sintassi per la clausola `From`.  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 La clausola `From` definisce l'ambito di una query, che è simile all'ambito di un ciclo `For`. Ogni variabile di intervallo `element` nell'ambito di una query deve pertanto avere un nome univoco. Poiché è possibile specificare più clausole `From` per una query, le clausole `From` successive possono fare riferimento alle variabili di intervallo nella clausola `From` oppure possono fare riferimento alle variabili di intervallo in una clausola `From` precedente. Ad esempio, nell'esempio seguente viene illustrata una clausola `From` annidata in cui la raccolta nella seconda clausola è basata su una proprietà della variabile di intervallo nella prima clausola.  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 Ogni clausola `From` può essere seguita da qualsiasi combinazione di clausole di query aggiuntive per perfezionare la query. È possibile affinare la query nei modi seguenti:  
  
- Combinare più raccolte in modo implicito usando le clausole `From` e `Select` oppure in modo esplicito usando le clausole `Join` o `Group Join`.  
  
- Utilizzare la clausola `Where` per filtrare il risultato della query.  
  
- Ordinare il risultato usando la clausola `Order By`.  
  
- Raggruppare i risultati simili utilizzando la clausola `Group By`.  
  
- Utilizzare la clausola `Aggregate` per identificare le funzioni di aggregazione da valutare per l'intero risultato della query.  
  
- Utilizzare la clausola `Let` per introdurre una variabile di iterazione il cui valore è determinato da un'espressione anziché da una raccolta.  
  
- Utilizzare la clausola `Distinct` per ignorare i risultati della query duplicati.  
  
- Identificare le parti del risultato da restituire utilizzando le clausole `Skip`, `Take`, `Skip While` e `Take While`.  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una clausola `From` per dichiarare una variabile di intervallo `cust` per ogni oggetto `Customer` nella raccolta `customers`. La clausola `Where` usa la variabile di intervallo per limitare l'output ai clienti dall'area specificata. Il ciclo `For Each` Visualizza il nome della società per ogni cliente nel risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
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

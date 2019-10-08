---
title: Clausola Where (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 404dd848058f7e5c9bc8a74b6d89df18c6c55fad
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005008"
---
# <a name="where-clause-visual-basic"></a>Clausola Where (Visual Basic)
Specifica la condizione di filtro per una query.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>Parti  
 `condition`  
 Obbligatorio. Espressione che determina se i valori per l'elemento corrente nella raccolta sono inclusi nella raccolta di output. L'espressione deve restituire un valore `Boolean` o l'equivalente di un valore `Boolean`. Se la condizione restituisce `True`, l'elemento viene incluso nel risultato della query. in caso contrario, l'elemento viene escluso dal risultato della query.  
  
## <a name="remarks"></a>Note  
 La clausola `Where` consente di filtrare i dati della query selezionando solo gli elementi che soddisfano determinati criteri. Gli elementi i cui valori determinano che la clausola `Where` restituisca `True` sono inclusi nel risultato della query. gli altri elementi sono esclusi. L'espressione utilizzata in una clausola `Where` deve restituire una `Boolean` o l'equivalente di un `Boolean`, ad esempio un numero intero che restituisce `False` quando il valore è zero. È possibile combinare più espressioni in una clausola `Where` usando operatori logici come `And`, `Or`, `AndAlso`, `OrElse`, `Is` e `IsNot`.  
  
 Per impostazione predefinita, le espressioni di query non vengono valutate fino a quando non vengono accessibili, ad esempio quando sono associate a dati o iterate in un ciclo `For`. Di conseguenza, la clausola `Where` non viene valutata fino a quando non viene eseguito l'accesso alla query. Se si dispone di valori esterni alla query utilizzati nella clausola `Where`, verificare che nel momento in cui viene eseguita la query venga utilizzato il valore appropriato nella clausola `Where`. Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura della prima query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 È possibile chiamare funzioni all'interno di una clausola `Where` per eseguire un calcolo o un'operazione su un valore dell'elemento corrente nella raccolta. La chiamata di una funzione in una clausola `Where` può causare l'esecuzione immediata della query quando viene definita al posto di quando viene eseguito l'accesso. Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura della prima query LINQ](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una clausola `From` per dichiarare una variabile di intervallo `cust` per ogni oggetto `Customer` nella raccolta `customers`. La clausola `Where` usa la variabile di intervallo per limitare l'output ai clienti dall'area specificata. Il ciclo `For Each` Visualizza il nome della società per ogni cliente nel risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono utilizzati gli operatori logici `And` e `Or` nella clausola `Where`.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Istruzione For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)

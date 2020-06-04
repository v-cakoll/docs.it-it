---
title: Clausola Where
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: b80bb047551dee8ab23cfac06b961996992d69b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359541"
---
# <a name="where-clause-visual-basic"></a>Clausola Where (Visual Basic)
Specifica la condizione di filtro per una query.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>Parti  
 `condition`  
 Obbligatorio. Espressione che determina se i valori per l'elemento corrente nella raccolta sono inclusi nella raccolta di output. L'espressione deve restituire un `Boolean` valore o l'equivalente di un `Boolean` valore. Se la condizione restituisce `True` , l'elemento viene incluso nel risultato della query. in caso contrario, l'elemento viene escluso dal risultato della query.  
  
## <a name="remarks"></a>Commenti  
 La `Where` clausola consente di filtrare i dati della query selezionando solo gli elementi che soddisfano determinati criteri. Gli elementi i cui valori determinano che la `Where` clausola restituisca `True` sono inclusi nel risultato della query; gli altri elementi sono esclusi. L'espressione utilizzata in una `Where` clausola deve restituire un oggetto `Boolean` o l'equivalente di un `Boolean` , ad esempio un Integer che restituisce `False` quando il valore è zero. È possibile combinare più espressioni in una `Where` clausola utilizzando operatori logici come `And` ,, `Or` `AndAlso` , `OrElse` , `Is` e `IsNot` .  
  
 Per impostazione predefinita, le espressioni di query non vengono valutate fino a quando non vengono accessibili, ad esempio quando sono associate a dati o iterate in un `For` ciclo. Di conseguenza, la `Where` clausola non viene valutata fino a quando non viene eseguito l'accesso alla query. Se i valori sono esterni alla query utilizzata nella `Where` clausola, verificare che nel momento in cui viene eseguita la query venga utilizzato il valore appropriato nella `Where` clausola. Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura della prima query LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
 È possibile chiamare le funzioni all'interno `Where` di una clausola per eseguire un calcolo o un'operazione su un valore dell'elemento corrente nella raccolta. La chiamata di una funzione in una `Where` clausola può causare l'esecuzione immediata della query quando viene definita al posto di quando viene eseguito l'accesso. Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura della prima query LINQ](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="example"></a>Esempio  
 Nell'espressione di query seguente viene utilizzata una `From` clausola per dichiarare una variabile di intervallo `cust` per ogni `Customer` oggetto della `customers` raccolta. La `Where` clausola usa la variabile di intervallo per limitare l'output ai clienti dall'area specificata. Il `For Each` ciclo Visualizza il nome della società per ogni cliente nel risultato della query.  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono utilizzati gli `And` `Or` operatori logici e nella `Where` clausola.  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola from](from-clause.md)
- [Clausola SELECT](select-clause.md)
- [Istruzione For Each...Next](../statements/for-each-next-statement.md)

---
title: Clausola Group Join (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupJoinIn
- vb.QueryGroupJoinOn
- vb.QueryGroupJoin
- vb.QueryGroupJoinInto
helpviewer_keywords:
- Group Join clause [Visual Basic]
- Group Join statement [Visual Basic]
- queries [Visual Basic], Group Join
ms.assetid: 37dbf79c-7b5c-421b-bbb7-dadfd2b92a1c
ms.openlocfilehash: 3da4ca2db299a65b2c0f1fa259bbaabe4f53aa33
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945314"
---
# <a name="group-join-clause-visual-basic"></a>Clausola Group Join (Visual Basic)
Combina due raccolte in un'unica raccolta gerarchica. L'operazione di join è basata su chiavi corrispondenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`element`|Obbligatorio. La variabile di controllo per la raccolta da unire in join.|  
|`type`|Facoltativo. Tipo di `element`. Se nessun `type` viene specificato, il tipo di `element` viene dedotto dal `collection`.|  
|`collection`|Obbligatorio. La raccolta da combinare con la raccolta che si trova sul lato sinistro del `Group Join` operatore. Oggetto `Group Join` clausola può essere annidata in una `Join` clausola o in un altro `Group Join` clausola.|  
|`key1` `Equals` `key2`|Obbligatorio. Identifica le chiavi per le raccolte da unire in join. È necessario usare il `Equals` operatore per confrontare le chiavi delle raccolte da unire in join. È possibile combinare le condizioni di join tramite il `And` operatore per identificare più chiavi. Il `key1` il parametro deve essere dall'insieme sul lato sinistro del `Join` operatore. Il `key2` il parametro deve essere dall'insieme sul lato destro del `Join` operatore.<br /><br /> Le chiavi usate nella condizione di join possono essere espressioni che includono più di un elemento dalla raccolta. Tuttavia, ogni espressione chiave può contenere solo gli elementi del rispettivo insieme.|  
|`expressionList`|Obbligatorio. Uno o più espressioni che identificano come vengono aggregati i gruppi di elementi dalla raccolta. Per identificare il nome di un membro per i risultati raggruppati, usare il `Group` parola chiave (`<alias> = Group`). È anche possibile includere funzioni di aggregazione da applicare al gruppo.|  
  
## <a name="remarks"></a>Note  
 Il `Group Join` clausola combina due raccolte in base ai corrispondenti valori di chiave da raccolte da includere. La raccolta risultante può contenere un membro che fa riferimento a una raccolta di elementi della seconda raccolta che corrisponde al valore chiave della prima raccolta. È anche possibile specificare funzioni di aggregazione da applicare agli elementi raggruppati della seconda raccolta. Per informazioni sulle funzioni di aggregazione, vedere [clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Si consideri, ad esempio, una raccolta di gestori e una raccolta di dipendenti. Gli elementi di entrambe le raccolte hanno una proprietà di ManagerID che identifichi i dipendenti che fanno riferimento a un particolare responsabile. I risultati di un'operazione di join contiene un risultato per ogni responsabile e dipendenti con un valore ManagerID corrispondente. I risultati di una `Group Join` operazione contiene l'elenco completo dei gestori. Ogni risultato manager sarebbe necessario un membro a cui fa riferimento l'elenco dei dipendenti che hanno una corrispondenza per il gestore specifico.  
  
 La raccolta risultante da un `Group Join` operazione può contenere qualsiasi combinazione di valori dalla raccolta identificata nel `From` clausola e alle espressioni identificate nel `Into` clausola del `Group Join` clausola. Per altre informazioni sulle espressioni valide per i `Into` clausola, vedere [clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Oggetto `Group Join` operazione restituirà tutti i risultati dalla raccolta identificata nel lato sinistro del `Group Join` operatore. Questo vale anche se non sono presenti corrispondenze nella raccolta da unire in join. Si tratta, ad esempio un `LEFT OUTER JOIN` in SQL.  
  
 È possibile usare il `Join` clausola per combinare raccolte in un'unica raccolta. Ciò equivale a un `INNER JOIN` in SQL.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente unisce due raccolte mediante il `Group Join` clausola.  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Join](../../../visual-basic/language-reference/queries/join-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Clausola Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)

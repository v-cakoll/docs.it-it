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
ms.openlocfilehash: 094281b0afb34451ae8539e4eb967043b21d379c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
|`type`|Facoltativo. Tipo di `element`. Se non `type` è specificato, il tipo di `element` viene dedotto dal `collection`.|  
|`collection`|Obbligatorio. La raccolta da combinare con la raccolta che si trova sul lato sinistro del `Group Join` operatore. Oggetto `Group Join` clausola può essere annidata una `Join` clausola o in un altro `Group Join` clausola.|  
|`key1` `Equals` `key2`|Obbligatorio. Identifica le chiavi per le raccolte da unire in join. È necessario utilizzare il `Equals` operatore per confrontare le chiavi dalle raccolte da unire in join. È possibile combinare le condizioni di join utilizzando il `And` operatore per identificare più chiavi. Il `key1` parametro deve essere dall'insieme sul lato sinistro del `Join` operatore. Il `key2` parametro deve essere dall'insieme sul lato destro del `Join` operatore.<br /><br /> Le chiavi usate nella condizione di join possono essere espressioni che includono più di un elemento dalla raccolta. Tuttavia, ogni espressione chiave può contenere solo gli elementi del rispettivo insieme.|  
|`expressionList`|Obbligatorio. Una o più espressioni che identificano come vengono aggregati i gruppi di elementi dalla raccolta. Per identificare un nome di membro per i risultati raggruppati, utilizzare il `Group` (parola chiave) (`<alias> = Group`). È anche possibile includere funzioni di aggregazione da applicare al gruppo.|  
  
## <a name="remarks"></a>Note  
 Il `Group Join` clausola combina due raccolte in base ai valori di chiave le raccolte da unire in join di corrispondenza. La raccolta risultante può contenere un membro che fa riferimento a una raccolta di elementi della seconda raccolta che corrisponde al valore di chiave della prima raccolta. È anche possibile specificare funzioni di aggregazione da applicare agli elementi raggruppati la seconda raccolta. Per informazioni sulle funzioni di aggregazione, vedere [clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Si consideri, ad esempio, una raccolta di gestori e una raccolta di dipendenti. Gli elementi di entrambe le raccolte hanno una proprietà ManagerID che identifica i dipendenti che fanno riferimento a una gestione particolare. I risultati di un'operazione di join conterrebbe un risultato per ogni manager ed employee con un valore di ManagerID corrispondente. I risultati di una `Group Join` operazione contiene l'elenco completo dei gestori. Ogni risultato del gestore avrebbe un membro che fa riferimento all'elenco dei dipendenti che hanno una corrispondenza per il gestore specifico.  
  
 La raccolta risultante da un `Group Join` operazione può contenere qualsiasi combinazione di valori dalla raccolta identificato nel `From` clausola ed espressioni identificate nella `Into` clausola del `Group Join` clausola. Per ulteriori informazioni sulle espressioni valide per il `Into` clausola, vedere [clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Oggetto `Group Join` operazione restituirà tutti i risultati dall'insieme identificato sul lato sinistro del `Group Join` operatore. Questo vale anche se non sono presenti corrispondenze nella raccolta da unire in join. Ciò equivale a un `LEFT OUTER JOIN` in SQL.  
  
 È possibile utilizzare il `Join` clausola per combinare le raccolte in un'unica raccolta. Ciò equivale a un `INNER JOIN` in SQL.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente crea un join tra due raccolte tramite la `Group Join` clausola.  
  
 [!code-vb[VbSimpleQuerySamples#14](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-join-clause_1.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Join](../../../visual-basic/language-reference/queries/join-clause.md)  
 [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Clausola Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)

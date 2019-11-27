---
title: Clausola Group Join
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
ms.openlocfilehash: 0546c86322663ce6c56a89e63311d0f02f88cfe4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346846"
---
# <a name="group-join-clause-visual-basic"></a>Clausola Group Join (Visual Basic)
Combina due raccolte in un'unica raccolta gerarchica. L'operazione di join è basata sulle chiavi corrispondenti.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
Group Join element [As type] In collection _  
  On key1 Equals key2 [ And key3 Equals key4 [... ] ] _  
  Into expressionList  
```  
  
## <a name="parts"></a>Parti  
  
|Termine|Definizione|  
|---|---|  
|`element`|Obbligatoria. Variabile di controllo per la raccolta da unire in join.|  
|`type`|Facoltativa. Tipo di `element`. Se non viene specificato alcun `type`, il tipo di `element` viene dedotto da `collection`.|  
|`collection`|Obbligatoria. Raccolta da combinare con la raccolta che si trova sul lato sinistro dell'operatore di `Group Join`. Una clausola `Group Join` può essere annidata in una clausola `Join` o in un'altra clausola `Group Join`.|  
|`key1` `Equals` `key2`|Obbligatoria. Identifica le chiavi per le raccolte da unire in join. È necessario utilizzare l'operatore `Equals` per confrontare le chiavi delle raccolte da unire in join. È possibile combinare le condizioni di join usando l'operatore `And` per identificare più chiavi. Il `key1` parametro deve provenire dalla raccolta sul lato sinistro dell'operatore `Join`. Il `key2` parametro deve essere dalla raccolta sul lato destro dell'operatore `Join`.<br /><br /> Le chiavi utilizzate nella condizione di join possono essere espressioni che includono più di un elemento della raccolta. Ogni espressione chiave può tuttavia contenere solo elementi della rispettiva raccolta.|  
|`expressionList`|Obbligatoria. Una o più espressioni che identificano la modalità di aggregazione dei gruppi di elementi della raccolta. Per identificare un nome di membro per i risultati raggruppati, usare la parola chiave `Group` (`<alias> = Group`). È anche possibile includere funzioni di aggregazione da applicare al gruppo.|  
  
## <a name="remarks"></a>Note  
 La clausola `Group Join` combina due raccolte in base ai valori di chiave corrispondenti delle raccolte da unire in join. La raccolta risultante può contenere un membro che fa riferimento a una raccolta di elementi della seconda raccolta che corrispondono al valore della chiave della prima raccolta. È inoltre possibile specificare le funzioni di aggregazione da applicare agli elementi raggruppati della seconda raccolta. Per informazioni sulle funzioni di aggregazione, vedere [clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Si consideri, ad esempio, una raccolta di Manager e una raccolta di dipendenti. Gli elementi di entrambe le raccolte hanno una proprietà ManagerID che identifica i dipendenti che riferiscono a un particolare responsabile. I risultati di un'operazione di join contengono un risultato per ogni responsabile e dipendente con un valore ManagerID corrispondente. I risultati di un'operazione di `Group Join` contengono l'elenco completo dei Manager. Ogni risultato di gestione avrà un membro che fa riferimento all'elenco di dipendenti che corrispondevano al responsabile specifico.  
  
 La raccolta risultante da un'operazione di `Group Join` può contenere qualsiasi combinazione di valori della raccolta identificata nella clausola `From` e le espressioni identificate nella clausola `Into` della clausola `Group Join`. Per ulteriori informazioni sulle espressioni valide per la clausola `Into`, vedere [clausola Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Un'operazione di `Group Join` restituirà tutti i risultati della raccolta identificata sul lato sinistro dell'operatore `Group Join`. Questo vale anche se non sono presenti corrispondenze nella raccolta da unire in join. Questa operazione è simile a una `LEFT OUTER JOIN` in SQL.  
  
 È possibile usare la clausola `Join` per combinare le raccolte in un'unica raccolta. Equivale a un `INNER JOIN` in SQL.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente unisce due raccolte usando la clausola `Group Join`.  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Join](../../../visual-basic/language-reference/queries/join-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
- [Clausola Group By](../../../visual-basic/language-reference/queries/group-by-clause.md)

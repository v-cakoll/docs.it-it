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
ms.openlocfilehash: 7916e51293c06016b2581b7109df3f0a599404ca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359833"
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
|`element`|Obbligatorio. Variabile di controllo per la raccolta da unire in join.|  
|`type`|Facoltativa. Tipo di `element`. Se non `type` viene specificato alcun parametro, il tipo di `element` viene dedotto da `collection` .|  
|`collection`|Obbligatorio. Raccolta da combinare con la raccolta che si trova sul lato sinistro dell' `Group Join` operatore. Una `Group Join` clausola può essere annidata in una `Join` clausola o in un'altra `Group Join` clausola.|  
|`key1` `Equals` `key2`|Obbligatorio. Identifica le chiavi per le raccolte da unire in join. `Equals`Per confrontare le chiavi delle raccolte da unire in join, è necessario usare l'operatore. È possibile combinare le condizioni di join usando l' `And` operatore per identificare più chiavi. Il `key1` parametro deve essere dalla raccolta a sinistra dell' `Join` operatore. Il `key2` parametro deve essere dalla raccolta a destra dell' `Join` operatore.<br /><br /> Le chiavi utilizzate nella condizione di join possono essere espressioni che includono più di un elemento della raccolta. Ogni espressione chiave può tuttavia contenere solo elementi della rispettiva raccolta.|  
|`expressionList`|Obbligatorio. Una o più espressioni che identificano la modalità di aggregazione dei gruppi di elementi della raccolta. Per identificare un nome di membro per i risultati raggruppati, usare la `Group` parola chiave ( `<alias> = Group` ). È anche possibile includere funzioni di aggregazione da applicare al gruppo.|  
  
## <a name="remarks"></a>Commenti  
 La `Group Join` clausola combina due raccolte in base ai valori di chiave corrispondenti delle raccolte da unire in join. La raccolta risultante può contenere un membro che fa riferimento a una raccolta di elementi della seconda raccolta che corrispondono al valore della chiave della prima raccolta. È inoltre possibile specificare le funzioni di aggregazione da applicare agli elementi raggruppati della seconda raccolta. Per informazioni sulle funzioni di aggregazione, vedere [clausola Aggregate](aggregate-clause.md).  
  
 Si consideri, ad esempio, una raccolta di Manager e una raccolta di dipendenti. Gli elementi di entrambe le raccolte hanno una proprietà ManagerID che identifica i dipendenti che riferiscono a un particolare responsabile. I risultati di un'operazione di join contengono un risultato per ogni responsabile e dipendente con un valore ManagerID corrispondente. I risultati di un' `Group Join` operazione contengono l'elenco completo dei Manager. Ogni risultato di gestione avrà un membro che fa riferimento all'elenco di dipendenti che corrispondevano al responsabile specifico.  
  
 La raccolta risultante da un' `Group Join` operazione può contenere qualsiasi combinazione di valori della raccolta identificata nella `From` clausola e le espressioni identificate nella `Into` clausola della clausola `Group Join` . Per ulteriori informazioni sulle espressioni valide per la `Into` clausola, vedere [clausola Aggregate](aggregate-clause.md).  
  
 Un' `Group Join` operazione restituirà tutti i risultati della raccolta identificata sul lato sinistro dell' `Group Join` operatore. Questo vale anche se non sono presenti corrispondenze nella raccolta da unire in join. Questa operazione è simile a `LEFT OUTER JOIN` in SQL.  
  
 È possibile usare la `Join` clausola per combinare le raccolte in un'unica raccolta. Equivale a un `INNER JOIN` in SQL.  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente unisce due raccolte usando la `Group Join` clausola.  
  
 [!code-vb[VbSimpleQuerySamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#14)]  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](index.md)
- [Clausola SELECT](select-clause.md)
- [Clausola from](from-clause.md)
- [Clausola join](join-clause.md)
- [Clausola WHERE](where-clause.md)
- [Clausola Group By](group-by-clause.md)

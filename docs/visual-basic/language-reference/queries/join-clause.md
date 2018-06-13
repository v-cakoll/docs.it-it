---
title: Clausola Join (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: 2186954ab6536988271629c4feba0a40563bfc3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603912"
---
# <a name="join-clause-visual-basic"></a>Clausola Join (Visual Basic)
Combina due raccolte in un'unica raccolta. L'operazione di join è basata su chiavi corrispondenti e utilizza il `Equals` operatore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>Parti  
 `element`  
 Obbligatorio. La variabile di controllo per la raccolta da unire in join.  
  
 `collection`  
 Obbligatorio. La raccolta da combinare con l'insieme identificato sul lato sinistro del `Join` operatore. Oggetto `Join` clausola può essere annidata in un'altra `Join` clausola, o in un `Group Join` clausola.  
  
 `joinClause`  
 Facoltativo. Uno o più ulteriori `Join` clausole per perfezionare la query.  
  
 `groupJoinClause`  
 Facoltativo. Uno o più ulteriori `Group Join` clausole per perfezionare la query.  
  
 `key1` `Equals` `key2`  
 Obbligatorio. Identifica le chiavi per le raccolte da unire in join. È necessario utilizzare il `Equals` operatore per confrontare le chiavi dalle raccolte da unire in join. È possibile combinare le condizioni di join utilizzando il `And` operatore per identificare più chiavi. `key1` devono essere comprese tra la raccolta a sinistra del `Join` operatore. `key2` devono essere comprese tra la raccolta sul lato destro del `Join` operatore.  
  
 Le chiavi usate nella condizione di join possono essere espressioni che includono più di un elemento dalla raccolta. Tuttavia, ogni espressione chiave può contenere solo gli elementi del rispettivo insieme.  
  
## <a name="remarks"></a>Note  
 Il `Join` clausola combina due raccolte in base ai valori di chiave le raccolte da unire in join di corrispondenza. La raccolta risulta può contenere qualsiasi combinazione di valori dalla raccolta identificata sul lato sinistro del `Join` operatore e la raccolta identificato nel `Join` clausola. La query restituirà solo i risultati per cui la condizione specificata dal `Equals` operatore viene soddisfatta. Ciò equivale a un `INNER JOIN` in SQL.  
  
 È possibile utilizzare più `Join` clausole in una query per unire due o più raccolte in un'unica raccolta.  
  
 È possibile eseguire un join implicito per combinare le raccolte senza il `Join` clausola. A tale scopo, includere più `In` clausole il `From` clausola e specificare un `Where` clausola che identifica le chiavi che si desidera utilizzare per il join.  
  
 È possibile utilizzare il `Group Join` clausola per combinare più raccolte in un'unica raccolta gerarchica. Ciò equivale a un `LEFT OUTER JOIN` in SQL.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente esegue un join implicito per combinare un elenco di clienti con i relativi ordini.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente crea un join tra due raccolte tramite la `Join` clausola.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 In questo esempio verrà produrrà un output simile al seguente:  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente crea un join tra due raccolte tramite la `Join` clausola con due colonne chiave.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 Nell'esempio verrà produrrà un output simile al seguente:  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Query](../../../visual-basic/language-reference/queries/queries.md)  
 [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Clausola Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)

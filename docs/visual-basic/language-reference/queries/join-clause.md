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
ms.openlocfilehash: b5211d0ed3f618013dc9fe764a6d7b2db8177c26
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582287"
---
# <a name="join-clause-visual-basic"></a>Clausola Join (Visual Basic)

Combina due raccolte in un'unica raccolta. L'operazione di join è basata sulle chiavi corrispondenti e usa l'operatore `Equals`.

## <a name="syntax"></a>Sintassi

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a>Parti

`element` Obbligatorio. Variabile di controllo per la raccolta da unire in join.

`collection`  
Obbligatorio. Raccolta da combinare con la raccolta identificata sul lato sinistro dell'operatore di `Join`. Una clausola `Join` può essere annidata in un'altra clausola `Join` o in una clausola `Group Join`.

`joinClause`  
Parametro facoltativo. Una o più clausole `Join` aggiuntive per perfezionare ulteriormente la query.

`groupJoinClause`  
Parametro facoltativo. Una o più clausole `Group Join` aggiuntive per perfezionare ulteriormente la query.

`key1` `Equals` `key2`  
Obbligatorio. Identifica le chiavi per le raccolte da unire in join. È necessario utilizzare l'operatore `Equals` per confrontare le chiavi delle raccolte da unire in join. È possibile combinare le condizioni di join usando l'operatore `And` per identificare più chiavi. `key1` deve provenire dalla raccolta sul lato sinistro dell'operatore `Join`. `key2` deve provenire dalla raccolta sul lato destro dell'operatore `Join`.

Le chiavi utilizzate nella condizione di join possono essere espressioni che includono più di un elemento della raccolta. Ogni espressione chiave può tuttavia contenere solo elementi della rispettiva raccolta.

## <a name="remarks"></a>Note

La clausola `Join` combina due raccolte in base ai valori di chiave corrispondenti delle raccolte da unire in join. La raccolta risultante può contenere qualsiasi combinazione di valori della raccolta identificata sul lato sinistro dell'operatore `Join` e della raccolta identificata nella clausola `Join`. La query restituirà solo i risultati per i quali viene soddisfatta la condizione specificata dall'operatore `Equals`. Equivale a un `INNER JOIN` in SQL.

È possibile utilizzare più clausole `Join` in una query per unire due o più raccolte in una singola raccolta.

È possibile eseguire un join implicito per combinare raccolte senza la clausola `Join`. A tale scopo, includere più clausole `In` nella clausola `From` e specificare una clausola `Where` che identifichi le chiavi che si desidera utilizzare per il join.

È possibile usare la clausola `Group Join` per combinare le raccolte in un'unica raccolta gerarchica. Questa operazione è simile a una `LEFT OUTER JOIN` in SQL.

## <a name="example"></a>Esempio

Nell'esempio di codice seguente viene eseguito un join implicito per combinare un elenco di clienti con i relativi ordini.

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a>Esempio

L'esempio di codice seguente unisce due raccolte usando la clausola `Join`.

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

In questo esempio verrà generato un output simile al seguente:

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a>Esempio

Nell'esempio di codice seguente vengono unite due raccolte utilizzando la clausola `Join` con due colonne chiave.

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

Nell'esempio viene generato un output simile al seguente:

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Query](../../../visual-basic/language-reference/queries/index.md)
- [Clausola Select](../../../visual-basic/language-reference/queries/select-clause.md)
- [Clausola From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Clausola Group Join](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Clausola Where](../../../visual-basic/language-reference/queries/where-clause.md)
